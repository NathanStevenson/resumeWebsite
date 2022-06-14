<script>
    
    import Transcript from './Transcripts.svelte';
    
    let showTranscript = false;
	let transcriptImg = "/Images/";

    const displayHSTranscript = () => {
		showTranscript = true;
		transcriptImg = "/Images/TandemTranscript.png";
	}

    const closeTranscript = () => {
        showTranscript = false;
		transcriptImg = "/Images/";
    }
</script>



<div>
    <div class="highSchool_Info">
        <h1>Tandem Friends School</h1>
        <p class="TimeAttended">August 2016 - May 2020</p>
    </div>

    <div class="Academics">
        <h2>Academics:</h2>
        <ul>
            <li>
                <p class="GPA">GPA: 4.32</p>
                <p class="UnofficialTranscript" on:click={displayHSTranscript}>Unofficial Transcript</p>
            </li>
        </ul>
    </div>

    <div>
        <Transcript {showTranscript} {transcriptImg} on:closeTranscript={closeTranscript}/>
    </div>

    <h2>Clubs and Achievements:</h2>
    <ul>
        <li>
            <h3>Clubs: </h3>
            <div class="clubs">
                <p>Ran Cross Country, Indoor Track, and Outdoor Track for four years</p>
                <p>Member of the Science Olympiad Team for four years</p>
                <p>Member of Latin Club for four years</p>
                <p>Member of Tandem Earth for 3 years</p>
                <p>Member of Student Senate for 2 years</p>
            </div>

            <h3>Achievements: </h3>
            <div class="achievements">
                <p>Captain of Cross Country, Indoor Track, and Outdoor Track my Senior year</p>
                <p>Science Olympiad Leadership Team Junior and Senior year</p>
                <p>Won medals for Boomilever, Thermodynamics, and Circuits at Science Olympiad</p>
                <p>President of Latin Club Junior and Senior year</p>
                <p>Treasurer for Tandem Earth Senior Year</p>
                <p>Won 4x800 relay at States, and Conference Champions for Cross Country</p>
            </div>
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
h3{
    color: rgb(0, 142, 0);
}

.TimeAttended{
    font-weight:bold;
    margin-top: 0px;
    margin-bottom: 10px;
    padding-bottom: 10px;
    border-bottom: 3px solid rgb(0, 142, 0);
    width: 25%;
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
    border-bottom: 3px solid rgb(0, 142, 0);
    width: 25%;
    margin-bottom: 10px;
}

.clubs{
    margin-left: 30px;
}
.achievements{
    margin-left: 30px;
}

.highSchool_Info{
    margin-bottom: 10px;
}

</style>