<main>
	<title>Burgeon</title>
	<div style="margin-top:15px;margin-bottom:15px;">
		<a on:click={() => send_to_mix("Writeups")} href="writeups">Writeups</a>
		✧ <a href="/about">{ti["about"][lshort]}</a> ✧ 
		<a href="/promo">{ti["contribute"][lshort]}</a><!-- ✧
		<a href="/brute">Bruteforce Method</a>-->
	</div>
	<img src="images/fluer1.svg" class="circle-light-up" style="filter: invert(100%); border: none;" title="{ti["name-info"][lshort]}" height=200px alt="logo banner">
	<h1 class="light-up-underline" title="{ti["name-info"][lshort]}" style="margin-top:5px;">burgeon</h1>
	<p style="margin-top: 3px;">
		{ti["description-p1"][lshort]}<br>
		{ti["description-p2"][lshort]}<br>
		We are part of the <a target="_blank" href="https://neuroregen.org">neuroregen collective [soon]</a>.
	</p>
	<p title="This is to spread our influence." style="font-size: 19px;margin-bottom:0px;">🚨 <span class="rainbow_text_animated"><a target="_blank" style="text-decoration:underline" rel="noreferrer" href="https://twitter.com/burgeonbook">Follow @burgeonbook</a></span> 🚨</p>
	<span>
		<!--
		<span>{ti["languages"][lshort]}:</span>
		<b>English, Arabic</b>
		{#each ["fr", "ru"] as lang}
		<img class="mini-flag" src="images/flags/{lang}.svg" alt="{lang}" style="filter: grayscale(1);" title="{ti["lang-disclaim"][lshort]}">
		{/each}
		-->
		</span>
	
	<!--<p><b>New <u><a href="/writeups">Writeups</a></u> section!</b></p>--><br>
	
	<!--
	<a on:click={() => send_to_mix("Physical Book")} href="physical_copy" rel="noreferrer"><button class="button">Physical Copy</button></a><br>
	<div style="padding-top:5px;font-size: 18px;"><a href="/chapter/1">Online version</a></div>
	-->
	<a href="/chapter/1"><button class="button">{ti["online-version"][lshort]}</button></a><br>
	<div style="padding-top:5px;font-size: 18px;"><a href="/brute">{ti["bruteforce-method"][lshort]}</a></div>
	<br>
	<!-- <a on:click={() => send_to_mix("Audiobook")} href="https://odysee.com/ppmo_audiobook_v3:e" rel="noreferrer" title="{ti["audiobook-info"][lshort]}">{ti["audiobook"][lshort]}</a> ✧ -->
	<!-- <a on:click={() => send_to_mix("Donate")} href="https://opencollective.com/ppmo-collective-fund" target="_blank" rel="noreferrer" title="{ti["donate-info"][lshort]}">{ti["donate"][lshort]}</a> ✧ --> 
	<Snow/>
</main>

<script>
	import Snow from '../components/Snow.svelte';

	export let translation_index = {};
	let ti = translation_index;
	export let language_info = {};
	let lshort = language_info.short_name;

	let ls_id = localStorage.getItem("usr_id");
		if(ls_id == undefined) {
			let date = Date.now()
			localStorage.setItem("usr_id", date);
			ls_id = date;
		}

	mixpanel.init('69f9e45d45df5706a4dda82222fb4141', {debug: true, ignore_dnt: true});
	mixpanel.identify(ls_id);

	function send_to_mix(text) {
		mixpanel.track(text);
	}

</script>
