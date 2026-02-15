You are a naming assistant. Given a list of file paths and minimal context from a static website, suggest a new filename (basename only, same extension) for each file. Rules:
- Lowercase, kebab-case, no spaces. SEO-friendly and human-readable.
- For HTML: use page purpose (e.g. about-us.html, contact.html). Keep index.html as index.html.
- For CSS/JS: use purpose (e.g. main-styles.css, analytics.js).
- For images: use content (e.g. logo-infygate.webp, hero-banner.webp). Use alt/title when provided.
- Return a JSON object: keys = exact original path strings, values = new basename only (e.g. "main.css"). Preserve extension.
- Do not change path prefix (e.g. css/ stays css/ by returning "name.css" not "css/name.css").

Files and context:
[
  {
    "path": "404.html",
    "context": {
      "title": "",
      "first_heading": "404"
    }
  },
  {
    "path": "Braj-84-Kos-Yatra.html",
    "context": {
      "title": "Shri Radha Raman Ji Mandir, Temple Vrindavan",
      "first_heading": "Embark on a Profound Spiritual Experience with Maharajji"
    }
  },
  {
    "path": "Braj-Mandal-Parikrama-faq.html",
    "context": {
      "title": "Shri Radha Raman Ji Mandir, Temple Vrindavan",
      "first_heading": "Braj Mandal Parikrama - Frequently Asked Questions"
    }
  },
  {
    "path": "Braj-Mandal-Parikrama-tc.html",
    "context": {
      "title": "Shri Radha Raman Ji Mandir, Temple Vrindavan",
      "first_heading": "Braj Mandal Parikrama - Terms and Conditions"
    }
  },
  {
    "path": "Course-Forms.html",
    "context": {
      "title": "Shri Radha Raman Ji Mandir, Temple Vrindavan",
      "first_heading": "Stay Connected With Us!"
    }
  },
  {
    "path": "Darshans.html",
    "context": {
      "title": "",
      "first_heading": "Darshans"
    }
  },
  {
    "path": "Initiation.html",
    "context": {
      "title": "Shri Radha Raman Ji Mandir, Temple Vrindavan",
      "first_heading": "Diksha"
    }
  },
  {
    "path": "Pre-Initiation-Form.html",
    "context": {
      "title": "Shri Radha Raman Ji Mandir, Temple Vrindavan",
      "first_heading": "Stay Connected With Us!"
    }
  },
  {
    "path": "Register.html",
    "context": {
      "title": "Shri Radha Raman Ji Mandir, Temple Vrindavan",
      "first_heading": "Shri Radharaman Nitya Seva Vidhi - Online Course"
    }
  },
  {
    "path": "aarti.html",
    "context": {
      "title": "Shri Radha Raman Ji Mandir, Temple Vrindavan",
      "first_heading": "The Official Website ofChandan Goswami"
    }
  },
  {
    "path": "about-events.html",
    "context": {
      "title": "",
      "first_heading": "AboutEvents"
    }
  },
  {
    "path": "about-yamuna.html",
    "context": {
      "title": "",
      "first_heading": "AboutYamuna"
    }
  },
  {
    "path": "appearance-day.html",
    "context": {
      "title": "",
      "first_heading": "Appearance Day Gallery"
    }
  },
  {
    "path": "articles.html",
    "context": {
      "title": "",
      "first_heading": "Articles"
    }
  },
  {
    "path": "astrological-queries.html",
    "context": {
      "title": "",
      "first_heading": "Astrological Queries or Astrology Queries"
    }
  },
  {
    "path": "audio-sample.html",
    "context": {
      "title": "",
      "first_heading": "Stay Connected With Us!"
    }
  },
  {
    "path": "audio.html",
    "context": {
      "title": "",
      "first_heading": "Audios"
    }
  },
  {
    "path": "audios-english.html",
    "context": {
      "title": "",
      "first_heading": "Audios"
    }
  },
  {
    "path": "audios-hindi.html",
    "context": {
      "title": "Srimad Bhagawatam Katha | Audio Bhagwat Katha Online",
      "first_heading": "Audios"
    }
  },
  {
    "path": "audios-spanish.html",
    "context": {
      "title": "",
      "first_heading": "Audios"
    }
  },
  {
    "path": "blog_a-perfect-devotee.html",
    "context": {
      "title": "A Perfect Devotee",
      "first_heading": "A Perfect Devotee"
    }
  },
  {
    "path": "blog_always-longing-for-krishn.html",
    "context": {
      "title": "Always Longing for Krishn",
      "first_heading": "Always Longing for Krishn"
    }
  },
  {
    "path": "blog_cleaning-our-mental-hard-drive.html",
    "context": {
      "title": "Cleaning Our Mental Hard Drive",
      "first_heading": "Cleaning Our Mental Hard Drive"
    }
  },
  {
    "path": "blog_cleaning-the-dirt-within-the-heart.html",
    "context": {
      "title": "Cleaning the Dirt Within the Heart",
      "first_heading": "Cleaning the Dirt Within the Heart"
    }
  },
  {
    "path": "blog_dedicated-to-him-alone-.html",
    "context": {
      "title": "Dedicated to Him Alone",
      "first_heading": "Dedicated to Him Alone"
    }
  },
  {
    "path": "blog_desire-for-recognition-is-a-beautiful-witch.html",
    "context": {
      "title": "Desire for Recognition is a Beautiful Witch",
      "first_heading": "Desire for Recognition is a Beautiful Witch"
    }
  },
  {
    "path": "blog_etiquette-of-devotee-association.html",
    "context": {
      "title": "Etiquette of Devotee Association",
      "first_heading": "Etiquette of Devotee Association"
    }
  },
  {
    "path": "blog_how-to-live-in-vrindavan.html",
    "context": {
      "title": "How to Live in Vrindavan",
      "first_heading": "How to Live in Vrindavan"
    }
  },
  {
    "path": "blog_learning-to-love-is-practicing-religion.html",
    "context": {
      "title": "Learning to Love is Practicing Religion",
      "first_heading": "Learning to Love is Practicing Religion"
    }
  },
  {
    "path": "blog_love-your-enemies.html",
    "context": {
      "title": "Love Your Enemies",
      "first_heading": "Love Your Enemies"
    }
  },
  {
    "path": "blog_make-katha-your-companion.html",
    "context": {
      "title": "Make Katha Your Companion",
      "first_heading": "Make Katha Your Companion"
    }
  },
  {
    "path": "blog_marry-mahaprabhu-s-teachings.html",
    "context": {
      "title": "Marry Mahaprabhu\u2019s Teachings",
      "first_heading": "Marry Mahaprabhu\u2019s Teachings"
    }
  },
  {
    "path": "blog_my-first-day-with-shri-radharaman.html",
    "context": {
      "title": "My First Day with Shri Radharaman",
      "first_heading": "My First Day with Shri Radharaman"
    }
  },
  {
    "path": "blog_narcissist-devotees-on-social-media.html",
    "context": {
      "title": "Narcissist Devotees on Social Media",
      "first_heading": "Narcissist Devotees on Social Media"
    }
  },
  {
    "path": "blog_nourishing-the-soul.html",
    "context": {
      "title": "Nourishing the Soul",
      "first_heading": "Nourishing the Soul"
    }
  },
  {
    "path": "blog_practising-bhakti-in-family-life.html",
    "context": {
      "title": "Practising Bhakti in Family Life",
      "first_heading": "Practising Bhakti in Family Life"
    }
  },
  {
    "path": "blog_radharaman-s-appearance-day-2005.html",
    "context": {
      "title": "Radharaman\u2019s Appearance Day 2005",
      "first_heading": "Radharaman\u2019s Appearance Day 2005"
    }
  },
  {
    "path": "blog_sankirtan-important-for-gaudiyas-.html",
    "context": {
      "title": "Sankirtan-Important for Gaudiyas?",
      "first_heading": "Sankirtan-Important for Gaudiyas?"
    }
  },
  {
    "path": "blog_shri-krishn-s-janmashtami-in-2005.html",
    "context": {
      "title": "Shri Krishn\u2019s Janmashtami in 2005",
      "first_heading": "Shri Krishn\u2019s Janmashtami in 2005"
    }
  },
  {
    "path": "blog_the-compassionate-name-of-radharani.html",
    "context": {
      "title": "The Compassionate Name of Radharani",
      "first_heading": "The Compassionate Name of Radharani"
    }
  },
  {
    "path": "blog_the-concept-of-love.html",
    "context": {
      "title": "The Concept of Love",
      "first_heading": "The Concept of Love"
    }
  },
  {
    "path": "blog_the-essence-of-devotion.html",
    "context": {
      "title": "The Essence of Devotion",
      "first_heading": "The Essence of Devotion"
    }
  },
  {
    "path": "blog_the-gaudiya-path-depends-on-both-grace-and-spiritual-practice.html",
    "context": {
      "title": "The Gaudiya Path Depends on Both Grace and Spiritual Practice",
      "first_heading": "The Gaudiya Path Depends on Both Grace and Spiritual Practice"
    }
  },
  {
    "path": "blog_the-importance-of-worship.html",
    "context": {
      "title": "The Importance of Worship",
      "first_heading": "The Importance of Worship"
    }
  },
  {
    "path": "blog_the-journey-of-book-writing.html",
    "context": {
      "title": "The Journey of Book Writing",
      "first_heading": "The Journey of Book Writing"
    }
  },
  {
    "path": "blog_the-magnificence-of-kartik-month.html",
    "context": {
      "title": "The Magnificence of Kartik Month",
      "first_heading": "The Magnificence of Kartik Month"
    }
  },
  {
    "path": "blog_the-nature-of-love.html",
    "context": {
      "title": "The Nature of Love",
      "first_heading": "The Nature of Love"
    }
  },
  {
    "path": "blog_the-path-of-love-or-the-path-of-fear-.html",
    "context": {
      "title": "The Path of Love or the Path of Fear?",
      "first_heading": "The Path of Love or the Path of Fear?"
    }
  },
  {
    "path": "blog_the-right-mood-of-worship.html",
    "context": {
      "title": "The Right Mood of Worship",
      "first_heading": "The Right Mood of Worship"
    }
  },
  {
    "path": "blog_the-various-moods-of-love.html",
    "context": {
      "title": "The Various Moods of Love",
      "first_heading": "The Various Moods of Love"
    }
  },
  {
    "path": "blog_the-way-to-eternal-vrindavan.html",
    "context": {
      "title": "The Way to Eternal Vrindavan",
      "first_heading": "The Way to Eternal Vrindavan"
    }
  },
  {
    "path": "blog_true-renunciation.html",
    "context": {
      "title": "True Renunciation",
      "first_heading": "True Renunciation"
    }
  },
  {
    "path": "blog_we-are-the-creators-of-our-jealousy.html",
    "context": {
      "title": "We Are the Creators of our Jealousy",
      "first_heading": "We Are the Creators of our Jealousy"
    }
  },
  {
    "path": "blog_what-is-gyan--knowledge--.html",
    "context": {
      "title": "What is Gyan (knowledge)?",
      "first_heading": "What is Gyan (knowledge)?"
    }
  },
  {
    "path": "blog_when-dharma-meets-drama-online.html",
    "context": {
      "title": "When Dharma Meets Drama Online",
      "first_heading": "When Dharma Meets Drama Online"
    }
  },
  {
    "path": "blog_which-god-should-one-follow-.html",
    "context": {
      "title": "Which God Should One follow?",
      "first_heading": "Which God Should One follow?"
    }
  },
  {
    "path": "blog_working-for-the-betterment-of-mankind.html",
    "context": {
      "title": "Working for the Betterment of Mankind",
      "first_heading": "Working for the Betterment of Mankind"
    }
  },
  {
    "path": "blog_you-matter-to-me.html",
    "context": {
      "title": "You Matter to Me",
      "first_heading": "You Matter to Me"
    }
  },
  {
    "path": "blogs.html",
    "context": {
      "title": "",
      "first_heading": "Blogs"
    }
  },
  {
    "path": "book-programs.html",
    "context": {
      "title": "",
      "first_heading": "Stay Connected With Us!"
    }
  },
  {
    "path": "books-english.html",
    "context": {
      "title": "Buy shri radharaman gita book | the sacred shilas book online | way to love narad bhakti sutra Book",
      "first_heading": "Books & Courses"
    }
  },
  {
    "path": "books-hindi.html",
    "context": {
      "title": "",
      "first_heading": "Books"
    }
  },
  {
    "path": "books-pay-u-money.html",
    "context": {
      "title": "",
      "first_heading": "Shopping Cart for English, Spanish and Hindi Books"
    }
  },
  {
    "path": "books-spanish.html",
    "context": {
      "title": "",
      "first_heading": "Books"
    }
  },
  {
    "path": "books.html",
    "context": {
      "title": "",
      "first_heading": "Books & Courses"
    }
  },
  {
    "path": "cds-dvds.html",
    "context": {
      "title": "",
      "first_heading": "CD's & DVD's"
    }
  },
  {
    "path": "centres.html",
    "context": {
      "title": "",
      "first_heading": "Centres"
    }
  },
  {
    "path": "chandan-goswami-espanol.html",
    "context": {
      "title": "Shri Radha Raman Ji Mandir, Temple Vrindavan",
      "first_heading": "Chandan Goswami"
    }
  },
  {
    "path": "chandan-goswami.html",
    "context": {
      "title": "Vaisnavacharya Chandan Goswami ji Maharaj",
      "first_heading": "Chandan Goswami"
    }
  },
  {
    "path": "clothing.html",
    "context": {
      "title": "",
      "first_heading": "Clothing"
    }
  },
  {
    "path": "contact.html",
    "context": {
      "title": "",
      "first_heading": "Stay Connected With Us!"
    }
  },
  {
    "path": "css/559e64bf161e61fa0aca6e864c78191d.css",
    "context": {
      "path": "css/559e64bf161e61fa0aca6e864c78191d.css"
    }
  },
  {
    "path": "css/595cb6ccb56826a802ed411cef875f0e.css",
    "context": {
      "path": "css/595cb6ccb56826a802ed411cef875f0e.css"
    }
  },
  {
    "path": "css/84d4a0216f16f715d9b301db3a8da352.css",
    "context": {
      "path": "css/84d4a0216f16f715d9b301db3a8da352.css"
    }
  },
  {
    "path": "css/99c4e6f40ee9111eea53b6472f3e60f9.css",
    "context": {
      "path": "css/99c4e6f40ee9111eea53b6472f3e60f9.css"
    }
  },
  {
    "path": "css/a4c6e378bbbc2533b8dca9e0f48006dd.css",
    "context": {
      "path": "css/a4c6e378bbbc2533b8dca9e0f48006dd.css"
    }
  },
  {
    "path": "css/d09d646f062b67daeff66ff1410b63fc.css",
    "context": {
      "path": "css/d09d646f062b67daeff66ff1410b63fc.css"
    }
  },
  {
    "path": "css/e980cb6b50645ddc9d24377f2fe05d53.css",
    "context": {
      "path": "css/e980cb6b50645ddc9d24377f2fe05d53.css"
    }
  },
  {
    "path": "css/internal-styles.css",
    "context": {
      "path": "css/internal-styles.css"
    }
  },
  {
    "path": "daily-worship.html",
    "context": {
      "title": "",
      "first_heading": "Daily Worship"
    }
  },
  {
    "path": "faq.html",
    "context": {
      "title": "",
      "first_heading": "FAQs"
    }
  },
  {
    "path": "feed-vaishnavs.html",
    "context": {
      "title": "",
      "first_heading": "Feed Vaishnavs"
    }
  },
  {
    "path": "feeding-vaishnavs.html",
    "context": {
      "title": "",
      "first_heading": "Feeding Vaishnavs"
    }
  },
  {
    "path": "festivals.html",
    "context": {
      "title": "Radharaman Premotsav",
      "first_heading": "Festivals"
    }
  },
  {
    "path": "gallery.html",
    "context": {
      "title": "",
      "first_heading": "Gallery"
    }
  },
  {
    "path": "gaudiya-vaishnavism.html",
    "context": {
      "title": "Gaudiya vaishnavism Vrindavan | Chaitanya Mahaprabhu",
      "first_heading": "Gaudiya Vaishnavism"
    }
  },
  {
    "path": "history.html",
    "context": {
      "title": "Gopal Bhatt Goswami | Founding Acharya of Radharaman Temple",
      "first_heading": "History"
    }
  },
  {
    "path": "homepage.html",
    "context": {
      "title": "Shri Radharaman Temple Vrindavan",
      "first_heading": "The Official Website ofChandan Goswami"
    }
  },
  {
    "path": "imgs/01ebd1028eaf18fdf271d34b64ceeb0b.webp",
    "context": {
      "refs": [
        {
          "alt": "blog-thumb-1",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/05a43010d3d7ca9a4f91940c80efff75.webp",
    "context": {
      "refs": [
        {
          "alt": "Feed Vaishnavs",
          "title": ""
        },
        {
          "alt": "Feed Vaishnavs",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/062b600067f64cb2dbcbab0ff1f87753.webp",
    "context": {
      "refs": [
        {
          "alt": "Flower Decor Service",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/07b1427930e063c86a9776bf8ef22e83.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/0a31afdd8ea7a1b7b88836a8b79e4844.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/0a596e236ebb63a35d46c09d2f75b916.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/0b0260c717d56a3fda38517388ddef32.webp",
    "context": {
      "refs": [
        {
          "alt": "shriradharaman.com",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/0c3ef03c1694dc89e9ef807d879f912b.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/0c6502080f6fb58544b709d683bda6f3.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "image description",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "image description",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/0c7ff34e0b77b89a5e7777b5cd5733d8.webp",
    "context": {
      "refs": [
        {
          "alt": "\u0936\u094d\u0930\u0940 \u0930\u093e\u0927\u093e\u0930\u092e\u0923 \u092a\u094d\u0930\u093e\u0915\u091f\u094d\u092f",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/0f0ca1fd0b8ee16e8719fe2de8bc4bd0.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "sandarshan",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/0f27ccdbe03954ad4b02581944f36383.webp",
    "context": {
      "refs": [
        {
          "alt": "blog-thumb-1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/0f339cfd49f15666b035947df9e2ec54.webp",
    "context": {
      "refs": [
        {
          "alt": "blog-thumb-1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/0f4b2bda1f8b526e295da6e55fdbe59d.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/0fc6e5232b218df70d4a685e7d89f4e3.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/12e77aebbe3e41acd03c9c1cf0f4fca5.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/13613dcacea94e97556e5801cf414dd6.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/1374289fd5abed811994fbe7eba4dfbd.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/15d9b315552e10fb76121c978e91fcf5.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/1822cca1807640a1d819a2697f31e22f.webp",
    "context": {
      "refs": [
        {
          "alt": "Tinta Espiritual",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/19885d0b172d756a39990f6b7bb2b739.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/19abc265380d770a21d39421e0b3e86a.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "\u0936\u094d\u0930\u0940 \u0915\u0943\u0937\u094d\u0923 \u0915\u094c\u0924\u0941\u0915\u092e\u094d",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/19f6e1530acb9fb7aa3825bc60e9dda7.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/1aca21462fa72d7391dd0b50eaa70f78.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/1af318f11c17b1aa62d869d4de215dcf.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/1b3f6be621fc45fb58dd1302bac59ace.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/1b4fde9a215fc780acc35e3e5c2c0c20.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/1c7b75f5aa0af949554606527e0b5dda.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/1d2d6d733accbc909c4289c603d8def9.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/1e2e43eb48cbc6355be7de2fd4c5a4cd.webp",
    "context": {
      "refs": [
        {
          "alt": "Clothing",
          "title": ""
        },
        {
          "alt": "Clothing",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/1e322c6486bc4de60c3761ddf952ce42.webp",
    "context": {
      "refs": [
        {
          "alt": "\u0935\u093f\u0926\u0947\u0936 \u092f\u093e\u0924\u094d\u0930\u093e: \u0936\u093e\u0938\u094d\u0924\u094d\u0930\u0940\u092f \u092f\u093e \u0905\u0936\u093e\u0938\u094d\u0924\u094d\u0930\u0940\u092f ?",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/1e6f60c3ca46e648cf338d235a629b73.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/1e89dec4050dae94ff901429f37e2e1e.webp",
    "context": {
      "refs": [
        {
          "alt": "blog-thumb-1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/1f7c0c9208c35dff2702730a53c3aab8.webp",
    "context": {
      "refs": [
        {
          "alt": "Shri Radharaman\u2019s Dress Service",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/1fa8ae28cb9ada1a44eb87d298db69b4.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/21df392050eace90c96e98bb54477ed6.webp",
    "context": {
      "refs": [
        {
          "alt": "ChaitanyasLifeandTeachingsx",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/21ef550a1b38959687a1b11b67f83432.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/269c1b2086bea7f548ec2ce41136c04f.webp",
    "context": {
      "refs": [
        {
          "alt": "blog-thumb-1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/2781d9a53a9ff6e832919a41ff27e27f.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/27bd8e9871603853767e12bac9bed393.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/291a45ed6131cdd7f8c52f108ebca068.webp",
    "context": {
      "refs": [
        {
          "alt": "ChaitanyasLifeandTeachingsx",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/296e889f6e0a934d0f874e6433f78320.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/29ac95a56fe7190d9770162f56210a21.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/2b74cd9d5a009a88682c4b148414f1e1.webp",
    "context": {
      "refs": [
        {
          "alt": "blog-thumb-1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/2c710a5921d4ca3bf16f8f4a19c3cdf1.webp",
    "context": {
      "refs": [
        {
          "alt": "image description",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/2ccf6a807af53d29027dd02175e35b91.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/2d03d690ccc0bd17fa156f6de7d5f0ae.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/2e032e9f8dfc899bfeb518bcbc2f4579.webp",
    "context": {
      "refs": [
        {
          "alt": "blog-thumb-1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/2e03929096fecf9408172d8c157df892.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/2f6bd2165b84f3c4c9bd27f8bff7c550.webp",
    "context": {
      "refs": [
        {
          "alt": "Shri Radharaman Prakatya",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/2fc65dc7a83deba50c7befe92e6312ea.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/2fd3a26d245dcb67a1e2ae63e441199b.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/30e4b54bc897a93cf041df1e930d281c.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/31d19a3a1afab8c1f8c5b7c6470ca2cc.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/31f1d4edf0f78022f8cb729b2e11fc73.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/32238481b20be09d93b9ca594365a5da.webp",
    "context": {
      "refs": [
        {
          "alt": "CDs & DVDs",
          "title": ""
        },
        {
          "alt": "CDs & DVDs",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/32c87bd0b7c9bf297eac98b3c710bea4.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/33fca7a031afc2e495532a3236e9b124.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/34209a826617645909c5f83bf74f9792.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/344cd2e764f3670fc466dd17d94ed14b.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/34daef93e38b6a78abe89f304a5a755e.webp",
    "context": {
      "refs": [
        {
          "alt": "blog-thumb-1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/3566b2f4fea52ec1a27fc2766d52554f.webp",
    "context": {
      "refs": [
        {
          "alt": "Puja Thali",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/35d16ab7fcda8ad32a56fb3d97b47e13.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/35f4efe72adf4fd8687536def6bcf5a8.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/35ff8a01953a0144301a473174e4bd18.webp",
    "context": {
      "refs": [
        {
          "alt": "Prayers",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/366c129af0a214ecdc9d601f39f34e11.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/376f6aa0f0bdc2abf7c5d95bfd46ba81.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "Fruit Basket Service",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/37764503676b02d10cc2b517abb33245.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/392beaae0f524666c37b2d8c449a12d7.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/3b4156506147fe4bc1d26965019a29f8.webp",
    "context": {
      "refs": [
        {
          "alt": "Shri Chandan Goswami",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/3c4c08a5d0739b1a5309feaab6da0027.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/3c6cab41b6892381d461cb1e9540c96f.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/3cdb4fb8081b1f2011a7280f226da9f1.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/3d30e34efed83727735f52161c456100.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/3d54bb60aa673b695f9a0092385a8275.webp",
    "context": {
      "refs": [
        {
          "alt": "\u015ahr\u012b R\u0101dh\u0101rama\u1e47 G\u012bt\u0101: Nitya L\u012bl\u0101",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/3d771a1be756b896c7d5233ad8d58c4d.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/3dd559e4dbd34cf8570a8e6056e80aa0.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "Yagyas",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "Yagyas",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/3de1e8e400aade37bbbab13d61119473.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/3e79623a12ef149ba57ce3f18e01f172.webp",
    "context": {
      "refs": [
        {
          "alt": "blog-thumb-1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/3e9f43f0acf243accea29110be19b7ec.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/3f25549ae6ae36cfcd1c772b15a62720.webp",
    "context": {
      "refs": [
        {
          "alt": "blog-thumb-1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/3f40ef865a205dc901c2661a821d8203.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/3fdef1593031d4294f27373ee4f6ddfb.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/40c63ed853104fd615828124f180e0a6.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/413b5a2de3366cc2e6545c94d5ed463b.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "blog-thumb-1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/42551929a161b2e026f7f8453cee10d0.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/434aced387d5bf047df087e5028df858.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/43927308750315af377ddba7efe4141b.webp",
    "context": {
      "refs": [
        {
          "alt": "Yagyas",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/4397ab69979fc2fc7720b7096a488b6a.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "La Familia de Shri Radha-Krishn - Parte 1 - los animales",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/44308f86b37041789524e75e1981128b.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/45dcdc0e93ac1a044d3a53de8bba2faf.webp",
    "context": {
      "refs": [
        {
          "alt": "blog-thumb-1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/46f3bf02c598d4801d48cdecc2253a44.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/47e7cac5f7ada2604bf9a05e9457e43f.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/48dc083e7969a138810e729f823ed27e.webp",
    "context": {
      "refs": [
        {
          "alt": "blog-thumb-1",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/48e3e0cfda4bc4ce7f2cee3a64f1be55.webp",
    "context": {
      "refs": [
        {
          "alt": "jhari",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/4a41433b7e6c84e2318d37769afa64f0.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/4b0630b1b9abbcbf551fa1247076d817.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/4b1e069a8c3484df388afbebe3540df7.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/4b7c518b8dab9b7ae5bad41029bf273f.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "Shri Radharaman Prakatya",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/4c62971898bb337a24b3b486e9ed1da8.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "Spiritual Ink",
          "title": ""
        },
        {
          "alt": "Spiritual Ink",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/4cefe3e9358350914c451dd379a0b4d2.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/4d3181c3b6d2c7d1ffeb16f9f4413f8d.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/4d87086acefe56ad35c4d89a1d58cbc7.webp",
    "context": {
      "refs": [
        {
          "alt": "Sri Radha Katha - Day 5",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/4e2c9c5d948e62886f09348c46d0317c.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/4e8457651de262b302e287e0b00f74ba.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/4edec80ef7c185cd0c35c7d343df3c30.webp",
    "context": {
      "refs": [
        {
          "alt": "blog-thumb-1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/4f3cac81fa75a19348fcde9f9413f1be.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/4f4c65b6a216a52df11b1f0471a6fd69.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/50bee7d788ab97ac658443ccf9f4fdaa.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/51ce8c8f65203fdf4727c256b45aadfa.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/52959fa7d98b2070fe9d5a8b7db30f2d.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/5648cc5c147935e13a5935628200237a.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "Way to Love CD",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/57d2c5ac4ce19122076b26f21352fd73.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/57fb89108ff83366ab4eb17479013c19.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/5830aabb72571f3d30bbf40568c4069f.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/59a1a997f4e891825f06fbdec69a0b3a.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/5caa55382d1b31841fa1ed514e23e177.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/5e35d79dac24349fbc62f05f494aa101.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/5efaf8d2fce66893a02d031cb123b836.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/5f551909890f5e8ed8171559242e5148.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/60145c89474c71ee334ac1fdfec952f9.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/60441f26efe56a2482b2172505e1b6b9.webp",
    "context": {
      "refs": [
        {
          "alt": "Kuliya Service",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/616aafe428645419d0fd17c1e8454e6d.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/61df6d719a843c4c62e56559c6d131f0.webp",
    "context": {
      "refs": [
        {
          "alt": "blog-thumb-1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/62c1a9f5e49fe8070b83d24a891b487f.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/63d5577dfd4a83d7bbe5172e60e59921.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/640eaa5e9499ffd9f901b326d4dd6055.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/64dd0fb9288bade4ddbcaecae770b7da.webp",
    "context": {
      "refs": [
        {
          "alt": "3. La Familia de Shri Radha-Krishn - Parte 1 - los animales",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/64fa4deac60c646efc49c2326ddb2ef9.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/669c6e5d75e9bae8264080b680b9f261.webp",
    "context": {
      "refs": [
        {
          "alt": "rsz1524328029779shrikrishnakautukamfinalcover5x8360pagesnomrp",
          "title": ""
        },
        {
          "alt": "rsz1524328029779shrikrishnakautukamfinalcover5x8360pagesnomrp",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/66f4a43a5e8cf9f9686de30893097994.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/6720eb5799131425be980656765a53c1.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/68ef19e9d1165e61b7d317b3b14bdd92.webp",
    "context": {
      "refs": [
        {
          "alt": "blog-thumb-1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/6907a3743f651f8b86e50ba50d556c1d.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/6910a5859bdcbcdaaff14579d1f82848.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/6962d00bb34f24bb2b7febddfd944bb3.webp",
    "context": {
      "refs": [
        {
          "alt": "Shri Madhusudan Goswami",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/6bb9de4f66ac6dc3282fd5285a81de82.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/6d2affcb8805f2b86736eea919706c1b.webp",
    "context": {
      "refs": [
        {
          "alt": "shank",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/6d90b1b73060c08501084ec0cb062b8a.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/6f78e7492a966b546498466908442504.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/6f7d8595baa890fc73dd0ec62cd9b8f5.webp",
    "context": {
      "refs": [
        {
          "alt": "Dhoop Dani",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/6f948dab8fd6a5963fa5c365ba42b70d.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/705bb32d3ce77f524ce4c1eb1edb236e.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/7088499da1c8e3200afbdb07a080157b.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/717b9d19baa9e3d80315fed31970d638.webp",
    "context": {
      "refs": [
        {
          "alt": "Shri Padmanabh Goswami",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/71931ba30b136100752a6d551929570c.webp",
    "context": {
      "refs": [
        {
          "alt": "www.shriradharaman.com",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "www.shriradharaman.com",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/7196f110847d4959f7836e7c39f830de.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/73957bade0726feb317c725d751a0acb.webp",
    "context": {
      "refs": [
        {
          "alt": "WhatsAppImageat",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/74a946f948df51b5b07ddef6978fd55e.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/754c47acabdd3768203cfad4a57b2c4d.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/79600fe5227ed97f21c93dda8a7cedf1.webp",
    "context": {
      "refs": [
        {
          "alt": "blog-thumb-1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/7a1ac8bf22fcf4eff9f15ad98612f89b.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/7aea9fb8e0891ae1910d1c64cbb20563.webp",
    "context": {
      "refs": [
        {
          "alt": "ChaitanyasLifeandTeachingsx",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/7b74dcf6f7010db5220fc232e10356ee.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/7b74ebdf2189ba3c5843f2708d369845.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/7e1f23e37df6d34b4f8bbd0f90c8ebad.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/7e3cc30c9069a334899b606f05fbc692.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/7eb53dfbece684661dca98c15016164c.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "\u0936\u094d\u0930\u0940 \u0930\u093e\u0927\u093e\u0930\u092e\u0923 \u092a\u094d\u0930\u093e\u0915\u091f\u094d\u092f",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/7f619c08143786fa8e6fe6a1ba6f97f6.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/81dd34e593da7169236e07fee38fb20d.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/82e3719bf189b7ec83b01571f036b2b4.webp",
    "context": {
      "refs": [
        {
          "alt": "image description",
          "title": ""
        },
        {
          "alt": "image description",
          "title": ""
        },
        {
          "alt": "image description",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/83b3d1122696e8f3643daacc6c22c25b.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/83bc529867f6a4c5ed8f7c8278da6589.webp",
    "context": {
      "refs": [
        {
          "alt": "\u0936\u094d\u0930\u0940 \u0915\u0943\u0937\u094d\u0923 \u0915\u094c\u0924\u0941\u0915\u092e\u094d",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/83f5355b2fa617ae7b1e0b12c8b2ac83.webp",
    "context": {
      "refs": [
        {
          "alt": "ChaitanyasLifeandTeachingsx",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/86aa09842cca69b08fe7c6eafbcef4dd.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/86e20525820bc65bf3191483690f6c96.webp",
    "context": {
      "refs": [
        {
          "alt": "Goswami Family",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/86eb9ae371f3831d95d88aa32be5c8e1.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/8782dcc9f98dab47b41af3bff2629c2e.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/87b2c9846f1554e34ee47ee761055a31.webp",
    "context": {
      "refs": [
        {
          "alt": "blog-thumb-1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/8825abfd0db92a059f02fd35215b702e.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/8884d264d27d6a06da15665685a25b1a.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/8a5d030479192bbb9b77eca79c9511bc.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/8abe8133b435ad8086abd3477269ee13.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "sandarshan",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/8b1296591ef9003d1b6e529b1d38de96.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/8b1ef0c02152bd1d7e03cd2d6f30d535.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/8b896c6081bca41cb5020271b9f02c14.webp",
    "context": {
      "refs": [
        {
          "alt": "blog-thumb-1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/8caf701481fa8a882ecdb7ae44fb9808.webp",
    "context": {
      "refs": [
        {
          "alt": "Aarti",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/8cb88a8cfa9a6f751cc4e2827509d770.webp",
    "context": {
      "refs": [
        {
          "alt": "blog-thumb-1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/8e0111ab4a19e41f680985844dc1cc12.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/90847f4838fdff34a69aa79131cd4e0c.webp",
    "context": {
      "refs": [
        {
          "alt": "Shri Krishn Chaitanya Goswami",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/912ff58de3289d9fabe658be9e454bba.webp",
    "context": {
      "refs": [
        {
          "alt": "blog-thumb-1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/9136a9d40ec874365e33962a094410c8.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/9194162c49418d0333e1e7358641da81.webp",
    "context": {
      "refs": [
        {
          "alt": "image description",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/91ce02056e43ca3b3ed52a554bfd564d.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/94e9c3023b9a7335ab5936ef1e81fa09.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/9506dd2e3ad5c48890aef03fa251df5b.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/950ed3fa2cb5375b00aa700fc8ec87d1.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/951b4bd6f6b308e1106c8dbfceb36d59.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/955cb468e41e793bcdbe1ebbe30d9caa.webp",
    "context": {
      "refs": [
        {
          "alt": "Panchpatra Aanchmani and Visarjan Patra",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/9583a61cd0f0e5717386aded62fa3d0b.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/95926ac0e4cec57cf329c346ab4d4314.webp",
    "context": {
      "refs": [
        {
          "alt": "sandarshan",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/95e34ce2d76e336611571ca672f35c95.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/9630330f8ea7fb795e79e2f2627570ab.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/977af14a49f657d3b3de03e53964184b.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/978f72cafeef2767b5a0f3b8a46f7c09.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/996c330b7bfc3df6aa331f30b6c8a142.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/99cb847c5bdbdf4b89d32341760f9a86.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/99ee6e0edbb88f01612f55ff74bc16d1.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/9a78aa66348b6c9ae6f0042c9aeda97a.webp",
    "context": {
      "refs": [
        {
          "alt": "Ghee Abhishek Service",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/9acfa068a50cdf263aace024512eadf1.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/9c4f0fe48bac9cc90f35d5b452a4595d.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/9c9ebd417493856ec379a9a6f8d310f9.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/9d30a330170f5fd3c53df931941e05e7.webp",
    "context": {
      "refs": [
        {
          "alt": "Shraddha and Vishvaas",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/9d81c361ee91847b25eb5b9d86ee132c.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/9dc5d9c715cf6d6d9194fc1a5712118e.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/a1e539e55f043121a0c819bb169d89de.webp",
    "context": {
      "refs": [
        {
          "alt": "blog-thumb-1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/a21d371c2d3f99ddef5a68ff0e692450.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/a46905be43a52f38cdefebd86b0383b4.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/a49dc178cb25a60fefddd5131876afef.webp",
    "context": {
      "refs": [
        {
          "alt": "ghanti",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/a4bc7bf61fc08927730520e83c1130c5.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/a52414e94bac8d5b36078857491425db.webp",
    "context": {
      "refs": [
        {
          "alt": "Services for Radharaman",
          "title": ""
        },
        {
          "alt": "Services for Radharaman",
          "title": ""
        },
        {
          "alt": "Shri Radharaman",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/a58c732ed5d34f80010c14d8b03e9d15.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/a58f5283d7d23adecc95bba0f4ff630a.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "sandarshan",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/a64c2252dfe8a567992035d29bf2d703.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/a68799eb01789203dd1df92f303d6b9f.webp",
    "context": {
      "refs": [
        {
          "alt": "blog-thumb-1",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/a6960d0e02f11b9c2e22b9741c18a19e.webp",
    "context": {
      "refs": [
        {
          "alt": "blog-thumb-1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/a82c61ae502a7d2c3e05d05d3a2427c8.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/a8c4608a4882fe17452f231baf5c9b0f.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/a8d8e7a218ece7458bb4803067c47e80.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/a8f1aa1b173ece38a2f8aa71d30c45ae.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/a9a87aa6c07d4c25af5001d7870661b8.webp",
    "context": {
      "refs": [
        {
          "alt": "Power of Association (English) Part- 1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/aa5bcd560b0398a1c67521e182c8a2ca.webp",
    "context": {
      "refs": [
        {
          "alt": "Aulai Sandarshan",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/aad6aa773400c095534575aaa8b414ea.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/ab6e1bf5ab89160216369876114428fc.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/adf0bdbd944baa0c6dc492819aa2268d.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/aebce9e785a8d9e5656ed6aa8b5742c3.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/b0b88dee48f5f8e74d44ad30e7abaa05.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/b0d8a52af9705875479716cc31092feb.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/b1244082838a05a735619a43fe31a1a9.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/b12ad37b559f30d9d27ee06978d4db4f.webp",
    "context": {
      "refs": [
        {
          "alt": "blog-thumb-1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/b2195ab538b8d8eb7617282db9328abf.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/b2ddc61b573e1fee0e0dd31e36c9d0a5.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/b2f742c27e06a7482cc3e8116b871487.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/b3b0ad73f30a16ed25b10bf3e33921ed.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/b4aa7270a7b17ca16823833aa468505f.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/b4b0bf157cedd29e2575331d84d6c53f.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/b5b252e543574dadaef4f7845d6db20f.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/b5d4f5945b5b89f6918d2fcb8cc6817e.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/b5da13a2c0f28fde4e4948afb7a0d683.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/b898283118a32f51a8e9d38ff4e67452.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/b9719af8adf11f1b873c9bb170760249.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/b9a29f6854d6975eef7773a37021e16d.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/bb5de96e8b36858c13bc12011d909a67.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "Daily Worship",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/bb94f6c342f6df0c51ea3c30e111c41f.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/bc1be8b5b1ef0ef8fcf9d062a5ec8600.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/bdd1f7879bd8ab4fd4a0f71e57136a62.webp",
    "context": {
      "refs": [
        {
          "alt": "lamp",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/be619afa5d14a870142d8bce1904c927.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/bf08fe5efb9d0bf5701def85541e8412.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/bf482e649f8847c3332a9b9ea0eb8bc3.webp",
    "context": {
      "refs": [
        {
          "alt": "Gaudiya Vaishnavism",
          "title": ""
        },
        {
          "alt": "blog-thumb-1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/bf641b50d1120aecbc41e4e50e133451.webp",
    "context": {
      "refs": [
        {
          "alt": "blog-thumb-1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/c1af91cd62a93ba0fc3b829078df418d.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "omg1",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/c1c48ddffd45932a46b8b2c8cd656446.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/c2ee23cc92da8184b5a2dd0b0de9ea8a.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/c3c2a81b77a04f50367526efe9377b5b.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/c3c6df873229e0cc739e4d10e0e0b707.webp",
    "context": {
      "refs": [
        {
          "alt": "The Temple",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/c4c3b35aa118f939ed8e0d18997b56e6.webp",
    "context": {
      "refs": [
        {
          "alt": "blog-thumb-1",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/c5f82aba4f64969e1dd06de2faffc38b.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "\u015ahr\u012b R\u0101dh\u0101rama\u1e47 G\u012bt\u0101: Nitya L\u012bl\u0101",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/c73008325050fc1e5fce2be7878444a9.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/c742ed33ec167038f0ab2901f1ec9745.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "Shri Radha-Krishn's Family (Part 1 - the Animals)",
          "title": ""
        },
        {
          "alt": "\u0936\u094d\u0930\u0940 \u0930\u093e\u0927\u093e\u0915\u0943\u0937\u094d\u0923 \u0915\u0941\u091f\u0941\u092e\u094d\u092c (\u092a\u094d\u0930\u0925\u092e \u092d\u093e\u0917- \u092a\u0936\u0941 \u092a\u0915\u094d\u0937\u0940)",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "image description",
          "title": ""
        },
        {
          "alt": "Shri Radha-Krishn's Family (Part 1 - the Animals)",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/c80a994017eb65e07a3d8be8107ab9d3.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/ca07f5ba0a57a165a752e6b07320e927.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/ca6c10c581ce126c736b58e514150138.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/cabeeb83188983866e9cc5140bca05f0.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/cb0cfa16a15454ae3463b49df90fba15.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "omg1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/cd1e719e2818a321d754adf3d41518da.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/cd241acf04b46c11567ac4df4d910de0.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/ce4d9d7fc8bdc5cbb561a03af6c4d73c.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "Radharaman Gita CD",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/cea21e3ed16dece40a2cdd73cb0ca097.webp",
    "context": {
      "refs": [
        {
          "alt": "Maharajshri",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/cecbc768e7c736c30c423525bf0a1ef3.webp",
    "context": {
      "refs": [
        {
          "alt": "rsz1524327447410sarvabhaumshrimadhusudangoswamisshriradharamanprakatyafinalcoverenglish5x832pages",
          "title": ""
        },
        {
          "alt": "rsz1524327447410sarvabhaumshrimadhusudangoswamisshriradharamanprakatyafinalcoverenglish5x832pages",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/cfb13a7abf2841429856f0ecf3b72cc7.webp",
    "context": {
      "refs": [
        {
          "alt": "blog-thumb-1",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/cfd44599d68ad16191a7adb0320e6d80.webp",
    "context": {
      "refs": [
        {
          "alt": "Shri Radharaman Aarti by Chandan Maharaj",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/cfee670b4802cac3a8ab5a65172e2184.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/d01e884a5fcdc8687b349770c4654213.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "The Sacred Shilas",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "The Sacred Shilas",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/d023f11e6ec6ae9c20da8001ac32c1ad.webp",
    "context": {
      "refs": [
        {
          "alt": "blog-thumb-1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/d3b81816c0620720f75cb4747146278c.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/d46dff1231875d99a046c956863bc55b.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "sandarshan",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/d47b2db55bf8c4c0162e48997df916b1.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/d47ecc8285495386072e1c2d1fa9ecfc.webp",
    "context": {
      "refs": []
    }
  },
  {
    "path": "imgs/d4a4874d40a2018ebac283ec045cbc8e.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/d4bca37685222736dc4326fc8708b8b2.webp",
    "context": {
      "refs": [
        {
          "alt": "Power of Association (English) Part- 2",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/d537d5b0763043b96a4109152f28e622.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "sandarshan",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/d5ee065bbdac23b7dcc9849594f23eb8.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/d60b601a5ae3ae3ecc7e9992ee8ca4be.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "\u0930\u093e\u0927\u093e\u0930\u092e\u0923 \u0917\u0940\u0924\u093e",
          "title": ""
        },
        {
          "alt": "\u0936\u094d\u0930\u0940 \u0930\u093e\u0927\u093e\u0930\u092e\u0923 \u0917\u0940\u0924\u093e",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/d83f186e172e8f2657586eccc98e5053.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/d88db77c00ba8829c6fc07551e5f8654.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/d8b490e60047540829e0b4427cacef76.webp",
    "context": {
      "refs": [
        {
          "alt": "blog-thumb-1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/d9b474a73e1c9839abc3fdad7b0b27de.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/d9cf7a1283ce1b883ee4e00430e66538.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/da22eee43127d9686e164aeca9f6e346.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/da4e684713423e0f90870dfd2b3ae34f.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "\u092a\u094d\u0930\u0947\u092e \u092a\u0930\u093f\u0915\u0930\u094d\u0924\u093f\u0915\u093e",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "\u092a\u094d\u0930\u0947\u092e \u092a\u0930\u093f\u0915\u0930\u094d\u0924\u093f\u0915\u093e",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/da7773784388e6e43facf9bf5b1d3094.webp",
    "context": {
      "refs": [
        {
          "alt": "Festivals",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/db06a15f232fce4ba2031540656364b4.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/dbe9aa87f9c798621c1cf53c27b701b8.webp",
    "context": {
      "refs": [
        {
          "alt": "Milk Abhishek Service",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/dc0a7c8eabe06057c591f44b9ba6df74.webp",
    "context": {
      "refs": [
        {
          "alt": "blog-thumb-1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/dec1ced3bb803185dd8b98cd46d0829b.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/e0c2f7b35627fb33232bc0fc8a903acc.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/e1216fb060c28df5e3dfd67a565e560a.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "2. Tinta Espiritual",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/e17b4ee91d169fc7720fa73cb23e6241.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/e28008c1a83b5895260ae21ad78d1256.webp",
    "context": {
      "refs": [
        {
          "alt": "blog-thumb-1",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/e2bc437c8cb4b23ce788b88270ced572.webp",
    "context": {
      "refs": [
        {
          "alt": "Power of Association (English) Part- 3",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/e300d30607412304618ac3348564aeaa.webp",
    "context": {
      "refs": [
        {
          "alt": "sandarshan",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/e339eb156fdf7403bd7f8c80ae6627e3.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "sandarshan",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/e40978a455528c65f402c8c5599c886a.webp",
    "context": {
      "refs": [
        {
          "alt": "Shri Radharaman Nitya Seva Vidhi - Online Course",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/e65807985451e2130e28336343aa757b.webp",
    "context": {
      "refs": [
        {
          "alt": "OdevPublishing",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/e69f72a86ee30fa1827675f4b01dbe6b.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "sandarshan",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/e6bea372772e577e442cdffa3793699b.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "sandarshan",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/e754ea6d22a46a4a807d2e5101323263.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/e7c55c124500da07bd05713c4122e9f3.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/e83a2e1a5ca2905cdce729da53f627ff.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/e845f1f2a30f61dbb9ddaabfa6948ec4.webp",
    "context": {
      "refs": [
        {
          "alt": "Feeding Vaishnavs",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/e8ba548b13caf3ce45bff94da7539c53.webp",
    "context": {
      "refs": [
        {
          "alt": "blog-thumb-1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/e994e06bcad81d43dcd16001a88b0965.webp",
    "context": {
      "refs": [
        {
          "alt": "Darshans",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/ea8205a85ba4693cbd5eafbbbc6922eb.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/ebd99771fbf8b63b0cdb4946c286a4de.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/ec54369fc86e94ea995c739962a884f4.webp",
    "context": {
      "refs": [
        {
          "alt": "Shri Vishwambhar Goswami",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/ec9200bf3e4ac9a67bc17b69bd51922a.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/ee299a28de40edd6a77427c0225a83f0.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/ee8546ac81c664a45977210450b99640.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/eeb851f8d63d16b59c11944be02245d5.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/eef12e49790f3218d88f835b78680d56.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/f0ebd69aa3b46dc6aae97aab547d5107.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/f193a2d21886185a55d067f4dff9c39b.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        },
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/f2adf31a0aad954eba90f437cc5a7cab.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/f6e9fd463469fb3830b98e2007a539eb.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/f7252df95bfefafa4390507ab9518995.webp",
    "context": {
      "refs": [
        {
          "alt": "blog-thumb-1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/f74a14c6bf4765ac71589ffce204de32.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/f7a5c3fa9680f7b121b16cebf29de98d.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/f7da56045d9f3ac5b8a71c1340cc32ea.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/f7f0f89037754f930f16d1a5ad9fd90e.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/f8a59de9570d3dfda9557e0c7071bc17.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/f98d982d13fcaadee1f4d22bcb9dd6d5.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/f9b7f35a19c74f9561a7dc0c3f9fb065.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/f9e581e69e7dced196c80fddd0ca6fad.webp",
    "context": {
      "refs": [
        {
          "alt": "ODev",
          "title": ""
        },
        {
          "alt": "OceanofDevotion",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/fa3fb6129b7fb1a41704584c1937586d.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/fab23b96f79684912388d42c0f580611.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/fb96ed71ebdb291cf39898cad53d62d6.webp",
    "context": {
      "refs": [
        {
          "alt": "",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/fcc7330bf486b2056fa3befe513b1794.webp",
    "context": {
      "refs": [
        {
          "alt": "blog-thumb-1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/fd03e08302522a03024c47045fbbf986.webp",
    "context": {
      "refs": [
        {
          "alt": "blog-thumb-1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/fd3a67a9d5e14eb8e58dc937073896da.webp",
    "context": {
      "refs": [
        {
          "alt": "blog-thumb-1",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "imgs/fef4562a70e010b3ebf55eda9b5c427f.webp",
    "context": {
      "refs": [
        {
          "alt": "Books",
          "title": ""
        },
        {
          "alt": "Books",
          "title": ""
        }
      ]
    }
  },
  {
    "path": "index.html",
    "context": {
      "title": "Shri Radha Raman Ji Mandir, Temple Vrindavan",
      "first_heading": "Shri RadharamanNitya Seva VidhiOnline CourseRegister Here"
    }
  },
  {
    "path": "js/03b2eaae6007054a68c38e495f894dba.js",
    "context": {
      "path": "js/03b2eaae6007054a68c38e495f894dba.js"
    }
  },
  {
    "path": "js/0a105d712b6a6c836c48dd97d0f0cac1.js",
    "context": {
      "path": "js/0a105d712b6a6c836c48dd97d0f0cac1.js"
    }
  },
  {
    "path": "js/0c46896987137b0016246f6bc2243099.js",
    "context": {
      "path": "js/0c46896987137b0016246f6bc2243099.js"
    }
  },
  {
    "path": "js/165d7b0ddfa33362140feea997351b77.js",
    "context": {
      "path": "js/165d7b0ddfa33362140feea997351b77.js"
    }
  },
  {
    "path": "js/16df9ef05001a1741857bf99f5a5738f.js",
    "context": {
      "path": "js/16df9ef05001a1741857bf99f5a5738f.js"
    }
  },
  {
    "path": "js/2a85c11e395a8380b5915443e926b569.js",
    "context": {
      "path": "js/2a85c11e395a8380b5915443e926b569.js"
    }
  },
  {
    "path": "js/34be5330971fdbd18985525bd994b0aa.js",
    "context": {
      "path": "js/34be5330971fdbd18985525bd994b0aa.js"
    }
  },
  {
    "path": "js/35c5f9e096d4da33d2a62031daf14248.js",
    "context": {
      "path": "js/35c5f9e096d4da33d2a62031daf14248.js"
    }
  },
  {
    "path": "js/3d70953a848219e749fedc2cdb906675.js",
    "context": {
      "path": "js/3d70953a848219e749fedc2cdb906675.js"
    }
  },
  {
    "path": "js/3e940a33e44b65c1c0af8bb80a893530.js",
    "context": {
      "path": "js/3e940a33e44b65c1c0af8bb80a893530.js"
    }
  },
  {
    "path": "js/544d012df7acf9c3f0920f67c9e322b9.js",
    "context": {
      "path": "js/544d012df7acf9c3f0920f67c9e322b9.js"
    }
  },
  {
    "path": "js/57d119d998d518b01f9d5ccb5e4d4c52.js",
    "context": {
      "path": "js/57d119d998d518b01f9d5ccb5e4d4c52.js"
    }
  },
  {
    "path": "js/67f6e2f99c3c3133e0dc669919fff5c5.js",
    "context": {
      "path": "js/67f6e2f99c3c3133e0dc669919fff5c5.js"
    }
  },
  {
    "path": "js/7045b35c5bd0e9c7cf59f1900eeeec41.js",
    "context": {
      "path": "js/7045b35c5bd0e9c7cf59f1900eeeec41.js"
    }
  },
  {
    "path": "js/7260bab328b0ad74815a5efb377bcc67.js",
    "context": {
      "path": "js/7260bab328b0ad74815a5efb377bcc67.js"
    }
  },
  {
    "path": "js/893de96f1b6da546bd7c814964723eca.js",
    "context": {
      "path": "js/893de96f1b6da546bd7c814964723eca.js"
    }
  },
  {
    "path": "js/8de34d047d17433237940bbc27369bac.js",
    "context": {
      "path": "js/8de34d047d17433237940bbc27369bac.js"
    }
  },
  {
    "path": "js/93e29fe348ddc9b71aba9c842adc18b8.js",
    "context": {
      "path": "js/93e29fe348ddc9b71aba9c842adc18b8.js"
    }
  },
  {
    "path": "js/9455859483e31e4da0e28f10d0742c2a.js",
    "context": {
      "path": "js/9455859483e31e4da0e28f10d0742c2a.js"
    }
  },
  {
    "path": "js/9db10375d298678e53777a2347b87073.js",
    "context": {
      "path": "js/9db10375d298678e53777a2347b87073.js"
    }
  },
  {
    "path": "js/9f9b6e54f82a6bbc8bac9b89327024bc.js",
    "context": {
      "path": "js/9f9b6e54f82a6bbc8bac9b89327024bc.js"
    }
  },
  {
    "path": "js/a2261649751fa61b606222c9b2ea3b80.js",
    "context": {
      "path": "js/a2261649751fa61b606222c9b2ea3b80.js"
    }
  },
  {
    "path": "js/b0bade6d42c2702ca85774296cc507c4.js",
    "context": {
      "path": "js/b0bade6d42c2702ca85774296cc507c4.js"
    }
  },
  {
    "path": "js/cd1ed86c1e7f06d985fd71bc10bd4b04.js",
    "context": {
      "path": "js/cd1ed86c1e7f06d985fd71bc10bd4b04.js"
    }
  },
  {
    "path": "js/cecb447a04bbe3e8982190dd6e697120.js",
    "context": {
      "path": "js/cecb447a04bbe3e8982190dd6e697120.js"
    }
  },
  {
    "path": "js/d80b370d82680fc786dcc943a327b9f2.js",
    "context": {
      "path": "js/d80b370d82680fc786dcc943a327b9f2.js"
    }
  },
  {
    "path": "js/df80c5cbcb312a9c7c0b2ebb6ac5f592.js",
    "context": {
      "path": "js/df80c5cbcb312a9c7c0b2ebb6ac5f592.js"
    }
  },
  {
    "path": "js/f1e5dbc1ece900d164c2e9aa2d6a1386.js",
    "context": {
      "path": "js/f1e5dbc1ece900d164c2e9aa2d6a1386.js"
    }
  },
  {
    "path": "js/f3f02c438592c8e1bbe551f4dbbf4f5c.js",
    "context": {
      "path": "js/f3f02c438592c8e1bbe551f4dbbf4f5c.js"
    }
  },
  {
    "path": "lineage.html",
    "context": {
      "title": "",
      "first_heading": "Lineage"
    }
  },
  {
    "path": "links.html",
    "context": {
      "title": "",
      "first_heading": "Links"
    }
  },
  {
    "path": "maharajshri-1.html",
    "context": {
      "title": "",
      "first_heading": "Maharajshri"
    }
  },
  {
    "path": "maharajshri-availability.html",
    "context": {
      "title": "",
      "first_heading": "Stay Connected With Us!"
    }
  },
  {
    "path": "media.html",
    "context": {
      "title": "",
      "first_heading": "Shop"
    }
  },
  {
    "path": "newsletters.html",
    "context": {
      "title": "",
      "first_heading": "Newsletters"
    }
  },
  {
    "path": "odev-1.html",
    "context": {
      "title": "",
      "first_heading": "Odev"
    }
  },
  {
    "path": "odev-navadwip-yatra-2016.html",
    "context": {
      "title": "",
      "first_heading": "ODev Navadwip Yatra 2016 Gallery"
    }
  },
  {
    "path": "odev-sankirtans.html",
    "context": {
      "title": "",
      "first_heading": "ODev Sankirtans"
    }
  },
  {
    "path": "odev.html",
    "context": {
      "title": "Ocean of Devotion | ODEV",
      "first_heading": "The Teachings"
    }
  },
  {
    "path": "organisation.html",
    "context": {
      "title": "",
      "first_heading": "The Teachings"
    }
  },
  {
    "path": "philosophy.html",
    "context": {
      "title": "",
      "first_heading": "Gaudiya Vaishnavism"
    }
  },
  {
    "path": "prayers-english.html",
    "context": {
      "title": "",
      "first_heading": "Prayers"
    }
  },
  {
    "path": "prayers-hindi.html",
    "context": {
      "title": "",
      "first_heading": "Prayers"
    }
  },
  {
    "path": "prayers-sanskrit.html",
    "context": {
      "title": "",
      "first_heading": "Prayers"
    }
  },
  {
    "path": "privacy-policy-espanol.html",
    "context": {
      "title": "Shri Radha Raman Ji Mandir, Temple Vrindavan",
      "first_heading": "Pol\u00edticade Privacidad"
    }
  },
  {
    "path": "privacy-policy.html",
    "context": {
      "title": "",
      "first_heading": "PrivacyPolicy"
    }
  },
  {
    "path": "product_.html",
    "context": {
      "title": "Shri Radharaman Prakatya Hindi",
      "first_heading": "\u0936\u094d\u0930\u0940 \u0930\u093e\u0927\u093e\u0930\u092e\u0923 \u092a\u094d\u0930\u093e\u0915\u091f\u094d\u092f"
    }
  },
  {
    "path": "product_11GheeLampOffering.html",
    "context": {
      "title": "11 Ghee Lamp Offering",
      "first_heading": "11 Ghee Lamp Offering"
    }
  },
  {
    "path": "product_56BhogBasic.html",
    "context": {
      "title": "56 Bhog - Basic",
      "first_heading": "56 Bhog - Basic"
    }
  },
  {
    "path": "product_56BhogSpecial.html",
    "context": {
      "title": "56 Bhog - Special",
      "first_heading": "56 Bhog - Special"
    }
  },
  {
    "path": "product_AbhishekOfferingwithPrayers.html",
    "context": {
      "title": "Abhishek Offering with Prayers",
      "first_heading": "Abhishek Offering with Prayers"
    }
  },
  {
    "path": "product_AdvanceRegistrationFee.html",
    "context": {
      "title": "84 Kos Registration Fee",
      "first_heading": "Advance Registration Fee"
    }
  },
  {
    "path": "product_AllDayBhog.html",
    "context": {
      "title": "All Day Bhog",
      "first_heading": "All Day Bhog"
    }
  },
  {
    "path": "product_AltarPhotosOnly.html",
    "context": {
      "title": "Altar Photos Only",
      "first_heading": "Altar Photos Only"
    }
  },
  {
    "path": "product_AstrologicalQuestion.html",
    "context": {
      "title": "Astrological Question",
      "first_heading": "Astrological Question"
    }
  },
  {
    "path": "product_ByaluBhog.html",
    "context": {
      "title": "Byalu Bhog",
      "first_heading": "Byalu Bhog"
    }
  },
  {
    "path": "product_CaminoalAmor.html",
    "context": {
      "title": "Camino al Amor",
      "first_heading": "Camino al Amor"
    }
  },
  {
    "path": "product_DamodarashtakamDailyRecitalforaMonth.html",
    "context": {
      "title": "Damodarashtakam Daily Recital for a Month",
      "first_heading": "Damodarashtakam - Daily Recital for a Month"
    }
  },
  {
    "path": "product_DikshaPack.html",
    "context": {
      "title": "Diksha Pack",
      "first_heading": "Diksha Pack"
    }
  },
  {
    "path": "product_DoodhBhog.html",
    "context": {
      "title": "Doodh Bhog",
      "first_heading": "Doodh Bhog"
    }
  },
  {
    "path": "product_Feed100Vaishnavs.html",
    "context": {
      "title": "Feed 100 Vaishnavs",
      "first_heading": "Feed 100 Vaishnavs"
    }
  },
  {
    "path": "product_Feed108Vaishnavs.html",
    "context": {
      "title": "Feed 108 Vaishnavs",
      "first_heading": "Feed 108 Vaishnavs"
    }
  },
  {
    "path": "product_Feed21Vaishnavs.html",
    "context": {
      "title": "Feed 21 Vaishnavs",
      "first_heading": "Feed 21 Vaishnavs"
    }
  },
  {
    "path": "product_Feed51Vaishnavs.html",
    "context": {
      "title": "Feed 51 Vaishnavs",
      "first_heading": "Feed 51 Vaishnavs"
    }
  },
  {
    "path": "product_FestivalKunj.html",
    "context": {
      "title": "Flower Kunj",
      "first_heading": "Festival Kunj"
    }
  },
  {
    "path": "product_Flowers.html",
    "context": {
      "title": "Flowers",
      "first_heading": "Flowers"
    }
  },
  {
    "path": "product_FruitBasketServiceBasic.html",
    "context": {
      "title": "Fruit Basket Service: Basic",
      "first_heading": "Fruit Basket Service: Basic"
    }
  },
  {
    "path": "product_FruitBasketServicePremium.html",
    "context": {
      "title": "Fruit Basket Service: Premium",
      "first_heading": "Fruit Basket Service: Premium"
    }
  },
  {
    "path": "product_FullDaySevaBasic.html",
    "context": {
      "title": "Full Day Seva - Basic",
      "first_heading": "Full Day Seva - Basic"
    }
  },
  {
    "path": "product_FullDaySevaSpecial.html",
    "context": {
      "title": "Full Day Seva - Special",
      "first_heading": "Full Day Seva - Special"
    }
  },
  {
    "path": "product_FullPayment12YearsInclusiveofAdvance.html",
    "context": {
      "title": "Full Payment for people above 12 years of age",
      "first_heading": "Full Payment - 12 Years + (Inclusive of Advance)"
    }
  },
  {
    "path": "product_FullPaymentChildrenbetween412YearsofAgeInclusiveofAdvance.html",
    "context": {
      "title": "Yatra 4 to 12",
      "first_heading": "Full Payment - Children between 4 & 12 Years of Age (Inclusive of Advance)"
    }
  },
  {
    "path": "product_GheeAbhishekService1kg.html",
    "context": {
      "title": "Ghee Abhishek Service: 1kg",
      "first_heading": "Ghee Abhishek Service: 1kg"
    }
  },
  {
    "path": "product_GheeAbhishekService2kg.html",
    "context": {
      "title": "Ghee Abhishek Service: 2kg",
      "first_heading": "Ghee Abhishek Service: 2kg"
    }
  },
  {
    "path": "product_GheeLampOfferingDailyfor31Days.html",
    "context": {
      "title": "Ghee Lamp Offering Daily for a Month",
      "first_heading": "Ghee Lamp Offering - Daily for 31 Days"
    }
  },
  {
    "path": "product_GopiGeetDailyRecitalforaMonth.html",
    "context": {
      "title": "Gopi Geet - Daily Recital for a Month",
      "first_heading": "Gopi Geet - Daily Recital for a Month"
    }
  },
  {
    "path": "product_Itra.html",
    "context": {
      "title": "Itra",
      "first_heading": "Itra"
    }
  },
  {
    "path": "product_JhariSeva.html",
    "context": {
      "title": "Jhari Seva",
      "first_heading": "Jhari Seva"
    }
  },
  {
    "path": "product_KirtanSeva.html",
    "context": {
      "title": "Kirtan Seva",
      "first_heading": "Kirtan Seva"
    }
  },
  {
    "path": "product_KrishnMarriageYagya.html",
    "context": {
      "title": "Krishn Marriage Yagya",
      "first_heading": "Krishn Marriage Yagya"
    }
  },
  {
    "path": "product_KuliyaService101Kuliyas.html",
    "context": {
      "title": "Kuliya Service: 101 Kuliyas",
      "first_heading": "Kuliya Service: 101 Kuliyas"
    }
  },
  {
    "path": "product_KuliyaService51Kuliyas.html",
    "context": {
      "title": "Kuliya Service: 51 Kuliyas",
      "first_heading": "Kuliya Service: 51 Kuliyas"
    }
  },
  {
    "path": "product_MediumKunj.html",
    "context": {
      "title": "Medium Kunj",
      "first_heading": "Medium Kunj"
    }
  },
  {
    "path": "product_MilkAbhishekService100litresofmilk.html",
    "context": {
      "title": "Milk Abhishek Service: 100 litres of milk",
      "first_heading": "Milk Abhishek Service: 100 litres of milk"
    }
  },
  {
    "path": "product_MilkAbhishekService150litresofmilk.html",
    "context": {
      "title": "Milk Abhishek Service: 150 litres of milk",
      "first_heading": "Milk Abhishek Service: 150 litres of milk"
    }
  },
  {
    "path": "product_MilkAbhishekService15litresofmilk.html",
    "context": {
      "title": "Milk Abhishek Service",
      "first_heading": "Milk Abhishek Service: 15 litres of milk"
    }
  },
  {
    "path": "product_MilkAbhishekService21litresofmilk.html",
    "context": {
      "title": "Milk Abhishek Service 21",
      "first_heading": "Milk Abhishek Service: 21 litres of milk"
    }
  },
  {
    "path": "product_MilkAbhishekService51litresofmilk.html",
    "context": {
      "title": "Milk Abhishek Service: 51 litres of milk",
      "first_heading": "Milk Abhishek Service: 51 litres of milk"
    }
  },
  {
    "path": "product_MohanBhog.html",
    "context": {
      "title": "Mohan Bhog",
      "first_heading": "Mohan Bhog"
    }
  },
  {
    "path": "product_NewSpiritualInk.html",
    "context": {
      "title": "Spiritual Ink",
      "first_heading": "New - Spiritual Ink"
    }
  },
  {
    "path": "product_PoshakSeva.html",
    "context": {
      "title": "Poshak Seva",
      "first_heading": "Poshak Seva"
    }
  },
  {
    "path": "product_PrayertoRadharaman.html",
    "context": {
      "title": "Prayer to Radharaman",
      "first_heading": "Prayer to Radharaman"
    }
  },
  {
    "path": "product_PremParikartika.html",
    "context": {
      "title": "Prem Parikartika",
      "first_heading": "Prem Parikartika \u092a\u094d\u0930\u0947\u092e \u092a\u0930\u093f\u0915\u0930\u094d\u0924\u093f\u0915\u093e"
    }
  },
  {
    "path": "product_RadhaKripaKataksh108Recitals.html",
    "context": {
      "title": "Radha Kripa Kataksh - 108 Recitals",
      "first_heading": "Radha Kripa Kataksh - 108 Recitals"
    }
  },
  {
    "path": "product_RadhaRasSudhaNidhiSingleRecital.html",
    "context": {
      "title": "Radha Ras Sudha Nidhi Single Recital",
      "first_heading": "Radha Ras Sudha Nidhi Single Recital"
    }
  },
  {
    "path": "product_RadhaYagya.html",
    "context": {
      "title": "Radha Yagya",
      "first_heading": "Radha Yagya"
    }
  },
  {
    "path": "product_RadharamanCalendar2021.html",
    "context": {
      "title": "Radharaman Calendar 2021",
      "first_heading": "Radharaman Calendar 2021"
    }
  },
  {
    "path": "product_RadharamanCalendar2024.html",
    "context": {
      "title": "Radharaman Calendar 2024",
      "first_heading": "Radharaman Calendar 2024"
    }
  },
  {
    "path": "product_RadharamanGitaCD.html",
    "context": {
      "title": "Radharaman Gita",
      "first_heading": "Radharaman Gita CD"
    }
  },
  {
    "path": "product_RadharamanPrasadiPoshak.html",
    "context": {
      "title": "Radharaman Prasadi Poshak",
      "first_heading": "Radharaman Prasadi Poshak"
    }
  },
  {
    "path": "product_Rajbhog.html",
    "context": {
      "title": "Rajbhog",
      "first_heading": "Rajbhog"
    }
  },
  {
    "path": "product_SRKFTheAnimalsEnglish.html",
    "context": {
      "title": "SRKF The Animals English",
      "first_heading": "SRKF The Animals English"
    }
  },
  {
    "path": "product_SRKFTheAnimalsHindi.html",
    "context": {
      "title": "SRKF The Animals Hindi",
      "first_heading": "SRKF The Animals Hindi"
    }
  },
  {
    "path": "product_SRKFTheAnimalsSpanish.html",
    "context": {
      "title": "SRKF The Animals Spanish",
      "first_heading": "SRKF The Animals Spanish"
    }
  },
  {
    "path": "product_SantanGopalYagya.html",
    "context": {
      "title": "Santan Gopal Yagya",
      "first_heading": "Santan Gopal Yagya"
    }
  },
  {
    "path": "product_ShriGopalMahamantraYagya1.html",
    "context": {
      "title": "Shri Gopal/Mahamantra Yagya 1",
      "first_heading": "Shri Gopal/Mahamantra Yagya 1"
    }
  },
  {
    "path": "product_ShriGopalMahamantraYagya2.html",
    "context": {
      "title": "Shri Gopal/Mahamantra Yagya 2",
      "first_heading": "Shri Gopal/Mahamantra Yagya 2"
    }
  },
  {
    "path": "product_ShriKrishnKautukam.html",
    "context": {
      "title": "Shri Krishn Kautukam Hindi",
      "first_heading": "Shri Krishn Kautukam"
    }
  },
  {
    "path": "product_ShriRadhaMantraYagya.html",
    "context": {
      "title": "Shri Radha Mantra Yagya",
      "first_heading": "Shri Radha Mantra Yagya"
    }
  },
  {
    "path": "product_ShriRadharamanGitaHindi.html",
    "context": {
      "title": "Shri Radharaman Gita Hindi",
      "first_heading": "Shri Radharaman Gita Hindi"
    }
  },
  {
    "path": "product_ShriRadharamanNityaSevaVidhiOnlineCourse.html",
    "context": {
      "title": "Shri Radharaman Nitya Seva Vidhi - Online Course",
      "first_heading": "Shri Radharaman Nitya Seva Vidhi - Online Course"
    }
  },
  {
    "path": "product_ShriRadharamanPrakatya.html",
    "context": {
      "title": "Shri Radharaman Prakatya English",
      "first_heading": "Shri Radharaman Prakatya"
    }
  },
  {
    "path": "product_ShriRadharamanStole.html",
    "context": {
      "title": "Shri Radharaman Stole",
      "first_heading": "Shri Radharaman Stole"
    }
  },
  {
    "path": "product_ShriRadharamanWorshipCourse.html",
    "context": {
      "title": "Shri Radharaman Worship Course",
      "first_heading": "Shri Radharaman Worship Course"
    }
  },
  {
    "path": "product_ShriRadharamansDress.html",
    "context": {
      "title": "Shri Radharaman's Dress",
      "first_heading": "Shri Radharaman's Dress"
    }
  },
  {
    "path": "product_ShriVishnuSahasranamArchanamDailyfor1Month.html",
    "context": {
      "title": "Shri Vishnu Sahasranam Archanam - Daily Recital for One Month",
      "first_heading": "Shri Vishnu Sahasranam Archanam - Daily for 1 Month"
    }
  },
  {
    "path": "product_ShriVishnuSahasranamArchanamDailyfor7Days.html",
    "context": {
      "title": "Shri Vishnu Sahasranam Archanam - Daily Recital for Seven Days",
      "first_heading": "Shri Vishnu Sahasranam Archanam - Daily for 7 Days"
    }
  },
  {
    "path": "product_ShriVishnuSahasranamArchanamOneRecitalOnly.html",
    "context": {
      "title": "Shri Vishnu Sahasranam Archanam - One Recital Only",
      "first_heading": "Shri Vishnu Sahasranam Archanam - One Recital Only"
    }
  },
  {
    "path": "product_ShrimadBhagwatamDailyRecitalofRaasPanchadhyayiforaMonth.html",
    "context": {
      "title": "Shrimad Bhagwatam - Daily Recital of Raas Panchadhyayi for a Month",
      "first_heading": "Shrimad Bhagwatam - Daily Recital of Raas Panchadhyayi for a Month"
    }
  },
  {
    "path": "product_ShrimadBhagwatamOneRecitalofRaasPanchadhyayi.html",
    "context": {
      "title": "Shrimad Bhagwatam - One Recital of Raas Panchadhyayi",
      "first_heading": "Shrimad Bhagwatam - One Recital of Raas Panchadhyayi"
    }
  },
  {
    "path": "product_ShrimadBhagwatamRaasPanchadhyayiRecitalfor1Week.html",
    "context": {
      "title": "Shrimad Bhagwatam - Raas Panchadhyayi Recital for 1 Week",
      "first_heading": "Shrimad Bhagwatam - Raas Panchadhyayi Recital for 1 Week"
    }
  },
  {
    "path": "product_ShrimadBhagwatamRecital.html",
    "context": {
      "title": "Shrimad Bhagwatam Recital",
      "first_heading": "Shrimad Bhagwatam Recital"
    }
  },
  {
    "path": "product_ShrimadBhagwatamRecitationTenthCanto.html",
    "context": {
      "title": "Shrimad Bhagwatam Recitation - Tenth Canto",
      "first_heading": "Shrimad Bhagwatam Recitation - Tenth Canto"
    }
  },
  {
    "path": "product_SmallKunj.html",
    "context": {
      "title": "Small Kunj",
      "first_heading": "Small Kunj"
    }
  },
  {
    "path": "product_SpiritualHealingYagya.html",
    "context": {
      "title": "Spiritual Healing Yagya",
      "first_heading": "Spiritual Healing Yagya"
    }
  },
  {
    "path": "product_SpiritualInk.html",
    "context": {
      "title": "Spiritual Ink",
      "first_heading": "Spiritual Ink"
    }
  },
  {
    "path": "product_TaniyaSeva.html",
    "context": {
      "title": "Taniya Seva",
      "first_heading": "Taniya Seva"
    }
  },
  {
    "path": "product_TheSacredShilas.html",
    "context": {
      "title": "The Sacred Shilas",
      "first_heading": "The Sacred Shilas"
    }
  },
  {
    "path": "product_TintaEspiritual.html",
    "context": {
      "title": "Tinta Espiritual",
      "first_heading": "Tinta Espiritual"
    }
  },
  {
    "path": "product_Tulsi.html",
    "context": {
      "title": "Tulsi",
      "first_heading": "Tulsi"
    }
  },
  {
    "path": "product_TulsiDistribution108TulsiPlants.html",
    "context": {
      "title": "Tulsi Distribution - 108 Tulsi Plants",
      "first_heading": "Tulsi Distribution - 108 Tulsi Plants"
    }
  },
  {
    "path": "product_TulsiDistribution21TulsiPlants.html",
    "context": {
      "title": "Tulsi Distribution - 21 Tulsi Plants",
      "first_heading": "Tulsi Distribution - 21 Tulsi Plants"
    }
  },
  {
    "path": "product_TulsiDistribution251TulsiPlants.html",
    "context": {
      "title": "Tulsi Distribution - 251 Tulsi Plants",
      "first_heading": "Tulsi Distribution - 251 Tulsi Plants"
    }
  },
  {
    "path": "product_TulsiDistribution500TulsiPlants.html",
    "context": {
      "title": "Tulsi Distribution - 500 Tulsi Plants",
      "first_heading": "Tulsi Distribution - 500 Tulsi Plants"
    }
  },
  {
    "path": "product_TulsiDistribution51TulsiPlants.html",
    "context": {
      "title": "Tulsi Distribution - 51 Tulsi Plants",
      "first_heading": "Tulsi Distribution - 51 Tulsi Plants"
    }
  },
  {
    "path": "product_UtsavKunj.html",
    "context": {
      "title": "Utsav Kunj",
      "first_heading": "Utsav Kunj"
    }
  },
  {
    "path": "product_ViamagusTest.html",
    "context": {
      "title": "Viamagus Test",
      "first_heading": "Viamagus Test"
    }
  },
  {
    "path": "product_WaytoLoveCD.html",
    "context": {
      "title": "Way to Love Audio Book",
      "first_heading": "Way to Love CD"
    }
  },
  {
    "path": "product_Waytolove.html",
    "context": {
      "title": "Way to love",
      "first_heading": "Way to love"
    }
  },
  {
    "path": "product_YagyaforFinancialIssues.html",
    "context": {
      "title": "Yagya for Financial Issues",
      "first_heading": "Yagya for Financial Issues"
    }
  },
  {
    "path": "product_YagyaforIllness.html",
    "context": {
      "title": "Yagya for Illness",
      "first_heading": "Yagya for Illness"
    }
  },
  {
    "path": "product_YagyaforMarriage.html",
    "context": {
      "title": "Yagya for Marriage",
      "first_heading": "Yagya for Marriage"
    }
  },
  {
    "path": "product_YagyaforPropertyMatters.html",
    "context": {
      "title": "Yagya for Property Matters",
      "first_heading": "Yagya for Property Matters"
    }
  },
  {
    "path": "product_YagyatoRemoveNegativeInfluences.html",
    "context": {
      "title": "Yagya to Remove Negative Influences",
      "first_heading": "Yagya to Remove Negative Influences"
    }
  },
  {
    "path": "product_hrRdhramaGtNityaLl.html",
    "context": {
      "title": "\u015ahr\u012b R\u0101dh\u0101rama\u1e47 G\u012bt\u0101: Nitya L\u012bl\u0101",
      "first_heading": "\u015ahr\u012b R\u0101dh\u0101rama\u1e47 G\u012bt\u0101: Nitya L\u012bl\u0101"
    }
  },
  {
    "path": "projects.html",
    "context": {
      "title": "",
      "first_heading": "Projects"
    }
  },
  {
    "path": "refund-policy-espanol.html",
    "context": {
      "title": "Shri Radha Raman Ji Mandir, Temple Vrindavan",
      "first_heading": "Pol\u00edticade Reembolso"
    }
  },
  {
    "path": "refund-policy.html",
    "context": {
      "title": "",
      "first_heading": "RefundPolicy"
    }
  },
  {
    "path": "resources.html",
    "context": {
      "title": "",
      "first_heading": "Resources"
    }
  },
  {
    "path": "services-for-radharaman.html",
    "context": {
      "title": "",
      "first_heading": "Services forRadharaman"
    }
  },
  {
    "path": "services.html",
    "context": {
      "title": "",
      "first_heading": "Stay Connected With Us!"
    }
  },
  {
    "path": "serving-the-elderly-espanol.html",
    "context": {
      "title": "Shri Radha Raman Ji Mandir, Temple Vrindavan",
      "first_heading": "Servicio a los Mayores"
    }
  },
  {
    "path": "serving-the-elderly.html",
    "context": {
      "title": "",
      "first_heading": "Serving the Elderly"
    }
  },
  {
    "path": "shipping-policy-espanol.html",
    "context": {
      "title": "Shri Radha Raman Ji Mandir, Temple Vrindavan",
      "first_heading": "Pol\u00edtica de Env\u00edos"
    }
  },
  {
    "path": "shipping-policy.html",
    "context": {
      "title": "Shri Radha Raman Ji Mandir, Temple Vrindavan",
      "first_heading": "Shipping Policy"
    }
  },
  {
    "path": "shop.html",
    "context": {
      "title": "",
      "first_heading": "Shop"
    }
  },
  {
    "path": "shri-radharaman-backup.html",
    "context": {
      "title": "",
      "first_heading": "ShriRadharaman"
    }
  },
  {
    "path": "shri-radharaman.html",
    "context": {
      "title": "",
      "first_heading": "Services forRadharaman"
    }
  },
  {
    "path": "shri-yamuna-aarti.html",
    "context": {
      "title": "",
      "first_heading": "Shri Yamuna Aarti Gallery"
    }
  },
  {
    "path": "shri-yamuna.html",
    "context": {
      "title": "",
      "first_heading": "Shri Yamuna Gallery"
    }
  },
  {
    "path": "shriji.html",
    "context": {
      "title": "",
      "first_heading": "Appearance Day Gallery"
    }
  },
  {
    "path": "temple.html",
    "context": {
      "title": "",
      "first_heading": "History"
    }
  },
  {
    "path": "terms-and-conditions.html",
    "context": {
      "title": "",
      "first_heading": "Terms&Conditions"
    }
  },
  {
    "path": "test.html",
    "context": {
      "title": "Shri Radharaman Temple Vrindavan",
      "first_heading": "Loading Viamagus Test...."
    }
  },
  {
    "path": "the-founder.html",
    "context": {
      "title": "",
      "first_heading": "Chandan Goswami"
    }
  },
  {
    "path": "the-goswami-family.html",
    "context": {
      "title": "",
      "first_heading": "The Goswami Family"
    }
  },
  {
    "path": "the-radharaman-temple.html",
    "context": {
      "title": "Radharaman Temple",
      "first_heading": "The Radharaman Temple"
    }
  },
  {
    "path": "the-teachings.html",
    "context": {
      "title": "",
      "first_heading": "Gaudiya Vaishnavism"
    }
  },
  {
    "path": "vaishnav-calendar.html",
    "context": {
      "title": "",
      "first_heading": "Vaishnav Calendar"
    }
  },
  {
    "path": "video-backup.html",
    "context": {
      "title": "",
      "first_heading": "Videos"
    }
  },
  {
    "path": "video.html",
    "context": {
      "title": "",
      "first_heading": "Videos"
    }
  },
  {
    "path": "videos.html",
    "context": {
      "title": "",
      "first_heading": "Videos"
    }
  },
  {
    "path": "vm-test.html",
    "context": {
      "title": "Shri Radha Raman Ji Mandir, Temple Vrindavan",
      "first_heading": "Loading Viamagus Test...."
    }
  },
  {
    "path": "yagyas.html",
    "context": {
      "title": "",
      "first_heading": "Yagyas"
    }
  },
  {
    "path": "yamuna.html",
    "context": {
      "title": "",
      "first_heading": "Yamuna"
    }
  }
]

Return only a JSON object mapping each path to its new basename (same extension). No other text.