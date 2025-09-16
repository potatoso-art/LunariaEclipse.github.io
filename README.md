import React, { useState, useEffect } from 'react';
import { Heart, Star, Moon, Sparkles, Github, Twitter, Instagram, Mail, Play, Volume2, Gamepad2, Users } from 'lucide-react';
import { motion, AnimatePresence } from 'framer-motion';

const App = () => {
  const [currentArtIndex, setCurrentArtIndex] = useState(0);
  const [isMenuOpen, setIsMenuOpen] = useState(false);

  const gameArt = [
    'https://placehold.co/1200x600/1a1a2e/16213e?text=Moonlit+Garden+Scene',
    'https://placehold.co/1200x600/0f3460/16213e?text=Character+Portrait',
    'https://placehold.co/1200x600/533483/16213e?text=Magical+Battle+Scene',
    'https://placehold.co/1200x600/7209b7/16213e?text=Enchanted+City'
  ];

  const gameplayVideos = [
    { id: 1, title: 'Character Abilities Showcase', thumbnail: 'https://placehold.co/600x338/1a1a2e/16213e?text=Combat+System', duration: '2:45' },
    { id: 2, title: 'Moonlit Exploration', thumbnail: 'https://placehold.co/600x338/0f3460/16213e?text=Open+World', duration: '3:12' },
    { id: 3, title: 'Story & Cutscenes', thumbnail: 'https://placehold.co/600x338/533483/16213e?text=Narrative', duration: '4:20' },
    { id: 4, title: 'Character Customization', thumbnail: 'https://placehold.co/600x338/7209b7/16213e?text=Styling', duration: '1:58' }
  ];

  const supportTiers = [
    {
      name: 'Star Light',
      price: '$5',
      benefits: ['Early Access to Art', 'Monthly Wallpaper', 'Discord Role', 'Developer Updates'],
      color: 'from-purple-400 to-pink-400',
      popular: false
    },
    {
      name: 'Moon Beam',
      price: '$15',
      benefits: ['All Star Light Benefits', 'Beta Access', 'Digital Artbook', 'Behind the Scenes', 'Exclusive Content'],
      color: 'from-blue-400 to-purple-500',
      popular: true
    },
    {
      name: 'Celestial Guardian',
      price: '%%%LATEX_BLOCK_1%%%{Math.random() * 100}%`,
              top: `%%%LATEX_BLOCK_2%%%{isMenuOpen ? 'rotate-45 translate-y-1' : '-translate-y-0.5'}`}></span>
              <span className={`bg-white block transition-all duration-300 ease-out h-0.5 w-6 rounded-sm my-0.5 %%%LATEX_BLOCK_3%%%{isMenuOpen ? '-rotate-45 -translate-y-1' : 'translate-y-0.5'}`}></span>
            </div>
          </button>
        </nav>
        {/* Mobile Menu */}
        <AnimatePresence>
          {isMenuOpen && (
            <motion.div
              initial={{ opacity: 0, height: 0 }}
              animate={{ opacity: 1, height: 'auto' }}
              exit={{ opacity: 0, height: 0 }}
              className="lg:hidden mt-4 bg-slate-800/90 backdrop-blur-sm rounded-xl p-6"
            >
              <div className="flex flex-col space-y-4">
                <a href="#features" className="hover:text-purple-400 transition-colors">Features</a>
                <a href="#gallery" className="hover:text-purple-400 transition-colors">Gallery</a>
                <a href="#gameplay" className="hover:text-purple-400 transition-colors">Gameplay</a>
                <a href="#support" className="hover:text-purple-400 transition-colors">Support</a>
                <a href="#about" className="hover:text-purple-400 transition-colors">About</a>
                <button className="px-6 py-2 bg-gradient-to-r from-purple-500 to-pink-500 rounded-full font-semibold hover:from-purple-600 hover:to-pink-600 transition-all w-fit">
                  Wishlist
                </button>
              </div>
            </motion.div>
          )}
        </AnimatePresence>
      </header>
      {/* Hero Section */}
      <section className="relative z-10 py-16 px-6">
        <div className="max-w-7xl mx-auto">
          <div className="grid lg:grid-cols-2 gap-12 items-center">
            <motion.div
              initial={{ opacity: 0, x: -30 }}
              animate={{ opacity: 1, x: 0 }}
              transition={{ duration: 0.8 }}
            >
              <h1 className="text-5xl lg:text-7xl font-bold mb-6 leading-tight">
                <span className="bg-gradient-to-r from-purple-400 via-pink-400 to-blue-400 bg-clip-text text-transparent">
                  Embark on a
                </span>
                <br />
                <span className="text-white">Celestial Journey</span>
              </h1>              
              <p className="text-xl text-gray-300 mb-8 leading-relaxed">
                Discover an enchanting world where dreams take flight under moonlit skies. 
                Experience magical adventures, forge meaningful connections, and uncover 
                the mysteries of the celestial realm.
              </p>
              <div className="flex flex-col sm:flex-row gap-4">
                <button className="px-8 py-4 bg-gradient-to-r from-purple-500 to-pink-500 rounded-full font-semibold text-lg hover:from-purple-600 hover:to-pink-600 transition-all transform hover:scale-105 flex items-center space-x-2 shadow-lg">
                  <Play className="w-5 h-5" />
                  <span>Wishlist Now</span>
                </button>     
                <button className="px-8 py-4 border-2 border-purple-400 rounded-full font-semibold text-lg hover:bg-purple-400 hover:text-slate-900 transition-all flex items-center space-x-2">
                  <Sparkles className="w-5 h-5" />
                  <span>View Trailer</span>
                </button>
              </div>
              <div className="flex items-center space-x-6 mt-8">
                <div className="flex items-center space-x-2">
                  <Users className="w-5 h-5 text-purple-400" />
                  <span className="text-gray-300">Indie Developer</span>
                </div>
                <div className="flex items-center space-x-2">
                  <Gamepad2 className="w-5 h-5 text-pink-400" />
                  <span className="text-gray-300">Coming 2024</span>
                </div>
              </div>
            </motion.div>
            <motion.div
              initial={{ opacity: 0, scale: 0.9 }}
              animate={{ opacity: 1, scale: 1 }}
              transition={{ duration: 0.8, delay: 0.2 }}
              className="relative"
            >
              <div className="relative overflow-hidden rounded-2xl shadow-2xl">
                <img
                  src={gameArt[currentArtIndex]}
                  alt="Game Art"
                  className="w-full h-96 lg:h-[500px] object-cover"
                />
                <div className="absolute inset-0 bg-gradient-to-t from-black/60 via-transparent to-transparent" /> 
>
                {/* Art Navigation */}
                <div className="absolute bottom-6 left-1/2 transform -translate-x-1/2 flex space-x-3">
                  {gameArt.map((_, index) => (
                    <button
                      key={index}
                      onClick={() => setCurrentArtIndex(index)}
                      className={`w-3 h-3 rounded-full transition-all %%%LATEX_BLOCK_4%%%{index + 1}`}
                    className="w-full h-48 object-cover"
                  />
                  <div className="absolute inset-0 bg-gradient-to-t from-black/50 to-transparent opacity-0 hover:opacity-100 transition-opacity flex items-end p-4">
                    <span className="text-sm font-medium">View Details</span>
                  </div>
                </motion.div>
              ))}
            </motion.div>
          </div>
        </div>
      </section>
      {/* Gameplay Section */}
      <section id="gameplay" className="relative z-10 py-20 px-6">
        <div className="max-w-7xl mx-auto">
          <motion.h2
            initial={{ opacity: 0, y: 20 }}
            whileInView={{ opacity: 1, y: 0 }}
            viewport={{ once: true }}
            className="text-4xl lg:text-5xl font-bold text-center mb-16"
            <span className="bg-gradient-to-r from-pink-400 to-purple-400 bg-clip-text text-transparent">
              Gameplay Showcase
            </span>
          </motion.h2>
          <div className="grid md:grid-cols-2 gap-8">
            {gameplayVideos.map((video, index) => (
              <motion.div
                key={video.id}
                initial={{ opacity: 0, y: 20 }}
                whileInView={{ opacity: 1, y: 0 }}
                viewport={{ once: true }}
                transition={{ delay: index * 0.1 }}
                className="group cursor-pointer"
                <div className="relative overflow-hidden rounded-xl mb-4">
                  <img
                    src={video.thumbnail}
                    alt={video.title}
                    className="w-full h-64 object-cover group-hover:scale-110 transition-transform duration-500"
                  />
                  <div className="absolute inset-0 bg-black/40 group-hover:bg-black/20 transition-all flex items-center justify-center">
                    <div className="w-20 h-20 bg-white/20 backdrop-blur-sm rounded-full flex items-center justify-center group-hover:bg-white/30 transition-all">
                      <Play className="w-8 h-8 text-white ml-1" />
                    </div>
                  </div>
                  <div className="absolute bottom-4 right-4 bg-black/70 backdrop-blur-sm rounded px-2 py-1 text-sm">
                    {video.duration}
                  </div>
                </div>
                <h3 className="text-xl font-semibold group-hover:text-purple-400 transition-colors">
                  {video.title}
                </h3>
              </motion.div>
            ))}
          </div>
          <motion.div
            initial={{ opacity: 0, y: 20 }}
            whileInView={{ opacity: 1, y: 0 }}
            viewport={{ once: true }}
            className="mt-16 text-center"
            <div className="inline-flex items-center space-x-6 bg-gradient-to-r from-purple-500/20 to-blue-500/20 p-8 rounded-2xl border border-purple-400/30 max-w-4xl mx-auto">
              <div className="p-4 bg-purple-500/20 rounded-full">
                <Volume2 className="w-10 h-10 text-purple-400" />
              </div>
              <div className="text-left">
                <h3 className="text-2xl font-bold mb-2">Immersive Soundtrack</h3>
                <p className="text-lg text-gray-300">
                  Experience the magical world with our original celestial-inspired music composed by award-winning artists. 
                  Each track is designed to enhance your emotional journey through the game.
                </p>
              </div>
            </div>
          </motion.div>
        </div>
      </section>
      {/* Support Section */}
      <section id="support" className="relative z-10 py-20 px-6">
        <div className="max-w-7xl mx-auto">
          <motion.h2
            initial={{ opacity: 0, y: 20 }}
            whileInView={{ opacity: 1, y: 0 }}
            viewport={{ once: true }}
            className="text-4xl lg:text-5xl font-bold text-center mb-16"
            <span className="bg-gradient-to-r from-pink-400 to-purple-400 bg-clip-text text-transparent">
              Support the Dream
            </span>
          </motion.h2>
          <div className="grid md:grid-cols-3 gap-8">
            {supportTiers.map((tier, index) => (
              <motion.div
                key={tier.name}
                initial={{ opacity: 0, y: 20 }}
                whileInView={{ opacity: 1, y: 0 }}
                viewport={{ once: true }}
                transition={{ delay: index * 0.1 }}
                className="relative bg-gradient-to-br from-slate-800/50 to-slate-900/50 backdrop-blur-sm rounded-2xl p-8 border border-purple-400/20 hover:border-purple-400/40 transition-all group overflow-hidden"
                {tier.popular && (
                  <div className="absolute -top-2 -right-2 bg-gradient-to-r from-pink-500 to-purple-500 text-white text-xs font-bold px-4 py-1 rounded-full rotate-45">
                    POPULAR
                  </div>
                )}
                <div className={`bg-gradient-to-r %%%LATEX_BLOCK_5%%%{tier.color} hover:shadow-lg transition-all transform hover:scale-105 text-white`}>
                  Choose {tier.name}
                </button>
              </motion.div>
            ))}
          </div>
          <motion.div
            initial={{ opacity: 0, y: 20 }}
            whileInView={{ opacity: 1, y: 0 }}
            viewport={{ once: true }}
            className="mt-16 text-center"
            <p className="text-xl text-gray-300 mb-8 max-w-3xl mx-auto">
              Every contribution helps bring Celestial Dreams to life. Your support means the world to our small, passionate team 
              of dreamers working tirelessly to create something magical for you.
            </p>            
            <div className="flex flex-col sm:flex-row gap-6 justify-center items-center">
              <button className="px-8 py-4 bg-gradient-to-r from-purple-500 to-pink-500 rounded-full font-semibold hover:from-purple-600 hover:to-pink-600 transition-all flex items-center space-x-3 shadow-lg">
                <Github className="w-5 h-5" />
                <span>GitHub Sponsors</span>
              </button>
              <button className="px-8 py-4 border-2 border-purple-400 rounded-full font-semibold hover:bg-purple-400 hover:text-slate-900 transition-all flex items-center space-x-3">
                <Heart className="w-5 h-5" />
                <span>One-time Donation</span>
              </button>
            </div>
          </motion.div>
        </div>
      </section>
      {/* About Section */}
      <section id="about" className="relative z-10 py-20 px-6">
        <div className="max-w-4xl mx-auto text-center">
          <motion.h2
            initial={{ opacity: 0, y: 20 }}
            whileInView={{ opacity: 1, y: 0 }}
            viewport={{ once: true }}
            className="text-4xl lg:text-5xl font-bold mb-8"
            <span className="bg-gradient-to-r from-purple-400 to-pink-400 bg-clip-text text-transparent">
              About the Journey
            </span>
          </motion.h2>         
          <motion.p
            initial={{ opacity: 0, y: 20 }}
            whileInView={{ opacity: 1, y: 0 }}
            viewport={{ once: true }}
            transition={{ delay: 0.1 }}
            className="text-xl text-gray-300 mb-8 leading-relaxed"
            Celestial Dreams began as a small passion project born from love for magical worlds and meaningful storytelling. 
            What started as sketches on napkins has evolved into an ambitious vision to create something truly special.
          </motion.p>       
          <motion.p
            initial={{ opacity: 0, y: 20 }}
            whileInView={{ opacity: 1, y: 0 }}
            viewport={{ once: true }}
            transition={{ delay: 0.2 }}
            className="text-lg text-gray-400 mb-12"
            As an indie developer, every bit of support brings us closer to sharing this dream world with you. 
            Thank you for being part of this incredible journey.
          </motion.p>
          <motion.div
            initial={{ opacity: 0, scale: 0.9 }}
            whileInView={{ opacity: 1, scale: 1 }}
            viewport={{ once: true }}
            transition={{ delay: 0.3 }}
            className="flex justify-center space-x-8"
            <div className="text-center">
              <div className="w-16 h-16 bg-gradient-to-r from-purple-500 to-pink-500 rounded-full flex items-center justify-center mx-auto mb-3">
                <Users className="w-8 h-8 text-white" />
              </div>
              <p className="font-semibold">Indie Team</p>
              <p className="text-gray-400 text-sm">1 Developer</p>
            </div>     
            <div className="text-center">
              <div className="w-16 h-16 bg-gradient-to-r from-blue-500 to-purple-500 rounded-full flex items-center justify-center mx-auto mb-3">
                <Gamepad2 className="w-8 h-8 text-white" />
              </div>
              <p className="font-semibold">Platform</p>
              <p className="text-gray-400 text-sm">PC & Consoles</p>
            </div>       
            <div className="text-center">
              <div className="w-16 h-16 bg-gradient-to-r from-pink-500 to-purple-600 rounded-full flex items-center justify-center mx-auto mb-3">
                <Heart className="w-8 h-8 text-white" />
              </div>
              <p className="font-semibold">Community</p>
              <p className="text-gray-400 text-sm">Growing Fast</p>
            </div>
          </motion.div>
        </div>
      </section>
      {/* Footer */}
      <footer className="relative z-10 py-12 px-6 border-t border-purple-400/20">
        <div className="max-w-7xl mx-auto">
          <div className="grid md:grid-cols-4 gap-8 mb-8">
            <div className="col-span-2">
              <div className="flex items-center space-x-3 mb-4">
                <Moon className="w-8 h-8 text-purple-400" />
                <span className="text-2xl font-bold">Celestial Dreams</span>
              </div>
              <p className="text-gray-400 mb-4 max-w-md">
                An indie game project bringing magical worlds to life through beautiful art, 
                meaningful stories, and innovative gameplay.
              </p>
              <div className="flex space-x-4">
                <a href="#" className="w-10 h-10 bg-slate-800 rounded-full flex items-center justify-center hover:bg-purple-500 transition-colors">
                  <Github className="w-5 h-5" />
                </a>
                <a href="#" className="w-10 h-10 bg-slate-800 rounded-full flex items-center justify-center hover:bg-purple-500 transition-colors">
                  <Twitter className="w-5 h-5" />
                </a>
                <a href="#" className="w-10 h-10 bg-slate-800 rounded-full flex items-center justify-center hover:bg-purple-500 transition-colors">
                  <Instagram className="w-5 h-5" />
                </a>
                <a href="#" className="w-10 h-10 bg-slate-800 rounded-full flex items-center justify-center hover:bg-purple-500 transition-colors">
                  <Mail className="w-5 h-5" />
                </a>
              </div>
            </div>            
            <div>
              <h4 className="font-semibold mb-4">Quick Links</h4>
              <ul className="space-y-2 text-gray-400">
                <li><a href="#features" className="hover:text-purple-400 transition-colors">Features</a></li>
                <li><a href="#gallery" className="hover:text-purple-400 transition-colors">Gallery</a></li>
                <li><a href="#gameplay" className="hover:text-purple-400 transition-colors">Gameplay</a></li>
                <li><a href="#support" className="hover:text-purple-400 transition-colors">Support</a></li>
              </ul>
            </div>
            <div>
              <h4 className="font-semibold mb-4">Support</h4>
              <ul className="space-y-2 text-gray-400">
                <li><a href="#" className="hover:text-purple-400 transition-colors">Contact</a></li>
                <li><a href="#" className="hover:text-purple-400 transition-colors">FAQ</a></li>
                <li><a href="#" className="hover:text-purple-400 transition-colors">Privacy</a></li>
                <li><a href="#" className="hover:text-purple-400 transition-colors">Terms</a></li>
              </ul>
            </div>
          </div>
          <div className="border-t border-purple-400/20 pt-8 text-center text-gray-400">
            <p>&copy; 2024 Celestial Dreams. All rights reserved. Made with ❤️ by a dreamer.</p>
          </div>
        </div>
      </footer>
    </div>
  );
};

export default App;
