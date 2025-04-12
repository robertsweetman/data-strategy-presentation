# Conclusion

<div id="donut-chart" style="width: 100%; display: flex; justify-content: center; align-items: center;"></div>

<script src="https://d3js.org/d3.v7.min.js"></script>
<script>
  document.addEventListener('DOMContentLoaded', function() {
    // Data for the chart
    const data = [
      { name: "Democratize Access", value: 25 },
      { name: "Increase Scrutiny", value: 25 },
      { name: "Actionable Feedback", value: 25 },
      { name: "Improve Training", value: 25 }
    ];
    
    // Check theme
    const isDarkTheme = document.documentElement.classList.contains('navy') || 
                       document.documentElement.classList.contains('ayu') ||
                       document.documentElement.classList.contains('coal');
    
    // Configure colors
    const textColor = isDarkTheme ? '#ffffff' : '#333333';
    const colors = d3.scaleOrdinal()
      .domain(data.map(d => d.name))
      .range(['#4e79a7', '#f28e2c', '#e15759', '#76b7b2']);
    
    // Set up dimensions - wider than tall for labels
    const width = 700;
    const height = 450;
    const margin = 140;
    const radius = Math.min(width - margin * 2, height - margin) / 2;
    const innerRadius = radius * 0.6;
    
    // Create SVG
    const svg = d3.select("#donut-chart")
      .append("svg")
        .attr("width", width)
        .attr("height", height)
      .append("g")
        .attr("transform", `translate(${width/2}, ${height/2})`);
    
    // Create the donut chart
    const pie = d3.pie()
      .value(d => d.value)
      .sort(null);
    
    const arc = d3.arc()
      .innerRadius(innerRadius)
      .outerRadius(radius);
    
    // Arc for label positioning
    const labelArc = d3.arc()
      .innerRadius(radius + 15)
      .outerRadius(radius + 15);
    
    const data_ready = pie(data);
    
    // Add segments
    svg.selectAll('path.segment')
      .data(data_ready)
      .join('path')
      .attr('class', 'segment')
      .attr('d', arc)
      .attr('fill', d => colors(d.data.name))
      .style('opacity', 0.8);
    
    // Add arrow markers at segment boundaries - completely revised
    data_ready.forEach((d, i) => {
      // Calculate position for each arrow
      const angle = d.endAngle;
      
      // For arrows exactly like the screenshot
      const arrowBase = 10; // Width of triangle base
      const arrowHeight = 10; // Height of triangle
      
      // Position at outer edge of donut (exact position where arrow should be)
      const x = Math.sin(angle) * radius;
      const y = -Math.cos(angle) * radius;
      
      // Get the color of the current segment
      const segmentColor = colors(d.data.name);
      
      // Create a simple triangular marker
      const trianglePath = svg.append('path');
      
      // Draw the triangle pointing outward from the circle
      if (angle === Math.PI/2) { // Top arrow (green in screenshot)
        trianglePath.attr('d', `M${x-arrowBase/2},${y} L${x+arrowBase/2},${y} L${x},${y-arrowHeight} Z`);
      } else if (angle === Math.PI) { // Left arrow (blue in screenshot) 
        trianglePath.attr('d', `M${x},${y-arrowBase/2} L${x},${y+arrowBase/2} L${x-arrowHeight},${y} Z`);
      } else if (angle === 3*Math.PI/2) { // Bottom arrow (orange in screenshot)
        trianglePath.attr('d', `M${x-arrowBase/2},${y} L${x+arrowBase/2},${y} L${x},${y+arrowHeight} Z`);
      } else if (angle === 0 || angle === 2*Math.PI) { // Right arrow (red in screenshot)
        trianglePath.attr('d', `M${x},${y-arrowBase/2} L${x},${y+arrowBase/2} L${x+arrowHeight},${y} Z`);
      }
      
      // Apply styles to match screenshot
      trianglePath
        .attr('fill', segmentColor)
        .attr('stroke', 'none');
    });
    
    // Add outer labels with lines
    svg.selectAll('.label-line')
      .data(data_ready)
      .join('polyline')
      .attr('class', 'label-line')
      .attr('points', function(d) {
        const pos = labelArc.centroid(d);
        const midAngle = (d.endAngle + d.startAngle) / 2;
        const posOutside = [
          pos[0] * (midAngle < Math.PI / 2 || midAngle > Math.PI * 1.5 ? 1.8 : 1.5), 
          pos[1] * 1.3
        ]; 
        return [arc.centroid(d), labelArc.centroid(d), posOutside];
      })
      .style('fill', 'none')
      .style('stroke', d => colors(d.data.name))
      .style('stroke-width', 1);
    
    // Add the labels outside the donut
    svg.selectAll('.label-text')
      .data(data_ready)
      .join('text')
      .attr('class', 'label-text')
      .attr('transform', function(d) {
        const pos = labelArc.centroid(d);
        const midAngle = (d.endAngle + d.startAngle) / 2;
        const posOutside = [
          pos[0] * (midAngle < Math.PI / 2 || midAngle > Math.PI * 1.5 ? 1.8 : 1.5), 
          pos[1] * 1.3
        ];
        return `translate(${posOutside})`;
      })
      .style('text-anchor', function(d) {
        return (d.endAngle + d.startAngle) / 2 > Math.PI ? 'end' : 'start';
      })
      .style('font-size', 14)
      .style('fill', textColor)
      .text(d => d.data.name);
    
    // Add central text
    svg.append('text')
      .attr('text-anchor', 'middle')
      .attr('dominant-baseline', 'middle')
      .attr('dy', -10)
      .style('font-size', 18)
      .style('fill', textColor)
      .text('Data');
      
    svg.append('text')
      .attr('text-anchor', 'middle')
      .attr('dominant-baseline', 'middle')
      .attr('dy', 15)
      .style('font-size', 18)
      .style('fill', textColor)
      .text('Strategy');
  });
</script>