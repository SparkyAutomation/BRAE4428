<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>BRAE 4428 | Agricultural Robotics</title>
    <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="bg-gray-50 text-gray-900 font-sans">

    <header class="bg-blue-900 text-white py-10 shadow-lg">
        <div class="container mx-auto px-6">
            <h1 class="text-4xl font-bold">BRAE 4428</h1>
            <p class="mt-2 text-blue-200 text-lg">Modern Robotics & Automation Modules</p>
        </div>
    </header>

    <main class="container mx-auto px-6 py-12">
        <div id="module-container" class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
            <p class="text-gray-500 animate-pulse">Loading course modules...</p>
        </div>
    </main>

    <script>
        // Configuration: Replace with your GitHub details
        const username = "YourGitHubUsername"; 
        const repo = "SparkyAutomation";
        const apiUrl = `https://api.github.com/repos/${username}/${repo}/contents/`;

        async function fetchModules() {
            try {
                const response = await fetch(apiUrl);
                const files = await response.json();
                const container = document.getElementById('module-container');
                container.innerHTML = ''; // Clear loading text

                // Filter for HTML files and exclude index.html
                const modules = files.filter(file => 
                    file.name.endsWith('.html') && 
                    file.name.toLowerCase() !== 'index.html'
                );

                modules.forEach(file => {
                    // Clean up name (e.g., "FourierSeries.html" -> "Fourier Series")
                    const displayName = file.name
                        .replace('.html', '')
                        .replace(/([A-Z])/g, ' $1')
                        .trim();

                    const card = `
                        <div class="bg-white rounded-xl shadow-md overflow-hidden hover:shadow-2xl transition-shadow duration-300 border border-gray-200">
                            <div class="p-6">
                                <div class="uppercase tracking-wide text-sm text-blue-600 font-semibold">Module</div>
                                <h2 class="block mt-1 text-xl leading-tight font-bold text-black">${displayName}</h2>
                                <p class="mt-2 text-gray-500">Interactive engineering demonstration for ${displayName}.</p>
                                <a href="${file.name}" class="mt-4 inline-block bg-blue-600 text-white px-4 py-2 rounded hover:bg-blue-700 transition-colors">
                                    View Module →
                                </a>
                            </div>
                        </div>
                    `;
                    container.innerHTML += card;
                });
            } catch (error) {
                console.error('Error fetching repo:', error);
                document.getElementById('module-container').innerHTML = '<p class="text-red-500">Failed to load modules.</p>';
            }
        }

        fetchModules();
    </script>
</body>
</html>
