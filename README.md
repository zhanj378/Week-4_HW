<!DOCTYPE html>
<html>
<head>
    <title>Hangman!</title>
</head>
<body>
    <h1> Hangman Game for Most Famous Landmarks in The World</h1>
    <script type="text/javascript">
    //An array of words

    var words = ["eiffel tower", "big ben", "leaning tower of pisa", "colosseum", "empire state building", "hollywood", "golden Gate Bridge", "tokyo tower", "london eye", "the great wall"]

    //Pick a random word from the words array

    var word = words[Math.floor(Math.random() * words.length)]
    console.log("Random word is: " + word)

    //Answer array 

    var answerArray = []
    for (var i = 0; i < word.length; i++) {
        answerArray[i] = "_"
    }

    var remainingLetters = word.length
    var guesses = 10;

    //The Game Loop

    while (remainingLetters > 0 && guesses > 0) {
        //Show the player their progress
        alert(answerArray.join(" "))

        //Get a guess from the player

        var guess = prompt("Guess a letter, or click cancel to stop playing.")
        if (guess === null) {
            //Exit the game
            break
        } else if (guess.length !== 1) {
// console.log("answerArray2 = " + answerArray)
            alert("Please enter a single letter.")
        } else {
            guesses--
            guess = guess.toLowerCase()
            for (var j = 0; j <word.length; j++) {
            //Update the game state with the guess
            	if (word[j] === guess && answerArray[j] === "_") {
                answerArray[j] = guess
                remainingLetters--
                    }
                }
            }
        }
        //End of the game loop

        //Show answer and congratulate the player
        alert(answerArray.join(" "))

	    if (guesses > 0) {
	      alert("Good job! The answer was " + word + ".")
	    } else {
	      alert("Too bad! The answer was " + word + ".")
	    }
    </script>
</body>

</html>
