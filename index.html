<script type="text/javascript">
        var gk_isXlsx = false;
        var gk_xlsxFileLookup = {};
        var gk_fileData = {};
        function filledCell(cell) {
          return cell !== '' && cell != null;
        }
        function loadFileData(filename) {
        if (gk_isXlsx && gk_xlsxFileLookup[filename]) {
            try {
                var workbook = XLSX.read(gk_fileData[filename], { type: 'base64' });
                var firstSheetName = workbook.SheetNames[0];
                var worksheet = workbook.Sheets[firstSheetName];

                // Convert sheet to JSON to filter blank rows
                var jsonData = XLSX.utils.sheet_to_json(worksheet, { header: 1, blankrows: false, defval: '' });
                // Filter out blank rows (rows where all cells are empty, null, or undefined)
                var filteredData = jsonData.filter(row => row.some(filledCell));

                // Heuristic to find the header row by ignoring rows with fewer filled cells than the next row
                var headerRowIndex = filteredData.findIndex((row, index) =>
                  row.filter(filledCell).length >= filteredData[index + 1]?.filter(filledCell).length
                );
                // Fallback
                if (headerRowIndex === -1 || headerRowIndex > 25) {
                  headerRowIndex = 0;
                }

                // Convert filtered JSON back to CSV
                var csv = XLSX.utils.aoa_to_sheet(filteredData.slice(headerRowIndex)); // Create a new sheet from filtered array of arrays
                csv = XLSX.utils.sheet_to_csv(csv, { header: 1 });
                return csv;
            } catch (e) {
                console.error(e);
                return "";
            }
        }
        return gk_fileData[filename] || "";
        }
        </script><!DOCTYPE html>
<html lang="en" dir="ltr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>DoxaCare AI - Healthcare Assistant for Sierra Leone</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap');
    
    body {
      font-family: 'Poppins', sans-serif;
      background-color: #f0fdf4;
    }
    
    .typing-indicator::after {
      content: '...';
      animation: typing 1.5s infinite;
    }
    
    @keyframes typing {
      0% { content: '.'; }
      33% { content: '..'; }
      66% { content: '...'; }
    }
    
    .translate-btn {
      transition: all 0.3s ease;
    }
    
    .translate-btn:hover {
      transform: scale(1.05);
    }
    
    .emergency-shake {
      animation: shake 0.5s cubic-bezier(.36,.07,.19,.97) both;
    }
    
    @keyframes shake {
      10%, 90% { transform: translate3d(-1px, 0, 0); }
      20%, 80% { transform: translate3d(2px, 0, 0); }
      30%, 50%, 70% { transform: translate3d(-4px, 0, 0); }
      40%, 60% { transform: translate3d(4px, 0, 0); }
    }
    /* Custom styles for the modal overlay */
    .modal-overlay {
        background-color: rgba(0, 0, 0, 0.5);
    }
    /* Custom styles for scrollbar in comments section */
    .max-h-48::-webkit-scrollbar {
        width: 8px;
    }
    .max-h-48::-webkit-scrollbar-track {
        background: #f1f1f1;
        border-radius: 10px;
    }
    .max-h-48::-webkit-scrollbar-thumb {
        background: #cbd5e1; /* gray-300 */
        border-radius: 10px;
    }
    .max-h-48::-webkit-scrollbar-thumb:hover {
        background: #94a3b8; /* gray-400 */
    }
    /* Custom styles for iframe maps */
    .map-iframe {
        width: 100%;
        height: 200px;
        border: none;
        border-radius: 8px;
        margin-top: 8px;
    }
  </style>
</head>
<body class="min-h-screen flex flex-col">
  <div id="auth-root"></div>
  <div id="app-content">
  <!-- Header -->
  <header class="bg-gradient-to-r from-green-600 to-yellow-400 shadow-md">
    <div class="container mx-auto px-4 py-3 flex items-center justify-between">
      <div class="flex items-center space-x-2">
        <i class="fas fa-heartbeat text-white text-2xl"></i>
        <h1 class="text-white font-bold text-xl md:text-2xl">DoxaCare AI</h1>
      </div>
      <div class="flex items-center space-x-4">
        <button id="languageToggle" class="bg-white text-green-800 px-3 py-1 rounded-full text-sm font-medium flex items-center translate-btn">
          <span id="currentLanguage">Krio</span>
          <i class="fas fa-exchange-alt ml-1"></i>
        </button>
        <button id="emergencyBtn" class="bg-red-600 text-white px-3 py-1 rounded-full text-sm font-medium flex items-center hover:bg-red-700 emergency-shake">
          <i class="fas fa-exclamation-triangle mr-1"></i>
          Emergency
        </button>
        <!-- Account Menu Button -->
        <div class="relative">
            <button id="accountMenuBtn" class="bg-white text-green-800 px-3 py-1 rounded-full text-sm font-medium flex items-center translate-btn">
                <i class="fas fa-user-circle mr-1"></i>
                <span id="accountStatusText">Account</span>
            </button>
            <!-- Account Dropdown/Modal Trigger -->
            <div id="accountDropdown" class="absolute right-0 mt-2 w-48 bg-white rounded-md shadow-lg py-1 z-20 hidden">
                <a href="#" id="signInOption" class="block px-4 py-2 text-sm text-gray-700 hover:bg-gray-100">Sign In / Sign Up</a>
                <a href="#" id="signOutOption" class="block px-4 py-2 text-sm text-red-700 hover:bg-gray-100 hidden">Sign Out</a>
            </div>
        </div>
      </div>
    </div>
  </header>
  <!-- Nav Tabs -->
  <div class="bg-white shadow-sm">
    <div class="container mx-auto px-4">
      <div class="flex overflow-x-auto">
        <button class="tab-btn active px-4 py-3 text-green-700 font-medium border-b-2 border-green-700 whitespace-nowrap" data-tab="home">
          <i class="fas fa-home mr-2"></i>Home
        </button>
        <button class="tab-btn px-4 py-3 text-gray-600 font-medium whitespace-nowrap" data-tab="symptoms">
          <i class="fas fa-notes-medical mr-2"></i>Health Topics
        </button>
        <button class="tab-btn px-4 py-3 text-gray-600 font-medium whitespace-nowrap" data-tab="advice">
          <i class="fas fa-lightbulb mr-2"></i>Health Advice
        </button>
        <button class="tab-btn px-4 py-3 text-gray-600 font-medium whitespace-nowrap" data-tab="clinics">
          <i class="fas fa-hospital mr-2"></i>Find Clinics
        </button>
        <button class="tab-btn px-4 py-3 text-gray-600 font-medium whitespace-nowrap" data-tab="account">
          <i class="fas fa-user mr-2"></i>Account
        </button>
      </div>
    </div>
  </div>
  <!-- Main Content -->
  <main class="flex-grow container mx-auto px-4 py-6">
    <!-- Home Tab (default visible) -->
    <div id="home-tab" class="tab-content active">
      <div class="bg-white rounded-lg shadow-md overflow-hidden mb-6">
        <div class="bg-green-100 p-4 border-b border-green-200">
          <h2 class="text-green-800 font-bold text-lg">Welcome to DoxaCare AI</h2>
          <p id="welcomeText" class="text-gray-700 text-sm mt-1">Your trusted healthcare assistant for Sierra Leone. Ask about symptoms, get health advice, or find nearby clinics.</p>
          <p id="welcomeTextKrio" class="text-gray-700 text-sm mt-1 hidden">DoxaCare AI wey dey for you pan Salone health. Ask about sick wey you get, take health advice, or find clinic close to you.</p>
        </div>
        <div class="p-4">
          <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
            <div class="bg-yellow-50 border border-yellow-200 rounded-lg p-4">
              <h3 class="font-bold text-yellow-800 mb-2 flex items-center">
                <i class="fas fa-bell text-yellow-600 mr-2"></i>
                <span id="healthAlertsTitle">Health Alerts</span>
              </h3>
              <div class="text-sm text-gray-700">
                <div id="healthAlertsText">
                  <p>• Monkeypox outbreak spreading nationwide (May 2025)</p>
                  <p>• Avoid contact with wild animals</p>
                  <p>• Isolate if rash/fever develops</p>
                </div>
                <div id="healthAlertsTextKrio" class="hidden">
                  <p>• Monkeypox dey spread for all Salone (May 2025)</p>
                  <p>• No touch bush meat or wild animal</p>
                  <p>• Stay for house if you get rash or fever</p>
                </div>
              </div>
            </div>
            <div class="bg-blue-50 border border-blue-200 rounded-lg p-4">
              <h3 class="font-bold text-blue-800 mb-2 flex items-center">
                <i class="fas fa-map-marker-alt text-blue-600 mr-2"></i>
                <span id="quickLinksTitle">Quick Chats</span>
              </h3>
              <div class="grid grid-cols-2 gap-2">
                <button class="quick-action-btn bg-green-100 text-green-800" data-action="malaria">
                  <i class="fas fa-bug mr-1"></i>
                  <span id="malariaBtnText">Malaria</span>
                </button>
                <button class="quick-action-btn bg-yellow-100 text-yellow-800" data-action="pregnancy">
                  <i class="fas fa-baby mr-1"></i>
                  <span id="pregnancyBtnText">Pregnancy</span>
                </button>
                <button class="quick-action-btn bg-red-100 text-red-800" data-action="diarrhea">
                  <i class="fas fa-tint mr-1"></i>
                  <span id="diarrheaBtnText">Diarrhea</span>
                </button>
                <button class="quick-action-btn bg-purple-100 text-purple-800" data-action="hypertension">
                  <i class="fas fa-heartbeat mr-1"></i>
                  <span id="hypertensionBtnText">Hypertension</span>
                </button>
              </div>
            </div>
          </div>
        </div>
      </div>
      <!-- Chat Interface -->
      <div class="bg-white rounded-lg shadow-md overflow-hidden">
        <div class="bg-green-600 p-3">
          <h2 class="text-white font-bold flex items-center">
            <i class="fas fa-comments mr-2"></i>
            <span id="chatTitle">Chat with DoxaCare AI</span>
          </h2>
        </div>
        <div id="chatWindow" class="h-64 overflow-y-auto p-4 bg-gray-50">
          <div class="chat-message bot-message mb-3">
            <div class="bg-white p-3 rounded-lg shadow-sm max-w-3/4 inline-block">
              <p id="welcomeChatText">Hello! How can I assist you with your health today? You can describe symptoms, ask for advice, or find clinics near you.</p>
              <p id="welcomeChatTextKrio" class="hidden">How you dey? Wetin I fit do for you health today? You fit talk about sick wey you get, ask for advice, or find clinic close to you.</p>
              <div class="quick-reply-buttons mt-2 flex flex-wrap gap-2">
                <button class="quick-reply-btn bg-green-100 text-green-800 text-sm px-3 py-1 rounded-full">I have fever</button>
                <button class="quick-reply-btn bg-green-100 text-green-800 text-sm px-3 py-1 rounded-full">Mosquito bite advice</button>
                <button class="quick-reply-btn bg-green-100 text-green-800 text-sm px-3 py-1 rounded-full">Find clinic near me</button>
              </div>
            </div>
          </div>
        </div>
        <div class="p-3 bg-gray-100 border-t border-gray-200">
          <div class="flex items-center">
            <input type="text" id="userInput" placeholder="Type your health question here..." class="flex-grow px-4 py-2 rounded-full border border-gray-300 focus:outline-none focus:ring-2 focus:ring-green-500 focus:border-transparent">
            <button id="sendBtn" class="ml-2 bg-green-600 text-white p-2 rounded-full hover:bg-green-700 transition-colors">
              <i class="fas fa-paper-plane"></i>
            </button>
          </div>
        </div>
      </div>
      <!-- Cultural Feature Section -->
      <div class="mt-6 bg-white rounded-lg shadow-md overflow-hidden">
        <div class="bg-gradient-to-r from-yellow-400 to-green-600 p-3">
          <h2 class="text-white font-bold flex items-center">
            <i class="fas fa-globe-africa mr-2"></i>
            <span id="culturalTitle">Cultural Health Tips</span>
          </h2>
        </div>
        <div class="p-4">
          <div class="flex flex-col md:flex-row items-center">
            <img src="https://images.app.goo.gl/6DwoTn2NgUnF7Di77" alt="Lumley Beach in Freetown, Sierra Leone" class="w-32 h-32 md:w-48 md:h-48 object-cover rounded-lg shadow mb-4 md:mb-0 md:mr-4">
            <div>
              <h3 class="font-semibold text-green-800 mb-2" id="localTipTitle">Local Health Wisdom</h3>
              <div id="culturalTipText" class="text-gray-700">
                <p>• Boil water for drinking to prevent waterborne diseases.</p>
                <p>• Use insecticide-treated nets (ITNs) every night during rainy season.</p>
                <p>• Sun-dry clothes thoroughly to kill germs.</p>
              </div>
              <div id="culturalTipTextKrio" class="text-gray-700 hidden">
                <p>• Make water hot well-well before you drink am to stop water sickness.</p>
                <p>• Use net wey get medicine for kill mosquito every night when rain dey fall.</p>
                <p>• Make sun dry your clothes proper to kill all germ.</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
        
    <!-- Symptom Checker Tab -->
    <div id="symptoms-tab" class="tab-content hidden">
      <div class="bg-white rounded-lg shadow-md overflow-hidden">
        <div class="bg-blue-600 p-3 flex justify-between items-center">
          <h2 class="text-white font-bold flex items-center">
            <i class="fas fa-notes-medical mr-2"></i>
            <span>Health Topics</span>
          </h2>
          <button id="refreshHealthTopics" class="text-white hover:text-blue-200 transition-colors" title="Refresh health topics">
            <i class="fas fa-sync-alt"></i>
          </button>
        </div>
        <div class="p-4">
          <div id="symptomInputArea" class="mb-4">
            <label for="symptomsInput" class="block text-gray-700 mb-2">Ask about any health topic:</label>
            <div class="flex">
              <input type="text" id="symptomsInput" class="flex-grow px-4 py-2 rounded-l-lg border border-gray-300 focus:outline-none focus:ring-2 focus:ring-blue-500 focus:border-transparent" placeholder="e.g. fever, exercise tips, nutrition advice">
              <button id="checkSymptomsBtn" class="bg-blue-600 text-white px-4 py-2 rounded-r-lg hover:bg-blue-700">Ask</button>
            </div>
          </div>
          <div id="symptomResults" class="hidden border-t pt-4">
            <!-- Results will be inserted here by JavaScript -->
          </div>
          <div class="mt-4 p-3 bg-gray-100 rounded-lg">
            <h4 class="font-medium text-gray-700 mb-2">Common Health Topics:</h4>
            <div class="grid grid-cols-2 gap-2">
              <button class="symptom-tag bg-white border border-blue-200 text-blue-700 px-3 py-1 rounded text-sm" data-symptoms="Malaria">Malaria</button>
              <button class="symptom-tag bg-white border border-blue-200 text-blue-700 px-3 py-1 rounded text-sm" data-symptoms="Typhoid">Typhoid</button>
              <button class="symptom-tag bg-white border border-blue-200 text-blue-700 px-3 py-1 rounded text-sm" data-symptoms="Cholera">Cholera</button>
              <button class="symptom-tag bg-white border border-blue-200 text-blue-700 px-3 py-1 rounded text-sm" data-symptoms="Dengue">Dengue</button>
              <button class="symptom-tag bg-white border border-blue-200 text-blue-700 px-3 py-1 rounded text-sm" data-symptoms="Pneumonia">Pneumonia</button>
              <button class="symptom-tag bg-white border border-blue-200 text-blue-700 px-3 py-1 rounded text-sm" data-symptoms="Meningitis">Meningitis</button>
              <button class="symptom-tag bg-white border border-blue-200 text-blue-700 px-3 py-1 rounded text-sm" data-symptoms="Lassa Fever">Lassa Fever</button>
              <button class="symptom-tag bg-white border border-blue-200 text-blue-700 px-3 py-1 rounded text-sm" data-symptoms="COVID-19">COVID-19</button>
            </div>
          </div>
          <div class="mt-4 p-3 bg-gray-100 rounded-lg">
            <h4 class="font-medium text-gray-700 mb-2">Common Symptoms:</h4>
            <div class="flex flex-wrap gap-2">
              <button class="symptom-tag bg-white border border-blue-200 text-blue-700 px-3 py-1 rounded-full text-sm">Fever</button>
              <button class="symptom-tag bg-white border border-blue-200 text-blue-700 px-3 py-1 rounded-full text-sm">Exercise</button>
              <button class="symptom-tag bg-white border border-blue-200 text-blue-700 px-3 py-1 rounded-full text-sm">Nutrition</button>
              <button class="symptom-tag bg-white border border-blue-200 text-blue-700 px-3 py-1 rounded-full text-sm">Pregnancy</button>
              <button class="symptom-tag bg-white border border-blue-200 text-blue-700 px-3 py-1 rounded-full text-sm">Diabetes</button>
              <button class="symptom-tag bg-white border border-blue-200 text-blue-700 px-3 py-1 rounded-full text-sm">Mental Health</button>
            </div>
          </div>
        </div>
      </div>
    </div>
        
    <!-- Health Advice Forum Tab -->
    <div id="advice-tab" class="tab-content hidden">
      <div class="max-w-3xl w-full bg-white rounded-lg shadow-md overflow-hidden">
        <div class="bg-purple-600 p-3 flex justify-between items-center rounded-t-lg">
          <h2 class="text-white font-bold flex items-center text-xl">
            <i class="fas fa-comments mr-2"></i>
            Community Health Forum
          </h2>
          <button onclick="showNewPostModal()" class="bg-white text-purple-600 px-3 py-1 rounded-full text-sm font-medium hover:bg-purple-100 transition-colors shadow-sm">
            <i class="fas fa-plus mr-1"></i> New Post
          </button>
        </div>
        <div id="postsContainer" class="p-4 space-y-4">
          <!-- Static Post 1 -->
          <div class="border border-gray-200 rounded-lg p-4 bg-gray-50 shadow-sm">
            <h4 class="font-semibold text-purple-700 text-lg mb-2">Tips for Preventing Malaria</h4>
            <p class="text-gray-700 text-base mb-3">Using mosquito nets every night has really helped my family avoid malaria. Also, clearing stagnant water around the house reduces mosquito breeding.</p>
            <div class="flex items-center text-xs text-gray-500 mb-4">
              <div class="bg-gray-200 border-2 border-dashed rounded-full w-6 h-6 mr-2 flex items-center justify-center overflow-hidden">
                <i class="fas fa-user text-gray-400 text-sm"></i>
              </div>
              <span>By Anonymous User</span>
              <span class="mx-2">•</span>
              <span>Freetown</span>
              <span class="mx-2">•</span>
              <span>Jul 15, 2025, 10:30 AM</span>
            </div>
            <div class="mt-4 border-t border-gray-200 pt-4">
              <h5 class="font-medium text-gray-800 mb-3 flex items-center">
                <i class="fas fa-comment-dots mr-2 text-blue-500"></i>
                Comments (<span id="commentCount-post1">1</span>)
              </h5>
              <div id="commentsList-post1" class="space-y-3 mb-4 max-h-48 overflow-y-auto pr-2">
                <div class="bg-white border border-gray-100 rounded-lg p-3 shadow-xs">
                  <p class="text-gray-700 text-sm mb-1">Great tip! I also use insect repellent in the evenings.</p>
                  <div class="flex items-center text-xs text-gray-500">
                    <div class="bg-gray-200 border-2 border-dashed rounded-full w-5 h-5 mr-1 flex items-center justify-center overflow-hidden">
                      <i class="fas fa-reply text-gray-400 text-xs"></i>
                    </div>
                    <span>By Community Member</span>
                    <span class="mx-1">•</span>
                    <span>Jul 15, 2025, 11:00 AM</span>
                  </div>
                </div>
              </div>
              <div class="flex items-center mt-2">
                <input type="text" id="commentInput-post1" class="flex-grow px-3 py-2 rounded-l-lg border border-gray-300 focus:outline-none focus:ring-2 focus:ring-purple-500 focus:border-transparent text-sm" placeholder="Add a comment..." data-post-id="post1">
                <button onclick="addComment('post1')" class="bg-purple-500 text-white p-2 rounded-r-lg hover:bg-purple-600 transition-colors shadow-sm">
                  <i class="fas fa-paper-plane"></i>
                </button>
              </div>
            </div>
          </div>
          <!-- Static Post 2 -->
          <div class="border border-gray-200 rounded-lg p-4 bg-gray-50 shadow-sm">
            <h4 class="font-semibold text-purple-700 text-lg mb-2">Managing High Blood Pressure</h4>
            <p class="text-gray-700 text-base mb-3">Reducing salt intake and walking daily has helped me control my blood pressure. Any other suggestions?</p>
            <div class="flex items-center text-xs text-gray-500 mb-4">
              <div class="bg-gray-200 border-2 border-dashed rounded-full w-6 h-6 mr-2 flex items-center justify-center overflow-hidden">
                <i class="fas fa-user text-gray-400 text-sm"></i>
              </div>
              <span>By Anonymous User</span>
              <span class="mx-2">•</span>
              <span>Bo</span>
              <span class="mx-2">•</span>
              <span>Jul 10, 2025, 09:00 AM</span>
            </div>
            <div class="mt-4 border-t border-gray-200 pt-4">
              <h5 class="font-medium text-gray-800 mb-3 flex items-center">
                <i class="fas fa-comment-dots mr-2 text-blue-500"></i>
                Comments (<span id="commentCount-post2">0</span>)
              </h5>
              <div id="commentsList-post2" class="space-y-3 mb-4 max-h-48 overflow-y-auto pr-2"></div>
              <p id="noCommentsMessage-post2" class="text-sm text-gray-600 italic mb-3">No comments yet. Be the first to reply!</p>
              <div class="flex items-center mt-2">
                <input type="text" id="commentInput-post2" class="flex-grow px-3 py-2 rounded-l-lg border border-gray-300 focus:outline-none focus:ring-2 focus:ring-purple-500 focus:border-transparent text-sm" placeholder="Add a comment..." data-post-id="post2">
                <button onclick="addComment('post2')" class="bg-purple-500 text-white p-2 rounded-r-lg hover:bg-purple-600 transition-colors shadow-sm">
                  <i class="fas fa-paper-plane"></i>
                </button>
              </div>
            </div>
          </div>
          <!-- No Posts Message -->
          <div id="noPostsMessage" class="bg-gray-50 border border-gray-200 rounded-lg p-6 text-center text-gray-600 hidden">
            <i class="fas fa-exclamation-circle text-gray-400 text-3xl mb-3"></i>
            <p class="font-medium text-lg mb-2">No posts yet!</p>
            <p class="mb-4">Be the first to share a health question or advice with the community.</p>
            <button onclick="showNewPostModal()" class="bg-purple-500 hover:bg-purple-600 text-white font-medium py-2 px-4 rounded-lg transition-colors shadow-md">
              Start a New Discussion
            </button>
          </div>
        </div>
        <!-- New Post Modal -->
        <div id="newPostModal" class="fixed inset-0 modal-overlay flex items-center justify-center z-50 p-4 hidden">
          <div class="bg-white rounded-lg shadow-xl max-w-lg w-full p-6 transform transition-all duration-300 scale-95 opacity-0" id="newPostModalContent">
            <div class="flex justify-between items-center mb-4">
              <h3 class="text-xl font-bold text-purple-700">Create New Post</h3>
              <button onclick="hideNewPostModal()" class="text-gray-500 hover:text-gray-700">
                <i class="fas fa-times text-lg"></i>
              </button>
            </div>
            <div class="mb-4">
              <label for="postTitle" class="block text-gray-700 text-sm font-medium mb-2">Title:</label>
              <input type="text" id="postTitle" class="w-full px-3 py-2 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-purple-500 focus:border-transparent" placeholder="Enter post title">
            </div>
            <div class="mb-4">
              <label for="postCity" class="block text-gray-700 text-sm font-medium mb-2">City/Town:</label>
              <input type="text" id="postCity" class="w-full px-3 py-2 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-purple-500 focus:border-transparent" placeholder="e.g., Freetown, Bo">
            </div>
            <div class="mb-6">
              <label for="postContent" class="block text-gray-700 text-sm font-medium mb-2">Content:</label>
              <textarea id="postContent" rows="5" class="w-full px-3 py-2 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-purple-500 focus:border-transparent resize-y" placeholder="Share your health question or advice..."></textarea>
            </div>
            <div class="flex justify-end space-x-3">
              <button onclick="hideNewPostModal()" class="bg-gray-200 text-gray-700 px-4 py-2 rounded-lg hover:bg-gray-300 transition-colors shadow-sm">Cancel</button>
              <button onclick="addPost()" class="bg-purple-600 text-white px-4 py-2 rounded-lg hover:bg-purple-700 transition-colors shadow-md">Submit Post</button>
            </div>
          </div>
        </div>
        <!-- Custom Alert Modal -->
        <div id="customAlertModal" class="fixed inset-0 modal-overlay flex items-center justify-center z-50 p-4 hidden">
          <div class="bg-white rounded-lg shadow-xl max-w-sm w-full p-6 transform transition-all duration-300 scale-95 opacity-0" id="customAlertModalContent">
            <div class="flex justify-between items-center mb-4">
              <h3 class="text-xl font-bold text-red-700" id="alertTitle">Alert</h3>
              <button onclick="hideAlert()" class="text-gray-500 hover:text-gray-700">
                <i class="fas fa-times text-lg"></i>
              </button>
            </div>
            <p id="alertMessage" class="text-gray-700 mb-6"></p>
            <div class="flex justify-end">
              <button onclick="hideAlert()" class="bg-red-600 text-white px-4 py-2 rounded-lg hover:bg-red-700 transition-colors shadow-md">OK</button>
            </div>
          </div>
        </div>
      </div>
    </div>
        
    <!-- Find Clinics Tab -->
    <div id="clinics-tab" class="tab-content hidden">
      <div class="bg-white rounded-lg shadow-md overflow-hidden">
        <div class="bg-red-600 p-3">
          <h2 class="text-white font-bold flex items-center">
            <i class="fas fa-hospital mr-2"></i>
            <span>Find Clinics</span>
          </h2>
        </div>
        <div class="p-4">
          <div class="mb-4">
            <label for="locationInput" class="block text-gray-700 mb-2">Enter your location (district or city):</label>
            <div class="flex">
              <input type="text" id="locationInput" class="flex-grow px-4 py-2 rounded-l-lg border border-gray-300 focus:outline-none focus:ring-2 focus:ring-red-500 focus:border-transparent" placeholder="e.g. Freetown, Bo, Kenema">
              <button id="findClinicsBtn" class="bg-red-600 text-white px-4 py-2 rounded-r-lg hover:bg-red-700">Search</button>
            </div>
          </div>
          <div id="clinicResults" class="space-y-4">
            <!-- Clinic cards will be dynamically inserted here by JavaScript -->
          </div>
        </div>
      </div>
    </div>
    
    <!-- Account Tab -->
    <div id="account-tab" class="tab-content hidden">
      <div class="max-w-md mx-auto bg-white rounded-lg shadow-md overflow-hidden">
        <!-- Account Content (Sign In/Sign Up Forms) -->
        <div id="account-content" class="p-6">
          <h2 class="text-2xl font-bold text-gray-800 mb-6 text-center" id="accountFormTitle">Sign In / Sign Up</h2>
          
          <!-- Social Login Options -->
          <div class="space-y-3 mb-6">
            <button id="googleSignInBtn" class="w-full bg-red-500 text-white py-2 px-4 rounded-lg flex items-center justify-center hover:bg-red-600 transition-colors shadow-md">
              <i class="fab fa-google mr-2"></i> Sign in with Google
            </button>
            <button id="facebookSignInBtn" class="w-full bg-blue-600 text-white py-2 px-4 rounded-lg flex items-center justify-center hover:bg-blue-700 transition-colors shadow-md">
              <i class="fab fa-facebook-f mr-2"></i> Sign in with Facebook
            </button>
          </div>
          <div class="relative flex py-5 items-center">
            <div class="flex-grow border-t border-gray-300"></div>
            <span class="flex-shrink mx-4 text-gray-500">Or</span>
            <div class="flex-grow border-t border-gray-300"></div>
          </div>

          <!-- Sign Up Form (always visible for anonymous users to fill profile) -->
          <form id="signUpForm" class="space-y-4">
            <div>
              <label for="firstName" class="block text-gray-700 text-sm font-medium mb-1">First Name:</label>
              <input type="text" id="firstName" class="w-full px-3 py-2 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-green-500" placeholder="Your first name">
            </div>
            <div>
              <label for="lastName" class="block text-gray-700 text-sm font-medium mb-1">Last Name:</label>
              <input type="text" id="lastName" class="w-full px-3 py-2 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-green-500" placeholder="Your last name">
            </div>
            <div>
              <label for="phone" class="block text-gray-700 text-sm font-medium mb-1">Phone Number:</label>
              <input type="tel" id="phone" class="w-full px-3 py-2 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-green-500" placeholder="e.g., +23276123456">
            </div>
            <div>
              <label for="username" class="block text-gray-700 text-sm font-medium mb-1">Username:</label>
              <input type="text" id="username" class="w-full px-3 py-2 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-green-500" placeholder="Choose a username">
            </div>
            <button type="submit" class="w-full bg-green-600 text-white py-2 px-4 rounded-lg hover:bg-green-700 transition-colors shadow-md">
              Complete Profile
            </button>
          </form>
          <p id="authMessage" class="mt-4 text-center text-sm text-red-600"></p>
        </div>
      </div>
    </div>
  </main>

  <!-- Footer -->
  <footer class="bg-green-800 text-white py-6">
    <div class="container mx-auto px-4">
      <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
        <div>
          <h3 class="font-bold mb-3">DoxaCare AI</h3>
          <p class="text-sm">Providing trusted healthcare advice for Sierra Leone</p>
          <div class="mt-3">
            <p class="text-sm"><i class="fas fa-phone-alt mr-2"></i> Emergency: 117, 112</p>
          </div>
        </div>
        <div>
          <h3 class="font-bold mb-3">Important Links</h3>
          <ul class="space-y-2 text-sm">
            <li><a href="https://www.who.int/countries/sle" target="_blank" class="hover:underline">WHO Sierra Leone</a></li>
            <li><a href="https://mohs.gov.sl" target="_blank" class="hover:underline">Sierra Leone Ministry of Health</a></li>
            <li><a href="https://www.nmcp.gov.sl" target="_blank" class="hover:underline">National Malaria Control Program</a></li>
            <li><a href="https://www.unicef.org/sierraleone/health" target="_blank" class="hover:underline">UNICEF Child Health</a></li>
          </ul>
        </div>
        <div>
          <h3 class="font-bold mb-3">Disclaimer</h3>
          <p class="text-xs">DoxaCare AI provides general health information only and does not replace professional medical advice. Always consult a qualified healthcare provider for diagnosis and treatment.</p>
        </div>
      </div>
      <div class="border-t border-green-700 mt-6 pt-4 text-center text-sm">
        <p>© 2023 DoxaCare AI - Healthcare Assistant for Sierra Leone</p>
      </div>
    </div>
  </footer>

  <!-- Emergency Modal -->
  <div id="emergencyModal" class="fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center z-50 hidden">
    <div class="bg-white rounded-lg shadow-xl max-w-md w-full p-6">
      <div class="flex justify-between items-center mb-4">
        <h3 class="text-xl font-bold text-red-600">
          <i class="fas fa-exclamation-triangle mr-2"></i>
          Emergency Assistance
        </h3>
        <button id="closeEmergencyModal" class="text-gray-500 hover:text-gray-700">
          <i class="fas fa-times"></i>
        </button>
      </div>
      <p class="text-gray-700 mb-4">If you're experiencing a medical emergency, please take these immediate actions:</p>
      <ul class="space-y-2 mb-4">
        <li class="flex items-start">
          <i class="fas fa-phone-alt text-red-500 mt-1 mr-2"></i>
          <span>Call emergency services: <strong>117 or 112</strong></span>
        </li>
        <li class="flex items-start">
          <i class="fas fa-hospital text-red-500 mt-1 mr-2"></i>
          <span>Go to the nearest hospital immediately</span>
        </li>
        <li class="flex items-start">
          <i class="fas fa-user-md text-red-500 mt-1 mr-2"></i>
          <span>Alert someone nearby for assistance</span>
        </li>
      </ul>
      <div class="bg-red-50 border border-red-200 rounded p-3 mb-4">
        <p class="text-sm text-red-700">Call 117 or go to the closest medical facility immediately if you experience:</p>
        <ul class="list-disc list-inside text-sm text-red-700 mt-1 pl-2">
          <li>Difficulty breathing</li>
          <li>Chest pain</li>
          <li>Severe bleeding</li>
          <li>Loss of consciousness</li>
        </ul>
      </div>
      <button id="callEmergencyBtn" class="w-full bg-red-600 hover:bg-red-700 text-white py-2 px-4 rounded-lg">
        <i class="fas fa-phone mr-2"></i> Call Emergency Services Now
      </button>
    </div>
  </div>

  <script type="module">
    // Firebase Imports
    import { initializeApp } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-app.js";
    import { getAuth, signInAnonymously, signInWithCustomToken, onAuthStateChanged, GoogleAuthProvider, FacebookAuthProvider, signInWithPopup, signOut } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-auth.js";
    import { getFirestore, doc, setDoc, getDoc, collection } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-firestore.js";

    // Initialize Firebase
    const firebaseConfig = JSON.parse(typeof __firebase_config !== 'undefined' ? __firebase_config : '{}');
    const app = initializeApp(firebaseConfig);
    const auth = getAuth(app);
    const db = getFirestore(app);

    // Global variables for Firebase instances and user ID
    let currentUserId = null;
    let isAuthReady = false;
    const appId = typeof __app_id !== 'undefined' ? __app_id : 'default-app-id';

    // Helper function for custom alert
    function showAlert(message, title = 'Alert') {
        const customAlertModal = document.getElementById('customAlertModal');
        const customAlertModalContent = document.getElementById('customAlertModalContent');
        const alertTitle = document.getElementById('alertTitle');
        const alertMessage = document.getElementById('alertMessage');

        alertTitle.textContent = title;
        alertMessage.textContent = message;
        customAlertModal.classList.remove('hidden');
        setTimeout(() => {
            customAlertModalContent.classList.remove('opacity-0', 'scale-95');
            customAlertModalContent.classList.add('opacity-100', 'scale-100');
        }, 10);
    }

    function hideAlert() {
        const customAlertModal = document.getElementById('customAlertModal');
        const customAlertModalContent = document.getElementById('customAlertModalContent');

        customAlertModalContent.classList.remove('opacity-100', 'scale-100');
        customAlertModalContent.classList.add('opacity-0', 'scale-95');
        setTimeout(() => {
            customAlertModal.classList.add('hidden');
        }, 300);
    }

    // Function to show the new post modal
    function showNewPostModal() {
        const newPostModal = document.getElementById('newPostModal');
        const newPostModalContent = document.getElementById('newPostModalContent');
        const postTitleInput = document.getElementById('postTitle');
        const postCityInput = document.getElementById('postCity');
        const postContentTextarea = document.getElementById('postContent');

        newPostModal.classList.remove('hidden');
        setTimeout(() => {
            newPostModalContent.classList.remove('opacity-0', 'scale-95');
            newPostModalContent.classList.add('opacity-100', 'scale-100');
        }, 10);
        postTitleInput.value = '';
        postCityInput.value = '';
        postContentTextarea.value = '';
        postTitleInput.focus();
    }

    // Function to hide the new post modal
    function hideNewPostModal() {
        const newPostModal = document.getElementById('newPostModal');
        const newPostModalContent = document.getElementById('newPostModalContent');
        newPostModalContent.classList.remove('opacity-100', 'scale-100');
        newPostModalContent.classList.add('opacity-0', 'scale-95');
        setTimeout(() => {
            newPostModal.classList.add('hidden');
        }, 300);
    }

    // Function to add a new post
    function addPost() {
        const title = document.getElementById('postTitle').value.trim();
        const city = document.getElementById('postCity').value.trim();
        const content = document.getElementById('postContent').value.trim();
        const accountStatusText = document.getElementById('accountStatusText').textContent;

        if (title === '' || content === '' || city === '') {
            showAlert('Please fill in title, content, and city/town for your post.');
            return;
        }

        const postsContainer = document.getElementById('postsContainer');
        const noPostsMessage = document.getElementById('noPostsMessage');
        const postId = 'post' + Math.random().toString(36).substring(2, 9);
        const timestamp = new Intl.DateTimeFormat('en-US', {
            year: 'numeric',
            month: 'short',
            day: 'numeric',
            hour: '2-digit',
            minute: '2-digit',
            hour12: true,
        }).format(new Date());

        const postDiv = document.createElement('div');
        postDiv.className = 'border border-gray-200 rounded-lg p-4 bg-gray-50 shadow-sm';
        postDiv.innerHTML = `
            <h4 class="font-semibold text-purple-700 text-lg mb-2">${title}</h4>
            <p class="text-gray-700 text-base mb-3">${content}</p>
            <div class="flex items-center text-xs text-gray-500 mb-4">
                <div class="bg-gray-200 border-2 border-dashed rounded-full w-6 h-6 mr-2 flex items-center justify-center overflow-hidden">
                    <i class="fas fa-user text-gray-400 text-sm"></i>
                </div>
                <span>By ${accountStatusText === 'Guest' ? 'Anonymous User' : accountStatusText}</span>
                <span class="mx-2">•</span>
                <span>${city}</span>
                <span class="mx-2">•</span>
                <span>${timestamp}</span>
            </div>
            <div class="mt-4 border-t border-gray-200 pt-4">
                <h5 class="font-medium text-gray-800 mb-3 flex items-center">
                    <i class="fas fa-comment-dots mr-2 text-blue-500"></i>
                    Comments (<span id="commentCount-${postId}">0</span>)
                </h5>
                <div id="commentsList-${postId}" class="space-y-3 mb-4 max-h-48 overflow-y-auto pr-2"></div>
                <p id="noCommentsMessage-${postId}" class="text-sm text-gray-600 italic mb-3">No comments yet. Be the first to reply!</p>
                <div class="flex items-center mt-2">
                    <input type="text" id="commentInput-${postId}" class="flex-grow px-3 py-2 rounded-l-lg border border-gray-300 focus:outline-none focus:ring-2 focus:ring-purple-500 focus:border-transparent text-sm" placeholder="Add a comment..." data-post-id="${postId}">
                    <button onclick="addComment('${postId}')" class="bg-purple-500 text-white p-2 rounded-r-lg hover:bg-purple-600 transition-colors shadow-sm">
                        <i class="fas fa-paper-plane"></i>
                    </button>
                </div>
            </div>
        `;
        postsContainer.insertBefore(postDiv, postsContainer.firstChild);
        noPostsMessage.classList.add('hidden');
        hideNewPostModal();
    }

    // Function to add a comment
    function addComment(postId) {
        const commentInput = document.getElementById(`commentInput-${postId}`);
        const commentText = commentInput.value.trim();
        const accountStatusText = document.getElementById('accountStatusText').textContent;

        if (commentText === '') {
            showAlert('Please enter your comment.');
            return;
        }

        const commentsList = document.getElementById(`commentsList-${postId}`);
        const noCommentsMessage = document.getElementById(`noCommentsMessage-${postId}`);
        const commentCount = document.getElementById(`commentCount-${postId}`);
        const timestamp = new Intl.DateTimeFormat('en-US', {
            year: 'numeric',
            month: 'short',
            day: 'numeric',
            hour: '2-digit',
            minute: '2-digit',
            hour12: true,
        }).format(new Date());

        const commentDiv = document.createElement('div');
        commentDiv.className = 'bg-white border border-gray-100 rounded-lg p-3 shadow-xs';
        commentDiv.innerHTML = `
            <p class="text-gray-700 text-sm mb-1">${commentText}</p>
            <div class="flex items-center text-xs text-gray-500">
                <div class="bg-gray-200 border-2 border-dashed rounded-full w-5 h-5 mr-1 flex items-center justify-center overflow-hidden">
                    <i class="fas fa-reply text-gray-400 text-xs"></i>
                </div>
                <span>By ${accountStatusText === 'Guest' ? 'Community Member' : accountStatusText}</span>
                <span class="mx-1">•</span>
                <span>${timestamp}</span>
            </div>
        `;
        commentsList.appendChild(commentDiv);
        noCommentsMessage.classList.add('hidden');
        commentCount.textContent = parseInt(commentCount.textContent) + 1;
        commentInput.value = '';
    }

    // Function to get or create user profile in Firestore
    async function getUserProfile(uid, email, displayName, photoURL) {
        const userProfileRef = doc(db, `artifacts/${appId}/users/${uid}/user_profiles`, "profile");
        const docSnap = await getDoc(userProfileRef);

        if (!docSnap.exists()) {
            const newProfile = {
                uid: uid,
                email: email || null,
                displayName: displayName || null,
                photoURL: photoURL || null,
                firstName: null,
                lastName: null,
                phone: null,
                username: null,
                createdAt: new Date().toISOString()
            };
            await setDoc(userProfileRef, newProfile);
            return newProfile;
        } else {
            return docSnap.data();
        }
    }

    // Function to update user profile in Firestore
    async function updateUserProfile(uid, firstName, lastName, phone, username) {
        const userProfileRef = doc(db, `artifacts/${appId}/users/${uid}/user_profiles`, "profile");
        await setDoc(userProfileRef, {
            firstName: firstName,
            lastName: lastName,
            phone: phone,
            username: username,
            updatedAt: new Date().toISOString()
        }, { merge: true });
    }

    // Auth state listener
    onAuthStateChanged(auth, async (user) => {
        if (user) {
            currentUserId = user.uid;
            const userProfile = await getUserProfile(user.uid, user.email, user.displayName, user.photoURL);
            updateAccountStatusUI(userProfile);
        } else {
            currentUserId = null;
            updateAccountStatusUI(null);
            if (typeof __initial_auth_token === 'undefined') {
                try {
                    await signInAnonymously(auth);
                } catch (error) {
                    console.error("Error signing in anonymously:", error);
                }
            }
        }
        isAuthReady = true;
    });

    // Initial sign-in
    async function initializeAuth() {
        if (typeof __initial_auth_token !== 'undefined' && __initial_auth_token) {
            try {
                await signInWithCustomToken(auth, __initial_auth_token);
            } catch (error) {
                console.error("Error signing in with custom token:", error);
                try {
                    await signInAnonymously(auth);
                } catch (anonError) {
                    console.error("Error signing in anonymously:", anonError);
                }
            }
        } else {
            try {
                await signInAnonymously(auth);
            } catch (error) {
                console.error("Error signing in anonymously:", error);
            }
        }
    }
    initializeAuth();

    // Update UI based on auth state
    function updateAccountStatusUI(userProfile) {
        const accountStatusText = document.getElementById('accountStatusText');
        const signInOption = document.getElementById('signInOption');
        const signOutOption = document.getElementById('signOutOption');
        const accountFormTitle = document.getElementById('accountFormTitle');
        const signUpForm = document.getElementById('signUpForm');
        const googleSignInBtn = document.getElementById('googleSignInBtn');
        const facebookSignInBtn = document.getElementById('facebookSignInBtn');

        if (userProfile && userProfile.username) {
            accountStatusText.textContent = userProfile.username;
            signInOption.classList.add('hidden');
            signOutOption.classList.remove('hidden');
            if (accountFormTitle) accountFormTitle.textContent = `Welcome, ${userProfile.username}!`;
            if (signUpForm) signUpForm.classList.add('hidden');
            if (googleSignInBtn) googleSignInBtn.classList.add('hidden');
            if (facebookSignInBtn) facebookSignInBtn.classList.add('hidden');
        } else if (userProfile && userProfile.displayName) {
            accountStatusText.textContent = userProfile.displayName.split(' ')[0];
            signInOption.classList.add('hidden');
            signOutOption.classList.remove('hidden');
            if (accountFormTitle) accountFormTitle.textContent = `Welcome, ${userProfile.displayName.split(' ')[0]}!`;
            if (signUpForm) signUpForm.classList.add('hidden');
            if (googleSignInBtn) googleSignInBtn.classList.add('hidden');
            if (facebookSignInBtn) facebookSignInBtn.classList.add('hidden');
        } else if (auth.currentUser && auth.currentUser.isAnonymous) {
            accountStatusText.textContent = 'Guest';
            signInOption.classList.remove('hidden');
            signOutOption.classList.add('hidden');
            if (accountFormTitle) accountFormTitle.textContent = 'Complete Your Profile';
            if (signUpForm) signUpForm.classList.remove('hidden');
            if (googleSignInBtn) googleSignInBtn.classList.remove('hidden');
            if (facebookSignInBtn) facebookSignInBtn.classList.remove('hidden');
        } else {
            accountStatusText.textContent = 'Account';
            signInOption.classList.remove('hidden');
            signOutOption.classList.add('hidden');
            if (accountFormTitle) accountFormTitle.textContent = 'Sign In / Sign Up';
            if (signUpForm) signUpForm.classList.remove('hidden');
            if (googleSignInBtn) googleSignInBtn.classList.remove('hidden');
            if (facebookSignInBtn) facebookSignInBtn.classList.remove('hidden');
        }
        const accountDropdown = document.getElementById('accountDropdown');
        if (accountDropdown) accountDropdown.classList.add('hidden');
    }

    // Force refresh
    if (performance.navigation.type === 1) {
      window.location.search = '?refresh=' + new Date().getTime();
    }

    // Language Toggle
    let isEnglish = false;
    document.getElementById('languageToggle').addEventListener('click', () => {
      isEnglish = !isEnglish;
      const elements = [
        { id: 'currentLanguage', en: 'English', krio: 'Krio' },
        { id: 'welcomeText', hide: !isEnglish },
        { id: 'welcomeTextKrio', hide: isEnglish },
        { id: 'healthAlertsText', hide: !isEnglish },
        { id: 'healthAlertsTextKrio', hide: isEnglish },
        { id: 'welcomeChatText', hide: !isEnglish },
        { id: 'welcomeChatTextKrio', hide: isEnglish },
        { id: 'culturalTipText', hide: !isEnglish },
        { id: 'culturalTipTextKrio', hide: isEnglish },
        { id: 'malariaBtnText', en: 'Malaria', krio: 'Malaria' },
        { id: 'pregnancyBtnText', en: 'Pregnancy', krio: ' Belleful' },
        { id: 'diarrheaBtnText', en: 'Diarrhea', krio: 'Run belle' },
        { id: 'hypertensionBtnText', en: 'Hypertension', krio: 'High BP' },
        { id: 'chatTitle', en: 'Chat with DoxaCare AI', krio: 'Chat wit DoxaCare AI' },
        { id: 'culturalTitle', en: 'Cultural Health Tips', krio: 'Health Tip for We Culture' },
        { id: 'localTipTitle', en: 'Local Health Wisdom', krio: 'Local Health Sense' },
        { id: 'healthAlertsTitle', en: 'Health Alerts', krio: 'Health News' },
        { id: 'quickLinksTitle', en: 'Quick Chats', krio: 'Quick Chat' }
      ];
      elements.forEach(el => {
        const element = document.getElementById(el.id);
        if (el.hide !== undefined) {
          element.classList.toggle('hidden', el.hide);
        } else {
          element.textContent = isEnglish ? el.en : el.krio;
        }
      });
    });

    // Chatbot functionality
    function addUserMessage(message) {
      const messageDiv = document.createElement('div');
      messageDiv.classList.add('chat-message', 'user-message', 'mb-3', 'text-right');
      messageDiv.innerHTML = `<div class="bg-green-500 p-3 rounded-lg shadow-sm max-w-3/4 inline-block text-white">${message}</div>`;
      document.getElementById('chatWindow').appendChild(messageDiv);
      document.getElementById('chatWindow').scrollTop = document.getElementById('chatWindow').scrollHeight;
    }

    function formatBotResponse(text) {
      let formattedText = text.replace(/\n\n/g, '</p><p class="mb-2">');
      formattedText = formattedText.replace(/\n/g, '<br>');
      formattedText = formattedText.replace(/\*\*(.*?)\*\*/g, '<strong>$1</strong>');
      formattedText = formattedText.replace(/\*(.*?)\*/g, '<em>$1</em>');
      if (!formattedText.startsWith('<p')) {
          formattedText = `<p class="mb-2">${formattedText}</p>`;
      }
      return formattedText;
    }

    async function simulateBotResponse(userMessage) {
      const typingIndicator = document.createElement('div');
      typingIndicator.classList.add('chat-message', 'bot-message', 'mb-3', 'typing-indicator');
      typingIndicator.innerHTML = '<div class="bg-white p-3 rounded-lg shadow-sm max-w-3/4 inline-block italic text-gray-500 leading-relaxed">DoxaCare AI is thinking...</div>';
      document.getElementById('chatWindow').appendChild(typingIndicator);
      document.getElementById('chatWindow').scrollTop = document.getElementById('chatWindow').scrollHeight;

      try {
          let chatHistory = [{ role: "user", parts: [{ text: userMessage }] }];
          const payload = { contents: chatHistory };
          const apiKey = "";
          const apiUrl = `https://generativelanguage.googleapis.com/v1beta/models/gemini-2.0-flash:generateContent?key=${apiKey}`;
          const response = await fetch(apiUrl, {
              method: 'POST',
              headers: { 'Content-Type': 'application/json' },
              body: JSON.stringify(payload)
          });
          const result = await response.json();
          let botResponseText = "I'm sorry, I couldn't get a response at this time. Please try again.";
          if (result.candidates && result.candidates[0].content && result.candidates[0].content.parts) {
              botResponseText = result.candidates[0].content.parts[0].text;
          }
          document.getElementById('chatWindow').removeChild(typingIndicator);
          const botMessageDiv = document.createElement('div');
          botMessageDiv.classList.add('chat-message', 'bot-message', 'mb-3');
          const formattedHtmlResponse = formatBotResponse(botResponseText);
          botMessageDiv.innerHTML = `<div class="bg-white p-3 rounded-lg shadow-sm max-w-3/4 inline-block leading-relaxed">${formattedHtmlResponse}</div>`;
          document.getElementById('chatWindow').appendChild(botMessageDiv);
          document.getElementById('chatWindow').scrollTop = document.getElementById('chatWindow').scrollHeight;
      } catch (error) {
          console.error("Error communicating with Gemini API:", error);
          document.getElementById('chatWindow').removeChild(typingIndicator);
          const errorMessageDiv = document.createElement('div');
          errorMessageDiv.classList.add('chat-message', 'bot-message', 'mb-3');
          errorMessageDiv.innerHTML = `<div class="bg-red-100 text-red-700 p-3 rounded-lg shadow-sm max-w-3/4 inline-block leading-relaxed">Error: Could not get a response. Please check your internet connection or try again later.</div>`;
          document.getElementById('chatWindow').appendChild(errorMessageDiv);
          document.getElementById('chatWindow').scrollTop = document.getElementById('chatWindow').scrollHeight;
      }
    }

    document.getElementById('sendBtn')?.addEventListener('click', () => {
      const message = document.getElementById('userInput').value.trim();
      if (message) {
        addUserMessage(message);
        simulateBotResponse(message);
        document.getElementById('userInput').value = '';
      }
    });

    document.getElementById('userInput')?.addEventListener('keypress', (e) => {
      if (e.key === 'Enter') {
        document.getElementById('sendBtn')?.click();
      }
    });

    document.querySelectorAll('.quick-reply-btn').forEach(button => {
      button.addEventListener('click', (event) => {
        const text = event.target.textContent || '';
        if (text) {
          addUserMessage(text);
          simulateBotResponse(text);
        }
      });
    });

    // Symptom checker functionality
    async function simulateHealthTopicResponse(topic) {
      const symptomResults = document.getElementById('symptomResults');
      symptomResults.innerHTML = '';
      symptomResults.classList.remove('hidden');

      const typingIndicator = document.createElement('div');
      typingIndicator.classList.add('bg-gray-100', 'p-3', 'rounded-lg', 'shadow-sm', 'text-center', 'text-gray-500', 'italic', 'typing-indicator', 'leading-relaxed');
      typingIndicator.textContent = 'DoxaCare AI is fetching information...';
      symptomResults.appendChild(typingIndicator);

      try {
          let chatHistory = [{ role: "user", parts: [{ text: `Provide detailed and accurate health information about "${topic}" relevant to Sierra Leone, including symptoms, prevention, and common treatments. Format the response clearly with paragraphs and important terms in bold.` }] }];
          const payload = { contents: chatHistory };
          const apiKey = "";
          const apiUrl = `https://generativelanguage.googleapis.com/v1beta/models/gemini-2.0-flash:generateContent?key=${apiKey}`;
          const response = await fetch(apiUrl, {
              method: 'POST',
              headers: { 'Content-Type': 'application/json' },
              body: JSON.stringify(payload)
          });
          const result = await response.json();
          let botResponseText = "<p class='text-gray-600 italic'>I'm sorry, I couldn't get detailed information for that topic at this time. Please try again or ask a different question.</p>";
          if (result.candidates && result.candidates[0].content && result.candidates[0].content.parts) {
              botResponseText = result.candidates[0].content.parts[0].text;
          }
          symptomResults.removeChild(typingIndicator);
          symptomResults.innerHTML = `
            <h3 class="font-semibold text-blue-800 mb-3">Information on ${topic}:</h3>
            <div class="text-gray-700 leading-relaxed">${botResponseText}</div>
          `;
      } catch (error) {
          console.error("Error communicating with Gemini API for health topics:", error);
          symptomResults.removeChild(typingIndicator);
          symptomResults.innerHTML = `<p class="text-red-700 leading-relaxed">Error: Could not fetch information for "${topic}". Please check your internet connection or try again later.</p>`;
      }
    }

    document.getElementById('checkSymptomsBtn')?.addEventListener('click', () => {
      const inputTopic = document.getElementById('symptomsInput').value.trim();
      if (inputTopic) {
        simulateHealthTopicResponse(inputTopic);
      } else {
        showAlert("Please enter a health topic or symptom.");
      }
    });

    document.getElementById('symptomsInput')?.addEventListener('keypress', (e) => {
      if (e.key === 'Enter') {
        document.getElementById('checkSymptomsBtn')?.click();
      }
    });

    document.querySelectorAll('.symptom-tag').forEach(button => {
      button.addEventListener('click', (event) => {
        const tagText = event.target.textContent || '';
        const dataSymptoms = event.target.dataset.symptoms || tagText;
        document.getElementById('symptomsInput').value = dataSymptoms;
        simulateHealthTopicResponse(dataSymptoms);
      });
    });

    document.getElementById('refreshHealthTopics')?.addEventListener('click', () => {
      document.getElementById('symptomsInput').value = '';
      const symptomResults = document.getElementById('symptomResults');
      if (symptomResults) {
        symptomResults.innerHTML = '';
        symptomResults.classList.add('hidden');
      }
    });

    // Find Clinics functionality
    const sierraLeoneClinics = {
      "freetown": [
        { name: "Connaught Hospital", type: "Government Hospital", address: "Lightfoot Boston St, Freetown", phone: "+232 25 345678", services: "General medicine, emergency, surgery. Open 24/7.", mapUrl: "https://www.openstreetmap.org/export/embed.html?bbox=-13.245,8.485,8.495,-13.235&layer=mapnik" },
        { name: "Lumley Community Clinic", type: "Community Health Centre", address: "Lumley Beach Rd, Freetown", phone: "+232 78 123456", services: "Outpatient care, maternal & child health. Mon-Fri, 8 AM - 5 PM.", mapUrl: "https://www.openstreetmap.org/export/embed.html?bbox=-13.265,8.475,8.485,-13.255&layer=mapnik" },
        { name: "Choithram Memorial Hospital", type: "Private Hospital", address: "Hill Station, Freetown", phone: "+232 79 987654", services: "Specialized care, diagnostics, surgery.", mapUrl: "https://www.openstreetmap.org/export/embed.html?bbox=-13.255,8.465,8.475,-13.245&layer=mapnik" },
        { name: "PCMH (Princess Christian Maternity Hospital)", type: "Maternity Hospital", address: "Freetown Central", phone: "+232 76 112233", services: "Maternal and child health services.", mapUrl: "https://www.openstreetmap.org/export/embed.html?bbox=-13.235,8.485,8.495,-13.225&layer=mapnik" }
      ],
      "bo": [
        { name: "Bo Government Hospital", type: "Government Hospital", address: "Hospital Road, Bo", phone: "+232 76 345678", services: "General hospital services. Open 24/7.", mapUrl: "https://www.openstreetmap.org/export/embed.html?bbox=-11.745,7.955,7.965,-11.735&layer=mapnik" },
        { name: "Bo Clinic Centre", type: "Private Clinic", address: "Dambala Road, Bo", phone: "+232 77 876543", services: "General consultations, minor procedures.", mapUrl: "https://www.openstreetmap.org/export/embed.html?bbox=-11.755,7.945,7.955,-11.745&layer=mapnik" }
      ],
      "kenema": [
        { name: "Kenema Government Hospital", type: "Government Hospital", address: "Clinic Road, Kenema", phone: "+232 76 987654", services: "Major regional hospital. Open 24/7.", mapUrl: "https://www.openstreetmap.org/export/embed.html?bbox=-11.195,7.875,7.885,-11.185&layer=mapnik" },
        { name: "Kenema Health Post", type: "Community Health Post", address: "Ngelehun, Kenema", phone: "N/A", services: "Basic health services, vaccinations.", mapUrl: "https://www.openstreetmap.org/export/embed.html?bbox=-11.205,7.865,7.875,-11.195&layer=mapnik" }
      ],
      "makeni": [
        { name: "Makeni Government Hospital", type: "Government Hospital", address: "Hospital Road, Makeni", phone: "+232 76 223344", services: "General hospital services.", mapUrl: "https://www.openstreetmap.org/export/embed.html?bbox=-12.045,8.885,8.895,-12.035&layer=mapnik" },
        { name: "St. John of God Hospital (Fatima Hospital)", type: "Mission Hospital", address: "Makeni", phone: "+232 77 556677", services: "General medical, surgical, and maternity services.", mapUrl: "https://www.openstreetmap.org/export/embed.html?bbox=-12.055,8.875,8.885,-12.045&layer=mapnik" }
      ],
      "port loko": [
        { name: "Port Loko Government Hospital", type: "Government Hospital", address: "Hospital Road, Port Loko", phone: "+232 76 334455", services: "General hospital services.", mapUrl: "https://www.openstreetmap.org/export/embed.html?bbox=-12.785,8.765,8.775,-12.775&layer=mapnik" }
      ],
      "kailahun": [
        { name: "Kailahun Government Hospital", type: "Government Hospital", address: "Hospital Road, Kailahun", phone: "+232 76 112233", services: "General hospital services.", mapUrl: "https://www.openstreetmap.org/export/embed.html?bbox=-10.575,8.275,8.285,-10.565&layer=mapnik" },
        { name: "Daru Community Health Centre", type: "Community Health Centre", address: "Daru, Kailahun", phone: "N/A", services: "Basic health services.", mapUrl: "https://www.openstreetmap.org/export/embed.html?bbox=-10.585,8.265,8.275,-10.575&layer=mapnik" }
      ],
      "kono": [
        { name: "Kono Government Hospital (Koidu)", type: "Government Hospital", address: "Koidu Town, Kono", phone: "+232 76 445566", services: "General hospital services.", mapUrl: "https://www.openstreetmap.org/export/embed.html?bbox=-10.975,8.645,8.655,-10.965&layer=mapnik" }
      ],
      "moyamba": [
        { name: "Moyamba Government Hospital", type: "Government Hospital", address: "Hospital Road, Moyamba", phone: "+232 76 778899", services: "General hospital services.", mapUrl: "https://www.openstreetmap.org/export/embed.html?bbox=-12.435,8.155,8.165,-12.425&layer=mapnik" }
      ],
      "bombali": [
        { name: "Bombali District Hospital", type: "Government Hospital", address: "Makeni", phone: "+232 76 223344", services: "General hospital services.", mapUrl: "https://www.openstreetmap.org/export/embed.html?bbox=-12.045,8.885,8.895,-12.035&layer=mapnik" }
      ],
      "tonkolili": [
        { name: "Magburaka Government Hospital", type: "Government Hospital", address: "Magburaka, Tonkolili", phone: "+232 76 334455", services: "General hospital services.", mapUrl: "https://www.openstreetmap.org/export/embed.html?bbox=-11.945,8.715,8.725,-11.935&layer=mapnik" }
      ],
      "pujehun": [
        { name: "Pujehun Government Hospital", type: "Government Hospital", address: "Pujehun", phone: "+232 76 990011", services: "General hospital services.", mapUrl: "https://www.openstreetmap.org/export/embed.html?bbox=-11.725,7.345,7.355,-11.715&layer=mapnik" }
      ],
      "kambia": [
        { name: "Kambia Government Hospital", type: "Government Hospital", address: "Kambia", phone: "+232 76 102030", services: "General hospital services.", mapUrl: "https://www.openstreetmap.org/export/embed.html?bbox=-12.925,9.115,9.125,-12.915&layer=mapnik" }
      ],
      "bonthe": [
        { name: "Bonthe Government Hospital", type: "Government Hospital", address: "Bonthe Island", phone: "+232 76 405060", services: "General hospital services.", mapUrl: "https://www.openstreetmap.org/export/embed.html?bbox=-12.505,7.525,7.535,-12.495&layer=mapnik" }
      ],
      "koinadugu": [
        { name: "Kabala Government Hospital", type: "Government Hospital", address: "Kabala, Koinadugu", phone: "+232 76 708090", services: "General hospital services.", mapUrl: "https://www.openstreetmap.org/export/embed.html?bbox=-11.555,9.585,9.595,-11.545&layer=mapnik" }
      ],
      "karene": [
        { name: "Karene District Hospital", type: "Government Hospital", address: "Kamalo, Karene", phone: "+232 76 112233", services: "General hospital services.", mapUrl: "https://www.openstreetmap.org/export/embed.html?bbox=-12.455,8.955,8.965,-12.445&layer=mapnik" }
      ],
      "falaba": [
        { name: "Falaba District Hospital", type: "Government Hospital", address: "Bendugu, Falaba", phone: "+232 76 223344", services: "General hospital services.", mapUrl: "https://www.openstreetmap.org/export/embed.html?bbox=-11.285,9.655,9.665,-11.275&layer=mapnik" }
      ],
      "pampana": [
        { name: "Pampana Health Centre", type: "Community Health Centre", address: "Pampana, Tonkolili", phone: "N/A", services: "Basic health services.", mapUrl: "https://www.openstreetmap.org/export/embed.html?bbox=-11.805,8.555,8.565,-11.795&layer=mapnik" }
      ],
      "waterloo": [
        { name: "Waterloo Community Hospital", type: "Community Hospital", address: "Waterloo, Western Area Rural", phone: "+232 76 556677", services: "General medical services.", mapUrl: "https://www.openstreetmap.org/export/embed.html?bbox=-13.085,8.335,8.345,-13.075&layer=mapnik" }
      ],
      "magburaka": [
        { name: "Magburaka Government Hospital", type: "Government Hospital", address: "Magburaka, Tonkolili", phone: "+232 76 334455", services: "General hospital services.", mapUrl: "https://www.openstreetmap.org/export/embed.html?bbox=-11.945,8.715,8.725,-11.935&layer=mapnik" }
      ]
    };

    function displayClinics(location) {
      const clinicResultsDiv = document.getElementById('clinicResults');
      clinicResultsDiv.innerHTML = '';
      const normalizedLocation = location.toLowerCase().trim();

      const clinics = sierraLeoneClinics[normalizedLocation];

      if (clinics && clinics.length > 0) {
        clinics.forEach(clinic => {
          const clinicCard = document.createElement('div');
          clinicCard.className = 'bg-gray-50 border border-gray-200 rounded-lg p-4 shadow-sm';
          clinicCard.innerHTML = `
            <h3 class="font-semibold text-red-700 text-lg mb-1">${clinic.name}</h3>
            <p class="text-sm text-gray-600 mb-2">${clinic.type}</p>
            <p class="text-gray-700 text-sm"><i class="fas fa-map-marker-alt mr-2 text-red-500"></i>${clinic.address}</p>
            <p class="text-gray-700 text-sm"><i class="fas fa-phone mr-2 text-red-500"></i>${clinic.phone}</p>
            <p class="text-gray-700 text-sm mt-1 mb-2"><strong>Services:</strong> ${clinic.services}</p>
            ${clinic.mapUrl ? `<iframe class="map-iframe" src="${clinic.mapUrl}" allowfullscreen></iframe>` : '<p class="text-sm text-gray-500 italic">Map not available for this clinic.</p>'}
          `;
          clinicResultsDiv.appendChild(clinicCard);
        });
      } else {
        clinicResultsDiv.innerHTML = `
          <div class="bg-yellow-50 border border-yellow-200 rounded-lg p-4 text-center text-yellow-800">
            <i class="fas fa-exclamation-circle text-2xl mb-2"></i>
            <p class="font-medium">No clinics found for "${location}".</p>
            <p class="text-sm mt-1">Please try a different district or city in Sierra Leone (e.g., Freetown, Bo, Kenema).</p>
          </div>
        `;
      }
    }

    document.getElementById('findClinicsBtn')?.addEventListener('click', () => {
      const locationInput = document.getElementById('locationInput').value.trim();
      if (locationInput) {
        displayClinics(locationInput);
      } else {
        showAlert("Please enter a location to find clinics.");
      }
    });

    document.getElementById('locationInput')?.addEventListener('keypress', (e) => {
      if (e.key === 'Enter') {
        document.getElementById('findClinicsBtn')?.click();
      }
    });

    // Tab switching logic
    document.querySelectorAll('.tab-btn').forEach(button => {
      button.addEventListener('click', (event) => {
        document.querySelectorAll('.tab-btn').forEach(btn => {
          btn.classList.remove('active', 'text-green-700', 'border-green-700');
          btn.classList.add('text-gray-600');
        });
        document.querySelectorAll('.tab-content').forEach(content => {
          content.classList.add('hidden');
        });

        event.currentTarget.classList.add('active', 'text-green-700', 'border-green-700');
        event.currentTarget.classList.remove('text-gray-600');
        document.getElementById(`${event.currentTarget.dataset.tab}-tab`).classList.remove('hidden');
      });
    });

    // Emergency Modal Logic
    document.getElementById('emergencyBtn')?.addEventListener('click', () => {
      document.getElementById('emergencyModal').classList.remove('hidden');
    });

    document.getElementById('closeEmergencyModal')?.addEventListener('click', () => {
      document.getElementById('emergencyModal').classList.add('hidden');
    });

    document.getElementById('callEmergencyBtn')?.addEventListener('click', () => {
      showAlert("This is a simulated call. In a real emergency, please dial 117 or 112 directly from your phone.", "Simulated Emergency Call");
    });

    // Account Dropdown Logic
    document.getElementById('accountMenuBtn')?.addEventListener('click', () => {
        const accountDropdown = document.getElementById('accountDropdown');
        accountDropdown.classList.toggle('hidden');
    });

    document.getElementById('signInOption')?.addEventListener('click', async (e) => {
        e.preventDefault();
        // Switch to account tab
        document.querySelectorAll('.tab-btn').forEach(btn => {
            btn.classList.remove('active', 'text-green-700', 'border-green-700');
            btn.classList.add('text-gray-600');
        });
        document.querySelectorAll('.tab-content').forEach(content => {
            content.classList.add('hidden');
        });
        document.querySelector('.tab-btn[data-tab="account"]').classList.add('active', 'text-green-700', 'border-green-700');
        document.querySelector('.tab-btn[data-tab="account"]').classList.remove('text-gray-600');
        document.getElementById('account-tab').classList.remove('hidden');
        
        document.getElementById('accountDropdown').classList.add('hidden'); // Hide dropdown after click
    });

    document.getElementById('signOutOption')?.addEventListener('click', async (e) => {
        e.preventDefault();
        try {
            await signOut(auth);
            showAlert("You have been signed out.", "Signed Out");
            // Optionally, switch back to home tab or refresh UI
            document.getElementById('accountDropdown').classList.add('hidden'); // Hide dropdown after click
        } catch (error) {
            console.error("Error signing out:", error);
            showAlert("Failed to sign out. Please try again.", "Sign Out Error");
        }
    });

    // Social Sign-in
    document.getElementById('googleSignInBtn')?.addEventListener('click', async () => {
        const provider = new GoogleAuthProvider();
        try {
            await signInWithPopup(auth, provider);
            showAlert("Signed in with Google successfully!", "Success");
        } catch (error) {
            console.error("Google sign-in error:", error);
            showAlert(`Google sign-in failed: ${error.message}`, "Sign-in Error");
        }
    });

    document.getElementById('facebookSignInBtn')?.addEventListener('click', async () => {
        const provider = new FacebookAuthProvider();
        try {
            await signInWithPopup(auth, provider);
            showAlert("Signed in with Facebook successfully!", "Success");
        } catch (error) {
            console.error("Facebook sign-in error:", error);
            showAlert(`Facebook sign-in failed: ${error.message}`, "Sign-in Error");
        }
    });

    // Profile Completion Form Submission
    document.getElementById('signUpForm')?.addEventListener('submit', async (e) => {
        e.preventDefault();
        const firstName = document.getElementById('firstName').value.trim();
        const lastName = document.getElementById('lastName').value.trim();
        const phone = document.getElementById('phone').value.trim();
        const username = document.getElementById('username').value.trim();
        const authMessage = document.getElementById('authMessage');

        if (!firstName || !lastName || !phone || !username) {
            authMessage.textContent = "Please fill in all profile fields.";
            authMessage.classList.remove('hidden');
            return;
        }

        if (!currentUserId) {
            authMessage.textContent = "Authentication error. Please try signing in again.";
            authMessage.classList.remove('hidden');
            return;
        }

        try {
            await updateUserProfile(currentUserId, firstName, lastName, phone, username);
            authMessage.textContent = "Profile updated successfully!";
            authMessage.classList.remove('hidden');
            authMessage.classList.remove('text-red-600');
            authMessage.classList.add('text-green-600');
            // Refresh UI after update
            const userProfile = await getUserProfile(currentUserId);
            updateAccountStatusUI(userProfile);
        } catch (error) {
            console.error("Error updating profile:", error);
            authMessage.textContent = `Failed to update profile: ${error.message}`;
            authMessage.classList.remove('hidden');
            authMessage.classList.remove('text-green-600');
            authMessage.classList.add('text-red-600');
        }
    });

    // Make functions globally accessible for onclick attributes
    window.showNewPostModal = showNewPostModal;
    window.hideNewPostModal = hideNewPostModal;
    window.addPost = addPost;
    window.addComment = addComment;
    window.showAlert = showAlert;
    window.hideAlert = hideAlert;
  </script>
  </div>
</body>
</html>
