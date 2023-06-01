<script>
	let questions = ["The United States should work to improve security in the Middle East.", "The United States should always support the interests of its allies.", "Where do you lie on the ideological spectrum.", "I favor a 2-state solution to the Israel-Palestine conflict, with a Jewish state and an Arab state.", "I favor Jerusalem being split between a Jewish state and an Arab state.", "The bombing of another nation, even if risking civilian casualities, is justified if security is threatened.", "I support the notion that a group of people should be able to reclaim their religious homeland.", "I support the notion that a group of people should not be pushed out from the land that they have lived in.", "Mass racial genocides, such as the Holocause, will never happen again in our modern world.", "I support Arab refugees being able to go back to Israel.", "Preventing people and goods from leaving or entering a country is justified when security is threatened by their free movement.", "Preventing a specific group of people from entering your country is justified if there is a potential security risk involved with letting them in.", "Israelis and Palestinians can live peacefully together despite their historical and cultural differences.", "Israelis have committed human rights violations during the conflict.", "Palestinians have committed human right violations during the conflict.", "The establishment of a Jewish homeland after World War 2 was the only way the Jewish people could finally escape millenia of persecution.", "The occupation of the West Bank and Golan Heights cannot be justified by the security situation of Israel.", "The settlement of Israelis into lands once inhabited by Palestinians is illegal.", "Jerusalem can be the capital of Israel if its inhabitants wish that to be the case.", "The state of Israel contributes to stability in the Middle East."]

	import Question from "./Question.svelte";
</script>
<div class="flex justify-center">
	<p class="text-5xl font-bold">Should the United States support Israel 🇮🇱 or Palestine 🇵🇸?</p>
</div>

<div class="grid grid-cols-1 h-screen place-items-center">
	<div>
		<Question />
	</div>
</div>
