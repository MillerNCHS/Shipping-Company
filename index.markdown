<div id="sortableTrash" class="sortable-code"></div> 
<div id="sortable" class="sortable-code"></div> 
<div style="clear:both;"></div> 
<p> 
    <input id="feedbackLink" value="Get Feedback" type="button" /> 
    <input id="newInstanceLink" value="Reset Problem" type="button" /> 
</p> 
<script type="text/javascript"> 
(function(){
  var initial = "age = input(&quot;How old are you? &quot;)\n" +
    "print(&quot;Got it! You are&quot;,age,&quot;years old. Now I will ask how old your teacher is...&quot;)\n" +
    "teacher = input(&quot;How old is your teacher? &quot;)\n" +
    "print(&quot;Got it! Your teacher is&quot;,age,&quot;years old. Let&#039;s find out how much older your teacher is...&quot;)\n" +
    "difference = int(teacher) - int(age)\n" +
    "print(&quot;You are&quot;,str(difference),&quot;years older than your teacher.&quot;)";
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
