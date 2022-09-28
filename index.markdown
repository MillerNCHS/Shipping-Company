<div id="sortableTrash" class="sortable-code"></div> 
<div id="sortable" class="sortable-code"></div> 
<div style="clear:both;"></div> 
<p> 
    <input id="feedbackLink" value="Get Feedback" type="button" /> 
    <input id="newInstanceLink" value="Reset Problem" type="button" /> 
</p> 
<script type="text/javascript"> 
(function(){
  var initial = "weightMin = 10\n" +
    "weightMax = 100\n" +
    "weight = int(input(&quot;Enter the weight of the package: &quot;))\n" +
    "while (weight &lt; weightMin or weight &gt; weightMax):\n" +
    "	if weight &lt; weightMin:\n" +
    "    	weight = int(input(&quot;The weight must be greater than &quot;+str(weightMin)+&quot;. Please enter a new weight: &quot;))\n" +
    "    elif weight &gt; weightMax:\n" +
    "    	weight = int(input(&quot;The weight must be less than &quot;+str(weightMax)+&quot;. Please enter a new weight: &quot;))\n" +
    "print(&quot;Thank you for shipping with us!&quot;)";
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
