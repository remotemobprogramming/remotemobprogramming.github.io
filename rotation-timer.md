*Time to next turn* is one of the main drivers of participant engagement. In other words, the higher the time to next turn, the higher the probability to become disengaged.

<div>
<label>
  Participants
  <input id="size" name="size" type="number" value="4" onchange="update()" min="3" required />
</label>
</div>

<div style="margin-top: 1em;">
  <ul>
    <li>next turn in <strong>30 minutes</strong>: rotation time <= <strong><span id="rotationTime30Minutes">5</span> minutes</strong> (recommended)</li>
    <li>next turn in <strong>45 minutes</strong>: rotation time <= <strong><span id="rotationTime45Minutes">5</span> minutes</strong></li>
    <li>next turn in <strong>60 minutes</strong>: rotation time <= <strong><span id="rotationTime60Minutes">5</span> minutes</strong></li>
  </ul>
</div>



<script type="application/javascript">
  function rotationTime(size, timeToNextTurn) {
    return Math.round(timeToNextTurn / (size - 1))
  }


  function update() {
    let size = parseInt(document.getElementById('size').value)
    document.getElementById('rotationTime30Minutes').innerText = rotationTime(size, 30)
    document.getElementById('rotationTime45Minutes').innerText = rotationTime(size, 45)
    document.getElementById('rotationTime60Minutes').innerText = rotationTime(size, 60)
  }

  update()
</script>
