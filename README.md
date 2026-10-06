# AcroRoute
# 📍 Acro Route - AITR Smart Campus Navigation Engine

**Acro Route** ek modern, web-based 2D vector campus navigation engine hai, jo specially **Acropolis Institute of Technology and Research (AITR), Indore** ke campus navigation ko fast, clean aur user-friendly banane ke liye banaya gaya hai.

Is app me clutter-free 2D map canvas, turn-by-turn voice navigation (Google Maps style), live directional arrow indicator, indoor floor-wise layout viewing (Ground se 3rd floor tak), aur dynamic custom location management (Classrooms, Faculty Cabins, Labs, HOD Offices) jaise advanced features integrated hain.

---

## 🛠️ Tech Stack & Requirements

- **Frontend Core:** HTML5, Modern JavaScript (ES6+), CSS3
- **Styling Framework:** Tailwind CSS & Custom Glassmorphic CSS
- **Mapping Library:** Leaflet.js (Simple CRS Vector Map Engine)
- **Icons & Graphics:** FontAwesome 6
- **Voice Guidance:** Browser Web Speech API (`SpeechSynthesis`)
- **Motion Sensors:** Browser DeviceMotion API (PDR Pedestrian Step Detection)

---

## 📖 App UI & Feature Guide (A2Z Explanation)

App ka dashboard 4 major sections me structured hai:

### 1. Top Header & Campus Banner
- **Campus Branding:** Screen ke sabse upar **Acro Route** aur **Acropolis Institute of Technology and Research** ka main title display hota hai.
- **Institute Photo Banner:** Title ke theek niche AITR campus ki full-width high-resolution photo lagi hai jo map start hone se pehle visual identity deti hai.

---

### 2. Main Control Bar (Search, Routing & Sound Controls)

- **Start Point Dropdown (`Start: ...`):**
  - Defualt **AITR Main Entrance** set rehta hai.
  - Aap chahein toh Block 1 Entrance, Block 2 Entrance, ya Block 3 Entrance ko apna start location select kar sakte hain.
- **Select Destination Dropdown:**
  - Campus ke saare major spots isme categories me organized hain:
    - **AITR Key Landmarks:** Central Canteen, Sports Complex (In front of Canteen), Stationery Shop (In front of Block 3), Medical Room, Printing Shop.
    - **Auditoriums & Special Units:** Dhairya Prabha Audi (MBA Block), Kamal Prabha Main Audi (AIMSR Zone), IDEA Lab (Block 2 - 1st Floor), Server Room (Block 2 - 1st Floor), Acro Care (Block 1 - 3rd Floor), CDC Center (Block 3 - Ground Floor).
    - **Administrative Offices:** Reception & Info, Fees Counter, Director Sir Office, Admission Cell.
    - **Custom Added Locations:** Agar aapne koi naya classroom ya faculty cabin add kiya hai, toh wo bhi is dropdown me automatically show hoga.
- **"Start Navigation" Button (Blue):**
  - Destination select karne ke baad is button par click karne par:
    1. Map par AITR main road ke along single blue-dashed route line active ho jati hai.
    2. Voice engine automatic active ho kar Hindi/English mixed voice directions dena start kar deta hai.
    3. User ka live directional marker active destination ki taraf rotate ho jata hai.
- **"PDR / Step Sensor" Button (Green):**
  - Is button par click karke aap motion sensors toggle kar sakte hain. Walking steps count hote hi live user dot move hone lagta hai.
- **"Voice Mute/Unmute" Button:**
  - Navigation ke dauran voice prompts ko sound icon par click karke play ya mute kiya ja sakta hai.

---

### 3. Floor Switcher & Step Counter Bar

- **Floor Buttons (`Ground`, `1st Floor`, `2nd Floor`, `3rd Floor`):**
  - **Ground Floor:** Civil Engineering Dept (Block 1), General Classrooms (Block 2), CDC Center (Block 3).
  - **1st Floor:** Civil Dept & Central Library (Block 1), IDEA Lab & Server Room (Block 2), Computer Science (CS) Dept (Block 3).
  - **2nd Floor:** 1st Year Classes (Block 1), Electronics & Comm (EC) Dept (Block 2), Information Technology (IT) Dept (Block 3).
  - **3rd Floor:** 1st Year Classes & Acro Care (Block 1), AIML Dept (Block 2), CSIT Dept (Block 3).
  - *Note:* Har floor par har block ke andar **Washroom** facility clearly marked hai.
- **Step Count & Distance Metric:**
  - User dwara chali gayi steps (`Steps: X`) aur approximate distance (`Distance: X.X m`) real-time calculate hoti hai.
- **"Reset" Button:**
  - Route line aur current navigation state ko clear karke default full campus zoom view par wapis le jata hai.

---

### 4. Interactive 2D Map Canvas (Clutter-Free Design)

- **AITR vs AIMSR Separation:**
  - **AITR (Engineering Campus):** Map ka main highlight section hai jaha saare 3 blocks, roads, canteen, aur grounds active hain.
  - **AIMSR Zone:** Left side par separate light-grey shaded region me Pharmacy/BBA/BSc zone aur **Kamal Prabha Main Auditorium** marked hain.
- **Visual Vector Elements:**
  - Asphalt Road network with center lane dashes.
  - Green Lawns, Trees clusters, and Sports field.
  - Blocks 1, 2, 3 represented in clean pastel architectural polygons.
- **Interactive Popup Cards:**
  - Kisi bhi block, canteen, ya auditorium par click karne par us specific building ke andar ke rooms, departments aur amenities ki crisp pop-up list open ho jati hai.

---

### 5. Dynamic "+ Add Location" Feature (Modal Workflow)

Top control bar me **"+ Add"** button diya gaya hai. Jab aap kisi naye cabin ya room ko map par register karna chahein:

1. **"+ Add"** button par click karein. Ek clean popup window (Modal) open hogi.
2. Select karein ki aap kya add karna chahte hain:
   - 🏫 **Add Class / Classroom**
   - 👤 **Add Faculty Cabin**
   - 🔬 **Add Labs**
   - 👔 **Add HOD Office**
3. Form bharein:
   - **Name / Room Number** (e.g., *Dr. Sharma Cabin*, *AI Lab 2*, *Room 304*)
   - **Block** (Block 1, Block 2, Block 3, Admin)
   - **Floor** (Ground, 1st, 2nd, 3rd)
   - **Department** (CS, IT, EC, Civil, AIML, etc.)
4. **"Pick Location on Map"** click karke map par exact spot choose karein aur **Save** kar dein.
5. Save hoti hi ye nayi location **Destination Dropdown** me hamesha ke liye add ho jati hai (`localStorage` persisted).

---

## 📂 Project Directory Structure

```text
AcroRoute/
 ├── index.html        # Complete Single-File Application (UI Layout, CSS, Leaflet Map, & JS Engine)
 ├── README.md         # Complete Project Documentation & Usage Manual
 └── assets/           # Campus Banner & Institutional Images
