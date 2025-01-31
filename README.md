<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>BUSH 🇺🇬 ♻️</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: Arial, sans-serif;
        }

   body {
            background-color: #111111; /* Dark Black */
            overflow-y: auto;
            color: white;
        }

  /* Top Navigation Bar - Dark Black */
        .top-nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 10px 20px;
            width: 100%;
            background-color: #111111; /* Dark Black */
            color: white;
            position: fixed;
            top: 0;
            left: 0;
            z-index: 1000;
        }

  .top-nav .left {
            display: flex;
            align-items: center;
        }

  .top-nav .left i {
            margin-right: 20px;
            font-size: 24px;
            cursor: pointer;
        }

  .top-nav .right {
            font-size: 18px;
            font-weight: bold;
        }

  /* Search Bar - Dark Black */
        .search-bar {
            padding: 10px 20px;
            width: 100%;
            background-color: #111111; /* Dark Black */
            position: fixed;
            top: 60px;
            left: 0;
            z-index: 1000;
        }

  .search-bar input {
            width: 100%;
            padding: 10px;
            border: none;
            border-radius: 5px;
            font-size: 16px;
            background-color: #333;
            color: white;
        }

  /* Category Navigation Bar - Dark Black */
        .category-nav {
            display: flex;
            overflow-x: auto;
            padding: 10px;
            background-color: #111111; /* Dark Black */
            white-space: nowrap;
            position: fixed;
            top: 110px;
            left: 0;
            width: 100%;
            z-index: 1000;
        }

  .category-item {
            color: white;
            padding: 10px 20px;
            margin-right: 10px;
            cursor: pointer;
            text-transform: uppercase;
            font-size: 14px;
            font-weight: bold;
        }

  .category-item.active {
            background-color: #333; /* Darker Black */
        }

  /* Video Grid Section */
        .video-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 10px;
            padding: 20px;
            width: 100%;
            margin-top: 160px;
            margin-bottom: 80px;
        }

  .video-item {
            background-color: #fff;
            border-radius: 12px;
            overflow: hidden;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
            cursor: pointer;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

  .video-item:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
        }

  .video-item video {
            width: 100%;
            height: 150px;
            object-fit: cover;
            display: block;
        }

  .video-item .info {
            padding: 10px;
        }

  .video-item .title {
            font-size: 14px;
            font-weight: bold;
            margin-bottom: 5px;
            color: #333;
        }

  .video-item .platform {
            font-size: 12px;
            color: #666;
        }

  /* Bottom Navigation Bar - Dark Black */
        .nav-bar {
            display: flex;
            justify-content: space-around;
            position: fixed;
            bottom: 0;
            width: 100%;
            background-color: #111111; /* Dark Black */
            padding: 10px 0;
            z-index: 1000;
        }

  .nav-item {
            color: white;
            text-align: center;
            cursor: pointer;
            text-transform: uppercase;
            font-size: 16px;
        }

  .nav-item i {
            font-size: 24px;
            margin-bottom: 5px;
        }

  .nav-item span {
            display: block;
            font-size: 14px;
            font-weight: bold;
        }

  .upload-item {
            background-color: white;
            color: #333;
            border-radius: 50%;
            width: 60px;
            height: 60px;
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 30px;
            margin-bottom: 10px;
            border: 2px solid #333;
        }

  .nav-item:hover {
            background-color: #333; /* Darker Black */
        }

   /* TikTok-Style Video Modal */
        .video-modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: black;
            z-index: 2000;
            overflow-y: auto;
        }

  .video-modal .video-container {
            width: 100%;
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            scroll-snap-type: y mandatory;
        }

  .video-modal video {
            width: 100%;
            height: 100%;
            object-fit: cover;
            scroll-snap-align: start;
        }

  .close-modal {
            position: fixed;
            top: 20px;
            right: 20px;
            color: white;
            font-size: 30px;
            cursor: pointer;
            z-index: 2001;
        }
    </style>
</head>
<body>
    <!-- Top Navigation Bar -->
    <div class="top-nav">
        <div class="left">
            <i class="fa fa-bell"></i>
            <i class="fa fa-search"></i>
        </div>
        <div class="right">
            <span>BUSH 🇺🇬 ♻️</span>
        </div>
    </div>
<!-- Search Bar -->
    <div class="search-bar">
        <input type="text" id="search-input" placeholder="Search videos..." oninput="filterVideos()">
    </div>
<!-- Category Navigation Bar -->
    <div class="category-nav">
        <div class="category-item active" data-category="all">All</div>
        <div class="category-item" data-category="travel">Travel</div>
        <div class="category-item" data-category="culture">Culture</div>
        <div class="category-item" data-category="sports">Sports</div>
        <div class="category-item" data-category="politics">Politics</div>
        <div class="category-item" data-category="music">Music</div>
        <div class="category-item" data-category="movies">Movies</div>
        <div class="category-item" data-category="agriculture">Agriculture</div>
        <div class="category-item" data-category="economics">Economics</div>
        <div class="category-item" data-category="construction">Construction</div>
    </div>
<!-- Video Grid Section -->
    <div class="video-grid" id="video-grid">
        <!-- Videos will be loaded here -->
    </div>
<!-- TikTok-Style Video Modal -->
    <div class="video-modal" id="tikTokModal">
        <span class="close-modal" onclick="closeTikTokModal()">&times;</span>
        <div class="video-container" id="videoContainer"></div>
    </div>
<!-- Bottom Navigation Bar -->
    <div class="nav-bar">
        <div class="nav-item">
            <i class="fa fa-home"></i>
            <span>Home</span>
        </div>
        <div class="nav-item">
            <i class="fa fa-fire"></i>
            <span>Viral</span>
        </div>
        <div class="nav-item upload-item">
            <i class="fa fa-upload"></i>
        </div>
        <div class="nav-item">
            <i class="fa fa-bell"></i>
            <span>Live</span>
        </div>
        <div class="nav-item">
            <i class="fa fa-user"></i>
            <span>Account</span>
        </div>
    </div>

  <script>
        let currentPage = 1;
        let isLoading = false;

        async function fetchArchiveVideos(query = '', page = 1) {
            const url = `https://archive.org/advancedsearch.php?q=${query}&fl[]=identifier,title,description,mediatype&rows=10&page=${page}&output=json`;
            try {
                const response = await fetch(url);
                const data = await response.json();
                const videos = data.response.docs;
                displayVideos(videos);
            } catch (error) {
                console.error("Error fetching Archive videos:", error);
            }
        }

        function displayVideos(videos) {
            const videoGrid = document.getElementById('video-grid');
            videos.forEach(video => {
                const videoItem = document.createElement('div');
                videoItem.className = 'video-item';
                videoItem.onclick = () => openTikTokModal(`https://archive.org/download/${video.identifier}/${video.identifier}.mp4`);

                const videoElement = document.createElement('video');
                videoElement.muted = true;
                videoElement.loop = true;
                videoElement.preload = 'metadata';
                videoElement.innerHTML = `
                    <source src="https://archive.org/download/${video.identifier}/${video.identifier}.mp4" type="video/mp4">
                    Your browser does not support the video tag.
                `;
                videoItem.appendChild(videoElement);

                const videoInfo = document.createElement('div');
                videoInfo.className = 'info';

                const videoTitle = document.createElement('div');
                videoTitle.className = 'title';
                videoTitle.textContent = video.title;
                videoInfo.appendChild(videoTitle);

                const platform = document.createElement('div');
                platform.className = 'platform';
                platform.textContent = "Archive.org";
                videoInfo.appendChild(platform);

                videoItem.appendChild(videoInfo);
                videoGrid.appendChild(videoItem);
            });
        }

        function openTikTokModal(videoSrc) {
            const modal = document.getElementById('tikTokModal');
            const videoContainer = document.getElementById('videoContainer');
            videoContainer.innerHTML = '';

            const videoElement = document.createElement('video');
            videoElement.src = videoSrc;
            videoElement.autoplay = true;
            videoElement.muted = true;
            videoElement.loop = true;
            videoElement.controls = false;
            videoElement.style.width = '100%';
            videoElement.style.height = '100%';
            videoElement.style.objectFit = 'cover';

            videoContainer.appendChild(videoElement);
            modal.style.display = 'block';
        }

        function closeTikTokModal() {
            const modal = document.getElementById('tikTokModal');
            modal.style.display = 'none';

            const videos = modal.querySelectorAll('video');
            videos.forEach(video => video.pause());
        }

        window.onload = () => {
            fetchArchiveVideos('Uganda', currentPage);

            // Infinite Scroll Event
            window.addEventListener('scroll', () => {
                const nearBottom = document.documentElement.scrollTop + window.innerHeight >= document.documentElement.scrollHeight - 100;
                if (nearBottom && !isLoading) {
                    isLoading = true;
                    currentPage++;
                    fetchArchiveVideos('Uganda', currentPage);
                    isLoading = false;
                }
            });
        };
    </script>
</body>
</html>
