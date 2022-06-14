
<main>
    <h1 class="orange">Language Experience</h1>
    <ul>
        <li>Python: Intro to CS Course</li>
        <li>Java: Intro to Data Structures and Software Development Lifecycle</li>
        <li>C++: Advanced Data Structures</li>
        <li>C: 2 weeks of Advanced Data Structures</li>
        <li>x86 Assemby: 3 weeks of Advanced Data Structures</li>
        <li>JavaScript, CSS: Summer internship with General Dynamics learned JS and CSS through Svelte</li>
    </ul>

    <h1 class="blue">Operating Systems</h1>
    <ul>
        <li>Windows: Personal OS and the one I have used the longest</li>
        <li>Linux: Advanced Data Structures taught in a Linux environment, worked in both Linux and Windows at General Dynamics</li>
    </ul>

    <h1 class="orange">Personal Projects</h1>
    <ul>
        <li>Python: Regex Project where the user specifies their desired start and end time of a class, as well as an <br>
        additional optional parameter (class department). The program then outputs all the classes that meet during <br>
        that time as well as the professor, his rating, course difficulty, and average GPA of the class.</li>

        <li>C++: NxN Grid Solver. The user inputs the size of the board he would like to solve and then inputs the grid. <br>
        The program then uses a breadth first search to determine the least amount of moves to solve the puzzle. It then <br>
        outputs the least amount of moves needed, as well as the moves themselves to solve the puzzle.</li>

        <li>Svelte: <a href="http://localhost:8080/">Building a website as my resume</a>
        </li>
    </ul>

    <h1 class="blue">School Projects</h1>
    <ul>
        <li>Java: Semester long Meme Project, where we designed a way for users to locally create and post memes to a feed. <br>
        Through this project also gained experience with Swing GUI framework, by generating a GUI that allowed users to create <br>
        a meme and then save it to their files on their computer.</li>

        <li>C++: Creating and AVL Tree from scratch that performs the necessary rotations when data is inserted.</li>

        <li>C++: Word search puzzle. The code starts by creating a hash table of all the words from a dictionary, and then <br>
        performs a search on a NxN grid to solve all the valid words, which are longer than 3 letters. Necessary optimizations <br>
        were added such that the code could solve a 300x300 grid in 300ms. The optimizations were: creating hash tables to check <br>
        valid prefixes of words in the dictionary, and stopping the search if it can back false, buffering the output, and finding <br>
        an optimal load factor.</li>

        <li>C++: Encoding and Decoding a string of text using a custom built Huffman Encoding Tree</li>
    </ul>

</main>

<style>

    main{
        font-family: "Times New Roman", Times, serif;
        margin-bottom: 50px;  
    }

    li{
        margin: 10px;
    }

    .orange{
        color: orange;
        padding-bottom: 10px;
        border-bottom: 3px solid orange;
    }

    .blue{
        color: blue;
        padding-bottom: 10px;
        border-bottom: 3px solid blue;
    }

</style>