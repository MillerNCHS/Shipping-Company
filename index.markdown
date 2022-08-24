<div id="sortableTrash" class="sortable-code"></div> 
<div id="sortable" class="sortable-code"></div> 
<div style="clear:both;"></div> 
<p> 
    <input id="feedbackLink" value="Get Feedback" type="button" /> 
    <input id="newInstanceLink" value="Reset Problem" type="button" /> 
</p> 
<script type="text/javascript"> 
(function(){
  var initial = "# Your Name\n" +
    "# The Date\n" +
    "# Create three columns of the top 5 selling videogames of all-time\n" +
    "print(&quot;{:20}{:&gt;15}{:&gt;20}&quot;.format(&quot;Game&quot;, &quot;Sales (In Millions)&quot;, &quot;Platform&quot;))\n" +
    "print(&quot;{:20}{:&gt;10}{:&gt;30}&quot;.format(&quot;Minecraft&quot;,238,&quot;Multi-platform&quot;))\n" +
    "print(&quot;{:20}{:&gt;10}{:&gt;30}&quot;.format(&quot;Grand Theft Auto V&quot;,168,&quot;Multi-platform&quot;))\n" +
    "print(&quot;{:20}{:&gt;10}{:&gt;30}&quot;.format(&quot;Tetris (EA)&quot;,100,&quot;Mobile&quot;))\n" +
    "print(&quot;{:20}{:&gt;10}{:&gt;30}&quot;.format(&quot;Wii Sports&quot;,82.9,&quot;Nintendo Wii&quot;))\n" +
    "print(&quot;{:20}{:&gt;10}{:&gt;30}&quot;.format(&quot;PUBG&quot;,75,&quot;Multi-platform&quot;))";
  var parsonsPuzzle = new ParsonsWidget({
    "sortableId": "sortable",
    "max_wrong_lines": 10,
    "grader": ParsonsWidget._graders.LineBasedGrader,
    "exec_limit": 2500,
    "can_indent": true,
    "x_indent": 50,
    "lang": "en",
    "show_feedback": true
  });
  parsonsPuzzle.init(initial);
  parsonsPuzzle.shuffleLines();
  $("#newInstanceLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.shuffleLines(); 
  }); 
  $("#feedbackLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.getFeedback(); 
  }); 
})(); 
</script>
