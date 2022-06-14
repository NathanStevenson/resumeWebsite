<script>
    
    import Transcript from '../Components/Transcripts.svelte';
    
    let showTranscript = false;
	let transcriptImg = "/Images/";

    const displayCollegeTranscript = () => {
		showTranscript = true;
		transcriptImg = "/Images/UVA_Transcript2022.png";
	}

    const closeTranscript = () => {
        showTranscript = false;
		transcriptImg = "/Images/";
    }
</script>

<div>
    <div class="college_Info">
        <h1>University of Virginia</h1>
        <p class="TimeAttended">August 2020 - Present</p>
    </div>

    <div class="Academics">
        <h2>Academics:</h2>
        <ul>
            <li>
                <p class="GPA">GPA: 3.916</p>
                <p class="UnofficialTranscript" on:click={displayCollegeTranscript}>Unofficial Transcript</p>
            </li>
        </ul>
    </div>

    <div>
        <Transcript {showTranscript} {transcriptImg} on:closeTranscript={closeTranscript}/>
    </div>

    <h3>Extracurriculars:</h3>
    <ul>
        <li>
            <p>Member of the Ultimate Frisbee Team: Night Train</p>
            <p>Treasurer of Night Train</p>
            <p>Coding projects in my free time and learning other programming langauges</p>
        </li>
    </ul>
</div>

<style>

div{
    font-family: "Times New Roman", Times, serif;
    margin-bottom: 50px;  
}
li{
    list-style:none;
}
h1{
    margin-bottom: 0px;
    padding-bottom: 5px;
}
h2{
    color: rgb(0, 0, 191);
}
h3{
    color:rgb(0, 0, 191);
}
.UnofficialTranscript{
    color: blue;
    text-decoration: underline;
    cursor: pointer;
    width: 42%;
}
.UnofficialTranscript:hover{
    color: rgb(183, 0, 82);
}
.Academics{
    border-bottom: 3px solid rgb(225, 146, 0);
    width: 25%;
    margin-bottom: 10px;
}
.college_Info{
    border-bottom: 3px solid rgb(225, 146, 0);
    width: 25%;
    margin-bottom: 10px;
}
.TimeAttended{
    font-weight:bold;
    margin-top: 0px;
    margin-bottom: 10px;
    padding-bottom: 0px;
}

</style>