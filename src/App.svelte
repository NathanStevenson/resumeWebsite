<script>
	import Header from './Components/Header.svelte';
	import Footer from './Components/Footer.svelte';
	import Images from './Components/Images.svelte';
	import Tabs from './Components/Tabs.svelte';
	import HighSchool from './Components/HighSchool.svelte';
	import College from './Data/College.svelte';
	import Languages from './Data/Languages.svelte';
	import Work from './Data/Work.svelte';
	import Password from './Components/PasswordModal.svelte';

	let tabs = ["Home", "Highschool", "College", "Work", "Programming Languages"];
	let activeTab = "Home";

	let showModal = true;
	let showErrorMessage = false;
	let username = "";
	let password = "";
	let favColor;

	/* change the activeTab on a click event in the Tab.svelte that gets dispatched here*/
	const tabChange = (e) => { activeTab = e.detail; }
	const toggleOff = (e) => {
		username = e.detail.uName;
		password = e.detail.pWord;
		if(e.detail.pWord != "wahoowa21" || e.detail.uName == ""){
			showErrorMessage = true;
			showModal = true;
			username = "";
			password = "";
		}
		else{
			showErrorMessage = false;
			showModal = false;
			favColor = e.detail.fColor;
		}
	}

</script>

{#if showModal}
<Password {favColor} {password} {username} {showErrorMessage} on:loggingIn={toggleOff} />
{:else}
<Header />
<main>
	<div class = "welcome">
		<h1 style="color: {favColor}">Welcome: {username}!</h1>
	</div>
	<Tabs {favColor} activeTab={activeTab} tabs={tabs} on:changeTab = {tabChange}/>
	{#if activeTab === "Home"}
		<div class="summary">
			<h1>Summary: </h1>
			<p>Third year student majoring in Computer Science through the School of Engineering and Applied Science at the University of Virginia with minors in Applied Mathematics and Economics. I am searching for a summer internship.</p>
		</div>
		<div class="Contact_Information">
			<h1>Contact Information: </h1>
			<p>
				Home Address: 853 West Main Street, Charlottesville, Virginia 22903 <br>
				Email: nts7bcj@virginia.edu <br>
				Phone Number: 434-529-7289 <br>
				<a target="_blank" rel="noopener noreferrer" href="https://www.linkedin.com/in/nathaniel-stevenson-0848531b5/">LinkedIn</a>
			</p>
		</div>
		<Images />
	{:else if activeTab === "Highschool"}
		<HighSchool />
	{:else if activeTab === "College"}
		<College />
	{:else if activeTab === "Work"}
		<Work />
	{:else if activeTab === "Programming Languages"}
		<Languages />
	{:else}
		<div>This should never be reached!</div>
	{/if}

</main>
<Footer />
{/if}

<style>
	
	.Contact_Information{
		font-family: "Times New Roman", Times, serif;
		margin-bottom: 0px;
		border-bottom: 3px solid rgba(9, 9, 9, 0.129);
		width: 30%;
	}
	.summary{
		font-family: "Times New Roman", Times, serif;
		margin-bottom: 0px;
	}
	.welcome{
		font-family: "Times New Roman", Times, serif;
		position: relative;
		padding-bottom: 0px;
		margin-bottom: 0px;
		font-size: 14px;
		text-align: center;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}

</style>