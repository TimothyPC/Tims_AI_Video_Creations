
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Video Gallery with External Audio</title>
  <style>

   audio { display: none;}
    
    body {
    background-color: black;
      color: white; 
      font-family: Arial, serif;
      margin: 0;
      padding: 0;
      display: flex;
      flex-wrap: wrap;
      gap: 16px;
      justify-content: center;
    }
    .video-container {
    
     /* Round the edges */
      border-radius: 6px;
      max-width: 300px;
    }
    video, audio {
    
    /*Round the edges */
      border-radius: 6px;
      height: auto;
      width: 100%;
    }
    
/* Style titles */
    p {
      margin-top: 8px;
      font-size: 16px;
      text-align: center;
    }
    
  </style>
</head>
<body>
  <div id="videoGallery"></div>

  <script>
    // Array of video and optional audio sources
    const media = [
      { videoSrc: "333923407231242244.mp4", audioSrc: "tornado_sound_1.mp3", title: "Tornado" },
      { videoSrc: "333735085892505603.mp4", title: "Beyonce and Macaulay Culkin" },
      { videoSrc: "333628961587437568.mp4", title: "Beyonce and Michael Jackson" },

{ videoSrc: "333608505539035140.mp4", title: "Beyonce Smoking" },

{ videoSrc: "333606574510817289.mp4", title: "Beyonce and Blue Earrings" },

{ videoSrc: "333594070342651905.mp4", title: "Beyonce and Mud" },
    
{ videoSrc: "332834079352217606.mp4", audioSrc: "The_Street_Beat_3.mp3", title: "Teddy Bears Rock" },

{ videoSrc: "Videos/Children_enjoy_Christmas.mp4", title: "Children Enjoy Christmas" },


{ videoSrc: "Videos/Friends_all_enjoy.mp4", title: "Friends All Enjoy" },


{ videoSrc: "Videos/Juanita_child.mp4", title: "Aunt And Child" },


{ videoSrc: "Videos/LizandMary.mp4", title: "Liz and Mary" },


{ videoSrc: "Videos/Mattie_child.mp4", title: "Aunt Mattie And Child" },


{ videoSrc: "Videos/MomsHair.mp4", title: "Moms Hair in Wind" },


{ videoSrc: "Videos/Superman_Batman_workout.mp4", title: "Superman Batman Workout" },


{ videoSrc: "Videos/brother_saulutes.mp4", title: "Brother Salutes" },


{ videoSrc: "Videos/car_green_tarp.mp4", title: "Car And Green Tarp" },


{ videoSrc: "Videos/carblowsmoke.mp4", title: "Car Blow Smoke" },


{ videoSrc: "Videos/carverboys.mp4", title: "Carver Boys" },

{ videoSrc: "Videos/deonsanders.mp4", title: "Deon Sanders" },


{ videoSrc: "Videos/momanddad.mp4", title: "Mom And Dad" },


{ videoSrc: "Videos/momanddaughters.mp4", title: "Mom And Daughters" },


{ videoSrc: "Videos/momandellis.mp4", title: "Mom And Ellis" },
      
{ videoSrc: "Videos/newyears_celebration.mp4", title: "New Years Celebration" }, 
      

{ videoSrc: "Videos/olderbrother.mp4", title: "Older Brother" },


{ videoSrc: "Videos/oldtimecar.mp4", title: "Old Time Car" },


{ videoSrc: "Videos/red_car_on_yellow.mp4", title: "Red Car on Slide" },


{ videoSrc: "Videos/sister_reads.mp4", title: "Sister Reads" },


{ videoSrc: "Videos/thecross.mp4", title: "The Cross" },


{ videoSrc: "Videos/titus.mp4", title: "Soldier at Ease" },
      
    ];

    // Reference to the video gallery container
    const videoGallery = document.getElementById("videoGallery");

    // Create video and audio elements dynamically
    media.forEach(item => {
      const container = document.createElement("div");
      container.classList.add("video-container");

      const videoElement = document.createElement("video");
      videoElement.src = item.videoSrc;
      videoElement.controls = true;

      const title = document.createElement("p");
      title.textContent = item.title;

      container.appendChild(videoElement);
      container.appendChild(title);

      // If there's an associated audio file, create an audio element
      if (item.audioSrc) {
        const audioElement = document.createElement("audio");
        audioElement.src = item.audioSrc;

        // Synchronize audio with the video
        videoElement.addEventListener("play", () => {
          audioElement.play();
        });

        videoElement.addEventListener("pause", () => {
          audioElement.pause();
        });

       videoElement.addEventListener("ended", () => {
    audioElement.pause();
    audioElement.currentTime = 0;
  });
        

        audioElement.controls = true; // Optional: Add controls for the audio
        container.appendChild(audioElement);
      }

      videoGallery.appendChild(container);
    });
  </script>
  
</body>
</html>


      
     





















   

