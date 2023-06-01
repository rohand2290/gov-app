<script>
	let questions = ["The United States should work to improve security in the Middle East.", "The United States should always support the interests of its allies.", "I agree with left wing ideals.", "I agree with right-wing ideals.", "I favor a 2-state solution to the Israel-Palestine conflict, with a Jewish state and an Arab state.", "I favor Jerusalem being split between a Jewish state and an Arab state.", "The bombing of another nation, even if risking civilian casualities, is justified if security is threatened.", "I support the notion that a group of people should be able to reclaim their religious homeland.", "I support the notion that a group of people should not be pushed out from the land that they have lived in.", "Mass racial genocides, such as the Holocause, will never happen again in our modern world.", "I support Arab refugees being able to go back to Israel.", "Preventing people and goods from leaving or entering a country is justified when security is threatened by their free movement.", "Preventing a specific group of people from entering your country is justified if there is a potential security risk involved with letting them in.", "Israelis and Palestinians can live peacefully together despite their historical and cultural differences.", "Israelis have committed human rights violations during the conflict.", "Palestinians have committed human right violations during the conflict.", "The establishment of a Jewish homeland after World War 2 was the only way the Jewish people could finally escape millenia of persecution.", "The occupation of the West Bank and Golan Heights cannot be justified by the security situation of Israel.", "The settlement of Israelis into lands once inhabited by Palestinians is illegal.", "Jerusalem can be the capital of Israel if its inhabitants wish that to be the case.", "The state of Israel contributes to stability in the Middle East."]
	let questionNum = 1;
	let viewpointNum = 0;
	let selected;
	let handleSubmit = () => {
		questionNum++;
		console.log(selected);
		if (questionNum === 4 || questionNum === 5 || questionNum === 9 || questionNum === 10 || questionNum === 13 || questionNum === 14 || questionNum === 17 || questionNum === 18) {
			switch(selected) {
				case "Strongly Disagree":
					viewpointNum = viewpointNum + 2;
					break;
				case "Disagree":
					viewpointNum = viewpointNum + 1;
					break;
				case "No Opinion":
					break;
				case "Agree":
					viewpointNum = viewpointNum - 1;
				case "Strongly Agree":
					viewpointNum = viewpointNum - 2;
			}
		} else {
			switch(selected) {
				case "Strongly Disagree":
					viewpointNum = viewpointNum - 2;
					break;
				case "Disagree":
					viewpointNum = viewpointNum - 1;
					break;
				case "No Opinion":
					break;
				case "Agree":
					viewpointNum = viewpointNum + 1;
				case "Strongly Agree":
					viewpointNum = viewpointNum + 2;
			}


		}
	}

</script>
{#if questionNum > 21}
	<p class="text-2xl font-bold underline">Congratulations, you finished the test!</p>
	{#if viewpointNum > 0}
		<p class="text-2xl font-bold">You are a supporter of Israel.</p>
	{:else if viewpointNum < 0}
		<p class="text-2xl font-bold"> You are a supporter of Palestine.</p>
	{:else}
		<p class="text-2xl font-bold">You are undecided.</p>
	{/if}
{:else}

	<h2 class="text-4xl font-bold underline"> Question {questionNum} of 21 </h2>

		<p class="text-3xl">{questions[questionNum - 1]}</p>


		<form on:submit|preventDefault={handleSubmit}>
                        <label class="text-2xl" for="options">Opinion:</label>
			<select bind:value={selected} name="" id="question1" class="text-xl">
                                <option value="Strongly Disagree">Strongly Disagree</option>
                                <option value="Disagree">Disagree</option>
                                <option value="No Opinion">No Opinion</option>
                                <option value="Agree">Agree</option>
                                <option value="Strongly Agree">Strongly Agree</option>
                        </select>
                        <br><br>
			<button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded"type="submit">Next</button>
                </form>
{/if}
