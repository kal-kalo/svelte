<form action="" id="collectionForm">
    <div class="input-label-container">
        <label class="mainLabel" for="numOfitemsInput">Number of items to receive: </label>
        <input type="number" name="" id="numOfitemsInput" value="5">
    </div>

    <div class="input-label-container">
        <label class="mainLabel" for="collectionsInput">Collections:</label>
        <select id="collectionsInput">
            <optgroup label="">
                <option value="ours">Choose collection</option>
            </optgroup>
            <optgroup label="Language Learning">
                <option value="2a">2a</option>
                <option value="2b">2b</option>
                <option value="3c">3c</option>
            </optgroup>
            <optgroup label="Islam Learning">
                <option value="3a">3a</option>
                <option value="3b">3b</option>
                <option value="3c">3c</option>
            </optgroup>
        </select>
        <label for="fileInput"> Or upload yours </label>
        <input type="file" name="" id="fileInput">
    </div>

    <label class="mainLabel" for="time">Notify me at: </label>
    <div id="interval-container">
        <input type="time" name="" id="time"><label class="day" for="sat">S</label><input class="dayCheckbox" type="checkbox" name="" id="sat"><label class="day" for="sun">S</label><input class="dayCheckbox" type="checkbox" name="" id="sun"><label class="day" for="mon">M</label><input class="dayCheckbox" type="checkbox" name="" id="mon"><label class="day" for="tue">T</label><input class="dayCheckbox" type="checkbox" name="" id="tue"><label class="day" for="wed">W</label><input class="dayCheckbox" type="checkbox" name="" id="wed"><label class="day"  for="thu">T</label><input class="dayCheckbox" type="checkbox" name="" id="thu"><label class="day"  for="fri">F</label><input class="dayCheckbox" type="checkbox" name="" id="fri">
       <button id="addAlarmBtn">➕</button>
    </div>
    
    
    <input type="submit" value="Submit">
</form>

<style>

	.day{
		border: 1px solid gray;
		border-radius: 50%; 
		display: flex;
		margin: 5px;
		width: 20px;
		height: 20px;
		user-select: none;
		font-size: small;
		justify-content: center;
		align-items: center;
		

	}
	.dayCheckbox{
		display: none;
	}
   
	form{
		border: 1px solid gray;
		padding: 10px;
	}
	
	#interval-container{
		display: flex;
		
	}
	
</style>
