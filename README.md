<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Ugochukwu's GitHub Profile</title>
  <script src="https://cdn.jsdelivr.net/npm/react@18.2.0/umd/react.production.min.js"></script>
  <script src="https://cdn.jsdelivr.net/npm/react-dom@18.2.0/umd/react-dom.production.min.js"></script>
  <script src="https://cdn.jsdelivr.net/npm/babel-standalone@7.22.10/babel.min.js"></script>
  <script src="https://cdn.tailwindcss.com"></script>
</head>
<body>
  <div id="root"></div>
  <script type="text/babel">
    const { useState } = React;

    const App = () => {
      const [isDarkMode, setIsDarkMode] = useState(true);
      const [formData, setFormData] = useState({ name: '', message: '' });

      const toggleTheme = () => setIsDarkMode(!isDarkMode);

      const handleInputChange = (e) => {
        const { name, value } = e.target;
        setFormData({ ...formData, [name]: value });
      };

      const handleSubmit = (e) => {
        e.preventDefault();
        alert(`Message from ${formData.name}: ${formData.message}`);
        setFormData({ name: '', message: '' });
      };

      return (
        <div className={`min-h-screen ${isDarkMode ? 'bg-gray-900 text-white' : 'bg-gray-100 text-gray-900'} transition-colors duration-300`}>
          <div className="container mx-auto p-6 max-w-4xl">
            <header className="text-center mb-8">
              <h1 className="text-4xl font-bold">Hi there, I'm Ugochukwu 👨‍💻🚀</h1>
              <button
                onClick={toggleTheme}
                className="mt-4 px-4 py-2 bg-blue-600 rounded hover:bg-blue-700 transition"
              >
                {isDarkMode ? 'Switch to Light Mode' : 'Switch to Dark Mode'}
              </button>
            </header>

            <section className="mb-8">
              <h2 className="text-2xl font-semibold mb-4">📱 Mobile App Development</h2>
              <p className="text-lg italic">Seriously, I just want to code and go home</p>
            </section>

            <section className="mb-8">
              <h2 className="text-2xl font-semibold mb-4">💡 Professional Snapshot</h2>
              <ul className="list-disc list-inside">
                <li><strong>Experience:</strong> 5+ years in mobile app development.</li>
                <li><strong>Specialization:</strong> Cross-platform applications.</li>
                <li><strong>Impact:</strong> 100,000+ app downloads across various industries.</li>
              </ul>
            </section>

            <section className="mb-8">
              <h2 className="text-2xl font-semibold mb-4">🛠️ Tools</h2>
              <div className="flex flex-wrap gap-2">
                {[
                  { name: 'React Native', color: 'bg-blue-500', logo: 'https://img.shields.io/badge/-React_Native-61DAFB?style=flat-square&logo=react&logoColor=white' },
                  { name: 'Dart', color: 'bg-blue-700', logo: 'https://img.shields.io/badge/-Dart-0175C2?style=flat-square&logo=dart&logoColor=white' },
                  { name: 'Flutter', color: 'bg-blue-800', logo: 'https://img.shields.io/badge/-Flutter-02569B?style=flat-square&logo=flutter&logoColor=white' },
                  { name: 'Firebase', color: 'bg-yellow-500', logo: 'https://img.shields.io/badge/-Firebase-FFCA28?style=flat-square&logo=firebase&logoColor=black' },
                  { name: 'Supabase', color: 'bg-green-500', logo: 'https://img.shields.io/badge/-Supabase-3ECF8E?style=flat-square&logo=supabase&logoColor=white' },
                  { name: 'Docker', color: 'bg-blue-600', logo: 'https://img.shields.io/badge/-Docker-2496ED?style=flat-square&logo=docker&logoColor=white' }
                ].map((tool) => (
                  <img
                    key={tool.name}
                    src={tool.logo}
                    alt={tool.name}
                    className={`h-8 transform hover:scale-110 transition duration-300 ${tool.color}`}
                  />
                ))}
              </div>
            </section>

            <section className="mb-8">
              <h2 className="text-2xl font-semibold mb-4">🌐 Let's Connect!</h2>
              <div className="flex justify-center gap-4">
                {[
                  { href: 'https://wa.me/2347012053471?text=Hello Henry I need you for a gig', src: 'https://img.shields.io/badge/WhatsApp-25D366?style=for-the-badge&logo=whatsapp&logoColor=white', alt: 'WhatsApp' },
                  { href: 'https://twitter.com/henry_dykee', src: 'https://img.shields.io/badge/Twitter-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white', alt: 'Twitter' },
                  { href: 'https://www.linkedin.com/in/ugochukwu-dike-33027b175/', src: 'https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white', alt: 'LinkedIn' },
                  { href: 'mailto:dykeehenry@gmail.com', src: 'https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white', alt: 'Email' }
                ].map((link) => (
                  <a key={link.alt} href={link.href} target="_blank" rel="noopener noreferrer">
                    <img src={link.src} alt={link.alt} className="h-10 hover:opacity-80 transition" />
                  </a>
                ))}
              </div>
            </section>

            <section className="mb-8">
              <h2 className="text-2xl font-semibold mb-4">📩 Contact Me</h2>
              <div className="max-w-md mx-auto">
                <input
                  type="text"
                  name="name"
                  value={formData.name}
                  onChange={handleInputChange}
                  placeholder="Your Name"
                  className={`w-full p-2 mb-4 rounded ${isDarkMode ? 'bg-gray-800 text-white' : 'bg-white text-gray-900'} border ${isDarkMode ? 'border-gray-700' : 'border-gray-300'}`}
                />
                <textarea
                  name="message"
                  value={formData.message}
                  onChange={handleInputChange}
                  placeholder="Your Message"
                  rows="4"
                  className={`w-full p-2 mb-4 rounded ${isDarkMode ? 'bg-gray-800 text-white' : 'bg-white text-gray-900'} border ${isDarkMode ? 'border-gray-700' : 'border-gray-300'}`}
                ></textarea>
                <button
                  onClick={handleSubmit}
                  className="w-full p-2 bg-blue-600 rounded hover:bg-blue-700 transition"
                >
                  Send Message
                </button>
              </div>
            </section>

            <section className="mb-8">
              <h2 className="text-2xl font-semibold mb-4">📊 GitHub Analytics</h2>
              <div className="flex flex-col items-center gap-4">
                <img src="https://github-readme-stats.vercel.app/api?username=Henrydykee&show_icons=true&theme=tokyonight&include_all_commits=true&count_private=true" alt="GitHub Stats" className="w-full max-w-md" />
                <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=Henrydykee&layout=compact&langs_count=7&theme=tokyonight" alt="Top Languages" className="w-full max-w-md" />
              </div>
            </section>

            <section className="mb-8">
              <h2 className="text-2xl font-semibold mb-4">🏆 Achievements & Milestones</h2>
              <img src="https://github-profile-trophy.vercel.app/?username=Henrydykee&theme=tokyonight&column=7&margin-w=15&margin-h=15" alt="GitHub Trophies" className="w-full" />
            </section>

            <section className="mb-8">
              <h2 className="text-2xl font-semibold mb-4">📈 Contribution Landscape</h2>
              <img src="https://github-readme-activity-graph.vercel.app/graph?username=Henrydykee&theme=tokyo-night" alt="Contribution Graph" className="w-full" />
            </section>

            <footer className="text-center">
              <p className="text-lg">Crafting code, creating experiences 💻✨</p>
              <p className="text-sm">Made with ❤️ by Ugochukwu</p>
            </footer>
          </div>
        </div>
      );
    };

    ReactDOM.render(<App />, document.getElementById('root'));
  </script>
</body>
</html>
