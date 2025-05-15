<!-- index.html -->
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Learning Management System</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: Arial, sans-serif;
             background-color: #e6e6fa; /* Clean white background */
            color:  #9370DB; /* Light blue font color */
        }

        .sidebar {
            width: 250px;
            height: 100vh;
            background-color: #e6e6fa;
            position: fixed;
            left: 0;
            top: 0;
            padding: 20px;
            overflow-y: auto;
        }

        .lesson-list {
            list-style: none;
        }

        .lesson-item {
            padding: 10px;
            margin: 5px 0;
            background-color: #e0f7fa;
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.3s;
        }

        .lesson-item:hover {
            background-color: #e0f7fa;
        }

        .main-content {
            margin-left: 250px;
            padding: 20px;
        }

        .lesson-content {
            background-color: #fff;
            padding: 20px;
            border-radius: 5px;
            box-shadow: 0 0 10px rgba(0,0,0,0.1);
        }
    </style>
</head>
<body>
    <div class="sidebar">
        
        <ul class="lesson-list" id="lessonList">
            <!-- Lessons will be added here dynamically -->
        </ul>
    </div>

    <div class="main-content">
        <div class="lesson-content" id="lessonContent">
            <h1>Mga Aralin sa Asignaturang Filipino sa Larang ng Iba't-ibang Disipilina</h1>
            
        </div>
    </div>

    <script>
        // Sample lesson data
        const lessons = [
            {
                id: 1,
                title: "Home",
                content: '<img src="https://assets.onecompiler.app/43hsvrazv/43hsr8xn9/HOME.png" alt="Welcome Image" width="500">'
            },
            {    
                id: 2,
                title: "Aralin 1: Introduction",
                content: "This is the content for Lesson 1..."
            },
            {
                id: 3,
                title: "Lesson 2: Basic Concepts",
                content: "This is the content for Lesson 2..."
            },
            {  
                
                id: 4,
                title: "About",
                content: "Ang website na ito ay inilaan para sa mga mag-aaral na kinakailangan basahin ang mga aralin sa asignaturang Filipino sa Larang ng iba't-ibang Disiplina"
          
            }
        ];

        // Function to display lessons in sidebar
        function displayLessons() {
            const lessonList = document.getElementById('lessonList');
            lessons.forEach(lesson => {
                const li = document.createElement('li');
                li.className = 'lesson-item';
                li.textContent = lesson.title;
                li.onclick = () => showLessonContent(lesson);
                lessonList.appendChild(li);
            });
        }

        // Function to show lesson content
        function showLessonContent(lesson) {
            const contentDiv = document.getElementById('lessonContent');
            contentDiv.innerHTML = `
                <h1>${lesson.title}</h1>
                <div>${lesson.content}</div>
            `;
        }

        // Initialize the page
        displayLessons();
    </script>
</body>
</html>
