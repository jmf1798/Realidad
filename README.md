<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Interactive Video Storyboard</title>
    <!-- Add Font Awesome CSS -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        /* Add CSS for the parallax header */
        .parallax-header {
            background-image: url('parallax-background.jpg');
            background-attachment: fixed;
            background-position: center;
            background-repeat: no-repeat;
            background-size: cover;
            color: #fff;
            text-align: center;
            padding: 100px 0;
        }

        /* Style for the header content */
        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        /* Style for the menu and search bar */
        .menu-and-search {
            background-color: #FFFFFF;
			position:-webkit-sticky;
			position: sticky;
            overflow: hidden;
            display: flex;
            align-items: center; /* Align the menu to the left */
			top: 0; /* Stick the navigation bar to the top of the viewport */
            z-index: 100; /* Ensure the navigation bar is above other elements */
        }

        .menu {
            display: flex;
        }

        .menu a {
            display: inline-block; /* Display menu items horizontally */
            color: black;
            text-align: center;
            padding: 14px 16px;
            text-decoration: none;
        }


        /* Style for the search bar */
        .search-bar {
            display: flex;
            align-items: center;
            margin-left: 10px; /* Add some space between the menu items and the search box */
        }

        .search-bar input[type="text"] {
            padding: 5px;
            border-radius: 5px;
            border: 1px solid #ccc;
        }

        .search-bar i {
            font-size: 20px;
            cursor: pointer;
            margin-left: 5px;
        }

     
        /* Style for the login button */
		.login-button {
			background-color: #cc8f32;
			color: #fff; /* White text color */
			border: none;
			padding: 10px 20px;
			border-radius: 5px;
			cursor: pointer;
			text-decoration: none; /* Remove underlines for better appearance */
			margin-right: 10px; /* Add some space between the login button and other menu items */
			margin-left: 10px; /* Add margin to the left side to move the login button to the left */
}

        }

        /* Style for the login button hover effect */
        .login-button:hover {
            background-color: #0056b3; /* Darker blue on hover */
        }

        /* Add your existing styles below */
    body {
    font-family: 'Poppins', Comforta, Century Gothic; /* Use the Poppins font */
    background: url('paper-texture.jpg') no-repeat;
    background-size: cover;
    background-position: center;
    margin: 0;
    padding: 0;
    min-height: 100vh;
    position: relative; /* Position relative to allow for ::before pseudo-element */
}

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
        }
body::before {
    content: "";
    background-color: #24471f; /* Color overlay */
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    opacity: 0.5; /* Adjust the opacity as needed */
}


.left-column {
    flex: 1;
    padding: 20px;
    background-color: #dfdfdf;
    border: 1px solid #ddd;
    border-radius: 5px;
    position: relative;
    z-index: 1;
    margin-right: 10px; /* Add right margin for spacing */
}

.right-column {
    flex: 1;
    padding: 20px;
    background-color: #dfdfdf;
    border: 1px solid #ddd;
    border-radius: 5px;
    position: relative;
    z-index: 1;
}



      .video-container {
			position: relative;
			padding-bottom: 56.25%;
			padding-top: 30px;
			height: 0;
			overflow: hidden;
		}
		 video {
            width: 100%;
			}

        .storyboard {
            display: flex;
            justify-content: space-between;
            margin-top: 20px;
        }

        .storyboard-item {
            flex: 1;
            margin: 0 10px;
            padding: 10px;
            background-color: #fff;
            border: 1px solid #ddd;
            border-radius: 5px;
            text-align: center;
            cursor: pointer;
            transition: background-color 0.3s ease;
            position: relative;
        }

        .storyboard-item:hover {
            background-color: #e0e0e0;
        }

        .video-buttons {
            display: flex;
            justify-content: space-between;
            margin-top: 20px;
        }

        .video-buttons button {
            background-color: #1877f2;
            color: #fff;
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.3s ease;
            display: flex;
            align-items: center;
        }

        .video-buttons button:hover {
            background-color: #0e5aee;
        }

        .video-buttons .like-button {
            flex: 1;
            margin-right: 10px;
        }

        .video-buttons .share-button {
            flex: 1;
        }

        /* Style for the cover images and play buttons */
        .scene-cover {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 1;
        }

        .scene-play-button {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            z-index: 2;
            padding: 10px 20px;
            background-color: #1877f2;
            color: #fff;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }

        /* Add a comment style */
        .comments {
            margin-top: 20px;
            border-top: 1px solid #ddd;
            padding-top: 20px;
        }

        .comment {
            margin-bottom: 10px;
        }

        /* Style for the comment form */
        .comment-form {
            margin-top: 20px;
        }

        .comment-form textarea {
            width: 100%;
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 5px;
            resize: vertical;
        }

        .comment-form button {
            margin-top: 10px;
            background-color: #1877f2;
            color: #fff;
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }

        .comment-form button:hover {
            background-color: #0e5aee;
        }
		/* Style for the subscribe button and subscriber count in the menu */
		/* Style for the subscribe button and subscriber count in the menu */
		.subscribe-button {
    display: flex;
    align-items: center; /* Align items vertically */
    margin-left: auto; /* Push the subscribe button to the right */
}

	.subscribe-button button {
    background-color: skyblue; /* Sky blue background color */
    color: #fff; /* White text color */
    border: none;
    padding: 10px 20px;
    border-radius: 5px;
    cursor: pointer;
    text-decoration: none; /* Remove underlines for better appearance */
    margin-right: 10px; /* Add some space to the right of the button */
}

	.subscribe-button button:hover {
    background-color: #00B7F9; /* Darker blue on hover */
}

	.subscribe-button .subscriber-count {
    font-size: 14px;
    color: #777;
}

	.subscribe-button .subscriber-count {
    font-size: 14px;
    color: #777;
}
	/* Style for the subscribe button and subscriber count in the menu */
	.subscribe-button {
    display: flex;
    align-items: center; /* Align items vertically */
    margin-left: auto; /* Push the subscribe button to the right */
}

	.subscribe-button button {
    background-color: #cc8f32; 
    color: #fff; /* White text color */
    border: none;
    padding: 10px 20px;
    border-radius: 5px;
    cursor: pointer;
    text-decoration: none; /* Remove underlines for better appearance */
    margin-right: 10px; /* Add some space to the right of the button */
}

	.subscribe-button button:hover {
    background-color: #24471f; /* Darker red-orange on hover */
}

	.subscribe-button .subscriber-count {
    font-size: 14px;
    color: #00B7F9;
}
	nav ul {
            list-style-type: none; /* Remove bullet points */
            padding: 0;
            margin: 0;
        }

        /* Style for navigation list items */
        nav ul li {
            display: inline; /* Display list items horizontally */
            margin-right: 20px; /* Add some space between list items */
        }
	 .video-question {
    position: absolute;
    top: 20%; /* Adjust the top value to position the content higher up */
    left: 50%;
    transform: translate(-50%, 0); /* Adjust the second parameter to control vertical positioning */
    background: rgba(0, 0, 0, 0.5);
    color: #fff;
    padding: 10px;
    border-radius: 5px;
    display: none;
    width: 80%; /* Adjust the width as needed */
}

        .close-button {
            position: absolute;
            top: 5px;
            right: 5px;
            cursor: pointer;
        }
		/* Inside your existing CSS style */
/* CSS for the video gallery and video elements */
/* Style for the video gallery and video elements */
/* Style for the video gallery and video elements */
.video-gallery {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-wrap: wrap;
    margin-top: 20px; /* Add margin at the top of the video gallery */
}

.video {
    margin: 10px; /* Adjust the margin to control spacing */
    text-align: center;
    border: none;
    cursor: pointer;
    position: relative;
    overflow: hidden; /* Hide the inner elements when not hovered */
    transition: transform 0.3s, box-shadow 0.3s, z-index 0.3s;
}

/* Add green background to Scene A (Video 2) */
.video:nth-child(2) {
    margin-right: 10px; /* Reduce the right margin for Scene A */
    background-color: #24471f; /* Green background color */
}

/* Add green background to Scene B (Video 3) */
.video:nth-child(3) {
    margin-left: 10px; /* Reduce the left margin for Scene B */
    margin-right: 10px; /* Reduce the right margin for Scene B */
    background-color: #cc8f32; /* Green background color */
}

/* Add hover styles for Scene A and Scene B */
.video:nth-child(2):hover,
.video:nth-child(3):hover {
    transform: scale(1.05); /* Enlarge the scene */
    box-shadow: 0 10px 20px rgba(0, 0, 0, 0.3); /* Add a shadow */
    z-index: 1; /* Bring to the front */
    background-color: none; /* Dark green background color on hover */
}

	
	
 .scrollable-section {
            max-width: 100px; /* Set the desired maximum width */
            margin: 0 auto; /* Center the scrollable section horizontally */
            height: 300px; /* Set the desired height for the scrollable section */
            overflow-y: scroll; /* Enable vertical scroll */
            border: 1px solid #ccc; /* Optional border for styling */
            padding: 10px; /* Reduced padding for content inside the section */
        }
 footer {
        background-color: #333;
        color: #fff;
        text-align: center;
        padding: 20px;
        cursor: pointer;
    }

    footer:hover {
        background-color: #444;
    }
	
	/* Chatbox button style */
.chatbox-button {
    position: fixed;
    bottom: 20px;
    right: 20px;
    background-color: #cc8f32;
    color: #fff;
    border: none;
    border-radius: 50%;
    width: 50px;
    height: 50px;
    font-size: 24px;
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: center;
    z-index: 100;
}

/* Chatbox container style */
.chatbox {
    position: fixed;
    bottom: 20px;
    right: 80px; /* Adjust this value to properly position the chatbox icon */
    width: 300px;
    background-color: #fff;
    border: 1px solid #ccc;
    border-radius: 5px;
    display: none;
}

.chatbox-header {
    background-color: #cc8f32;
    color: #fff;
    display: flex;
    justify-content: space-between;
    padding: 10px;
    border-radius: 5px 5px 0 0;
}

.chatbox-title {
    font-size: 18px;
    font-weight: bold;
}

.chatbox-close {
    font-size: 20px;
    cursor: pointer;
}

.chatbox-close:hover {
    color: #f00;
}

.chatbox-messages {
    max-height: 200px;
    overflow-y: auto;
    padding: 10px;
}

.chatbox-input {
    display: flex;
    align-items: center;
    padding: 10px;
}

#chatbox-input {
    flex: 1;
    padding: 5px;
    border: 1px solid #ccc;
    border-radius: 5px;
    margin-right: 10px;
}

#chatbox-send {
    background-color: #cc8f32;
    color: white;
    border: none;
    border-radius: 5px;
    padding: 5px 10px;
    cursor: pointer;
}

/* Style for the "Next" button */
.next-button {
    background-color: transparent;
    color: #fff;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    display: none;
    align-items: center;
    padding: 10px 20px;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    position: absolute;
    bottom: 20px; /* Adjust the position as needed */
    right: 20px; /* Adjust the position as needed */
}

.next-button i {
    margin-left: 5px;
    font-size: 20px;
}

.next-button:hover {
    background-color: rgba(0, 0, 0, 0.2);
}

/* Style for the video player */
.video {
    position: relative; /* Set the position to relative to allow absolute positioning */
}

/* Style for the "Question" section */
.video-question {
    position: absolute;
    top: 70%;
    left: 50%;
    transform: translate(-50%, -50%);
    background: rgba(0, 0, 0, 0.5);
    color: #fff;
    padding: 10px;
    border-radius: 5px;
    display: none;
    width: 80%; /* Adjust the width as needed */
    text-align: left; /* Align text to the left */
}

/* Style for the "Close" button */
.close-button {
    position: absolute;
    top: 5px;
    right: 5px;
    cursor: pointer;
}

 .on-top {
            position: absolute;
            z-index: 999; /* Set a high z-index */
        }
	.floating-ads-banner {
				position: fixed;
				bottom: 10px; /* Adjust the distance from the bottom as needed */
				right: 10px; /* Adjust the distance from the right as needed */
				z-index: 9999;
				background-color: #fff;
				box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.5);
				border-radius: 10px;
				overflow: hidden;
	}

		.floating-ads-banner .ads-content {
			position: relative;
	}

		/* Style for the close button */
		.floating-ads-banner .close-button {
			position: absolute;
			top: 10px;
			right: 10px;
			background-color: #fff;
			border: none;
			border-radius: 50%;
			padding: 5px 10px;
			cursor: pointer;
			z-index: 1;
}

.subscribe-button .subscriber-count {
    font-size: 14px;
    color: #24471f;
	}
	
	/* Style for the movie icon */
.movie-icon::before {
    content: '\f008'; /* Unicode for the movie icon (adjust as needed) */
    font-family: 'Font Awesome 6 Pro'; /* Replace with your Font Awesome font family */
    font-size: 20px; /* Adjust the size of the movie icon as needed */
    margin-right: 5px; /* Add space between the icon and text (adjust as needed) */
}



    </style>
</head>
<body>
<!-- Parallax header -->
<div class="parallax-header">
    <div class="header-content">
        <h1>R    E    A    L    I    D    A    D (G-4)</h1>
    </div>
</div>

<!-- Menu and Search Bar -->
<!-- Menu and Search Bar -->
<!-- Menu and Search Bar -->
<!-- Menu and Search Bar -->
<div class="menu-and-search">
    <a class="login-button" href="file:///C:/Users/Administrator/OneDrive/Desktop/Semi-Final%20Multimedia%20Project/Login%20Page.html">Login</a>
    <div class="menu">
        <a href="#home"></i> Home</a>
        <a href="#blogs"></i> Blogs</a>
        <a href="#about"></i> About Us</a>
    </div>
    <div class="search-bar">
        <input type="text" placeholder="Search">
        <i class="fas fa-search" style="margin-left: 5px;"></i>
    </div>
	 <div class="subscribe-button">
        <button id="subscribeButton" onclick="subscribe()">Subscribe</button>
        <div class="subscriber-count" id="subscriberCount">0 Subscribers</div>
    </div>
</div>

</div>



<div class="container">
    <div class="left-column">
        <!-- Add your right content here -->
         <div id="main-video" class="video">
    <h1>Interactive Video</h1>
    <video id="video-player" width="400" controls>
        <source src="" type="video/mp4">
        Your browser does not support the video tag.
    </video>
    <div class="video-question" id="question-section">
        <span class="close-button" onclick="closeQuestion()">X</span>
        <h2>Question:</h2>
        <p id="question">What do you think will happen next?</p>
        <p id="question">Choose either from Scene 1 or Scene 2 to proceed to the next story!</p>
    </div>
  <a href="file:///C:/Users/Administrator/OneDrive/Desktop/Realidad%20Movie%20Part2.html">
    <button id="next-button" class="next-button on-top" onclick="playNextVideo()">
        <i class="fas fa-arrow-right"></i> Next
    </button>
</a>
</div>

  <div class="video-gallery">
    <button class="video" onclick="loadVideo('SYMBIOSIS a short film by Mitchell Counsell.mp4', 'Interactive Film')">
        <img src="video1-thumbnail.jpg" alt="">
        <h3>MAIN FILM</h3>
    </button>
    <button class="video" onclick="loadVideo('ABC.mp4', 'Video 2 Title', true)">
        <img src="video2-thumbnail.jpg" alt="">
        <h3>SCENE A</h3>
    </button>
    <button class="video" onclick="loadVideo('SYMBIOSIS a short film by Mitchell Counsell.mp4', 'Video 3 Title', true)">
        <img src="video3-thumbnail.jpg" alt="">
        <h3>SCENE B</h3>
    </button>
    <!-- Add more video thumbnails as needed -->
</div>

		
        <!-- Add a comment section -->
        <div class="comments" id="comments">
            <h2>Share your thoughts</h2>
            <div class="comment">
                <strong>Anonymous 2023:</strong> Love this video!
            </div>
            <div class="comment">
                <strong>Miss125:</strong> Great video!
            </div>
        </div>
        <!-- Add a comment form -->
        <div class="comment-form">
            <h2>Add a Comment</h2>
            <textarea id="commentInput" placeholder="Write your comment here..." rows="4"></textarea>
            <button onclick="addComment()">Submit Comment</button>
        </div>
    </div>

    <div class="right-column">
	<div class="left-column">
        <!-- Add your left content here -->
     <article>
    <h2>The Societal Value of Education, Literacy, and Mental Health Awareness</h2>
    <img src="education-mental-health.jpg" alt="Education and Mental Health">
    <p>
        Education and literacy, along with mental health awareness, play pivotal roles in shaping not only individuals but also entire societies. These interconnected aspects contribute to the overall well-being and progress of communities. Let's delve into their significance.
    </p>
    <h3>Education and Literacy</h3>
    <p>
        Education is the cornerstone of personal development and societal advancement. It equips individuals with knowledge, skills, and critical thinking abilities necessary to lead fulfilling lives and contribute positively to society.
    </p>
    <p>
        Literacy, the ability to read and write, is an integral part of education. It empowers individuals to access information, participate in economic activities, and engage in civic life. A literate population is better equipped to address societal challenges and make informed decisions.
    </p>
    <h3>Mental Health Awareness</h3>
    <p>
        Mental health awareness is an essential component of societal well-being. It involves understanding, destigmatizing, and supporting individuals facing mental health challenges. Acknowledging mental health is as crucial as physical health.
    </p>
    <p>
        Promoting mental health awareness reduces the stigma surrounding mental illnesses, encouraging those affected to seek help and support. It also fosters empathy and compassion in society, creating a more inclusive and understanding community.
    </p>
    <h3>The Interconnection</h3>
    <p>
        Education and literacy contribute to mental health awareness in several ways. Educated individuals are more likely to recognize the importance of mental health and seek help when needed. Literacy enables access to mental health resources and information.
    </p>
    <p>
        Conversely, mental health challenges can hinder one's educational journey. Addressing mental health issues early can prevent educational setbacks and promote lifelong learning.
    </p>
    <h3>Conclusion</h3>
    <p>
        In summary, education, literacy, and mental health awareness are intertwined aspects of societal value. They empower individuals, foster personal and collective growth, and create a more inclusive and compassionate society. Prioritizing these areas benefits not only individuals but also the entire community, leading to a brighter and more prosperous future.
    </p>
</article>
<!-- Floating Ads Banner -->
<div class="floating-ads-banner">
    <div class="ads-content">
        <button class="close-button" onclick="closeFloatingAdsBanner()"><span>&times;</span></button>
        <img src="ads.gif" alt="Ads Banner">
    </div>
</div>

			
		
</div>

        </div>
    </div>
</div>

		<div id="chatbox-button" class="chatbox-button">
		<i class="fas fa-comments"></i>
		</div>

		<!-- Chatbox container -->
		<div id="chatbox" class="chatbox">
			<div class="chatbox-header">
				<span class="chatbox-title">Chat</span>
				<span id="chatbox-close" class="chatbox-close">×</span>
			</div>
			<div class="chatbox-messages" id="chatbox-messages">
			<!-- Chat messages will be displayed here -->
			</div>
		<div class="chatbox-input">
        <input type="text" id="chatbox-input" placeholder="Type a message...">
        <button id="chatbox-send">Send</button>
		</div>
</div>
<footer>
    <div class="container">
        <p>&copy; 2023 Your Website Name. All rights reserved.</p>
    </div>
</footer>

<script>

	function playNextVideo() {
    // ... your existing code to load and play the next video ...

    // Show the "Next" button again after loading the next video
    const nextButton = document.getElementById('next-button');
    nextButton.style.display = 'none'; // Hide the button
}

// Add an event listener to the main video for the "ended" event
const mainVideo = document.querySelector('#main-video video');
mainVideo.addEventListener('ended', () => {
    // Show the "Next" button when the main video ends
    const nextButton = document.getElementById('next-button');
    nextButton.style.display = 'block'; // Display the button
});

     function loadVideo(videoUrl, videoTitle, closeQuestion = false) {
            const mainVideo = document.querySelector('#main-video video');
            const videoQuestion = document.querySelector('#question-section');

            mainVideo.innerHTML = ''; // Clear any previous source elements
            mainVideo.innerHTML = `
                <source src="${videoUrl}" type="video/mp4">
                Your browser does not support the video tag.
            `;
            mainVideo.parentElement.querySelector('h1').innerText = videoTitle;

            mainVideo.load();
            mainVideo.play();

            // Listen for the video's "ended" event
            mainVideo.addEventListener('ended', function() {
                // Show the question section when the video ends
                videoQuestion.style.display = 'block';
            });

            // Close the question section if closeQuestion is true
            if (closeQuestion) {
                videoQuestion.style.display = 'none';
            }
        }

        function closeQuestion() {
            const videoQuestion = document.querySelector('#question-section');
            videoQuestion.style.display = 'none';
        }
		
// Function to close the ads banner
function closeFloatingAdsBanner() {
    const floatingAdsBanner = document.querySelector('.floating-ads-banner');
    floatingAdsBanner.style.display = 'none';

    // Set a flag to indicate that the banner has been displayed
    localStorage.setItem('adsBannerDisplayed', 'true');
}


		1
 function updateYear() {
        const year = new Date().getFullYear();
        const yearElement = document.querySelector('#currentYear');
        yearElement.textContent = year;
    }
	
	  const autoReplyMessages = [
        "Hello! How can I help you?",
        "Thank you for your message. Our team will get back to you shortly.",
        "Is there anything else you'd like to know?",
        "Feel free to ask any questions you have.",
    ];

    chatboxSend.addEventListener('click', () => {
        const message = chatboxInput.value.trim();
        if (message !== '') {
            const userMessageDiv = document.createElement('div');
            userMessageDiv.classList.add('chatbox-message');
            userMessageDiv.classList.add('user-message');
            userMessageDiv.textContent = message;
            chatboxMessages.appendChild(userMessageDiv);
            chatboxInput.value = '';

            // Simulate an automatic reply after a short delay
            setTimeout(() => {
                const autoReplyMessage = autoReplyMessages[Math.floor(Math.random() * autoReplyMessages.length)];
                const botMessageDiv = document.createElement('div');
                botMessageDiv.classList.add('chatbox-message');
                botMessageDiv.classList.add('bot-message');
                botMessageDiv.textContent = autoReplyMessage;
                chatboxMessages.appendChild(botMessageDiv);
            }, 1000); // Adjust the delay (in milliseconds) as needed
        }
    });




</script>
</body>
</html>
