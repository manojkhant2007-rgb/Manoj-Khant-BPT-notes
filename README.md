# Manoj-Khant-BPT-notes<!DOCTYPE html>
<html lang="hi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Manoj Khant ki Notes</title>
    <!-- jsPDF Library for Dynamic PDF Generation -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/jspdf/2.5.1/jspdf.umd.min.js"></script>
    <style>
        * { box-sizing: border-box; font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; }
        body { background: #0f172a; color: #f8fafc; margin: 0; padding: 20px; text-align: center; }
        .container { max-width: 600px; margin: auto; background: #1e293b; padding: 25px; border-radius: 16px; box-shadow: 0 10px 25px rgba(0,0,0,0.3); }
        h1 { color: #38bdf8; font-size: 26px; margin-bottom: 10px; }
        p { color: #94a3b8; font-size: 15px; }
        
        .btn { display: flex; align-items: center; justify-content: center; width: 100%; padding: 14px; margin: 12px 0; background: #2563eb; color: white; border: none; border-radius: 10px; font-size: 16px; font-weight: bold; cursor: pointer; transition: 0.2s; text-decoration: none; }
        .btn:hover { background: #1d4ed8; transform: translateY(-2px); }
        .btn-open { background: #059669; font-size: 18px; padding: 16px; }
        .btn-open:hover { background: #047857; }
        .btn-pdf { background: #e11d48; width: auto; padding: 8px 14px; font-size: 13px; margin: 0; }
        .btn-pdf:hover { background: #be123c; }
        .btn-back { background: #475569; margin-top: 15px; }
        .btn-back:hover { background: #334155; }
        
        .gesture { font-size: 22px; margin-left: 8px; animation: bounce 1s infinite alternate; }
        @keyframes bounce { 0% { transform: translateX(0); } 100% { transform: translateX(8px); } }

        .topic-card { display: flex; justify-content: space-between; align-items: center; background: #334155; padding: 12px 16px; border-radius: 8px; margin: 10px 0; text-align: left; }
        .topic-title { font-size: 15px; font-weight: 500; color: #f1f5f9; width: 70%; }
        
        .hidden { display: none; }
    </style>
</head>
<body>

<div class="container">

    <!-- 1. LANDING PAGE / WELCOME SCREEN -->
    <div id="landing-page">
        <h1 style="font-size: 30px; color: #38bdf8;">Manoj Khant ki notes</h1>
        <p>BPT 2nd Year Complete Study Hub</p>
        <br>
        <button class="btn btn-open" onclick="showScreen('subjects-page')">
            OPEN <span class="gesture">👈 Click Here</span>
        </button>
    </div>

    <!-- 2. SUBJECTS MENU (7 OPTIONS) -->
    <div id="subjects-page" class="hidden">
        <h1>📚 Choose Subject</h1>
        <button class="btn" onclick="showScreen('pathology-page')">1. Pathology</button>
        <button class="btn" onclick="showScreen('pharmacology-page')">2. Pharmacology</button>
        <button class="btn" onclick="showScreen('microbiology-page')">3. Microbiology</button>
        <button class="btn" onclick="showScreen('biomechanics-page')">4. Biomechanics</button>
        <button class="btn" onclick="showScreen('electrotherapy-page')">5. Electrotherapy</button>
        <button class="btn" onclick="showScreen('exercisetherapy-page')">6. Exercise Therapy</button>
        <button class="btn" onclick="showScreen('yoga-page')">7. Yoga</button>
        <button class="btn btn-back" onclick="showScreen('landing-page')">⬅ Back to Home</button>
    </div>

    <!-- 3. PATHOLOGY QUESTIONS -->
    <div id="pathology-page" class="hidden">
        <h1>🔬 Pathology Topics</h1>
        <div class="topic-card">
            <div class="topic-title">1. Cell Injury & Necrosis</div>
            <button class="btn btn-pdf" onclick="generatePDF('Cell Injury & Necrosis', 'Pathology', 'Complete study guide for Cell Injury and Necrosis covering definitions, etiology, types of necrosis (coagulative, liquefactive, caseous), and nuclear changes.')">PDF 📄</button>
        </div>
        <div class="topic-card">
            <div class="topic-title">2. Neoplasia</div>
            <button class="btn btn-pdf" onclick="generatePDF('Neoplasia', 'Pathology', 'Benign vs Malignant tumors, Anaplasia, Pathways of spread/metastasis, and Carcinogenesis.')">PDF 📄</button>
        </div>
        <div class="topic-card">
            <div class="topic-title">3. Diabetes Mellitus</div>
            <button class="btn btn-pdf" onclick="generatePDF('Diabetes Mellitus', 'Pathology', 'Etiology, Type 1 vs Type 2 DM, Pathophysiology, Clinical features, and long-term complications.')">PDF 📄</button>
        </div>
        <div class="topic-card">
            <div class="topic-title">4. Inflammation (Acute & Chronic)</div>
            <button class="btn btn-pdf" onclick="generatePDF('Inflammation', 'Pathology', 'Vascular and cellular events of acute inflammation, chemical mediators, and granulomatous inflammation.')">PDF 📄</button>
        </div>
        <div class="topic-card">
            <div class="topic-title">5. Atherosclerosis</div>
            <button class="btn btn-pdf" onclick="generatePDF('Atherosclerosis', 'Pathology', 'Risk factors, pathogenesis (Response-to-Injury hypothesis), morphology, and clinical consequences.')">PDF 📄</button>
        </div>
        <button class="btn btn-back" onclick="showScreen('subjects-page')">⬅ Back to Subjects</button>
    </div>

    <!-- 4. PHARMACOLOGY QUESTIONS -->
    <div id="pharmacology-page" class="hidden">
        <h1>💊 Pharmacology Topics</h1>
        <div class="topic-card"><div class="topic-title">1. General Pharmacokinetics (ADME)</div><button class="btn btn-pdf" onclick="generatePDF('Pharmacokinetics', 'Pharmacology', 'Absorption, Distribution, Metabolism, and Excretion of drugs.')">PDF 📄</button></div>
        <div class="topic-card"><div class="topic-title">2. NSAIDs & Analgesics</div><button class="btn btn-pdf" onclick="generatePDF('NSAIDs', 'Pharmacology', 'Mechanism of action (COX inhibitors), classification, and side effects.')">PDF 📄</button></div>
        <div class="topic-card"><div class="topic-title">3. Muscle Relaxants</div><button class="btn btn-pdf" onclick="generatePDF('Muscle Relaxants', 'Pharmacology', 'Centrally vs Peripherally acting muscle relaxants and clinical uses in PT.')">PDF 📄</button></div>
        <div class="topic-card"><div class="topic-title">4. Corticosteroids</div><button class="btn btn-pdf" onclick="generatePDF('Corticosteroids', 'Pharmacology', 'Mechanism, anti-inflammatory actions, adverse effects, and withdrawal.')">PDF 📄</button></div>
        <div class="topic-card"><div class="topic-title">5. Autonomic Nervous System Drugs</div><button class="btn btn-pdf" onclick="generatePDF('ANS Drugs', 'Pharmacology', 'Sympathomimetics, Parasympathomimetics, and blocker agents.')">PDF 📄</button></div>
        <button class="btn btn-back" onclick="showScreen('subjects-page')">⬅ Back to Subjects</button>
    </div>

    <!-- 5. MICROBIOLOGY QUESTIONS -->
    <div id="microbiology-page" class="hidden">
        <h1>🦠 Microbiology Topics</h1>
        <div class="topic-card"><div class="topic-title">1. Sterilization & Disinfection</div><button class="btn btn-pdf" onclick="generatePDF('Sterilization', 'Microbiology', 'Physical and chemical methods of sterilization in hospital settings.')">PDF 📄</button></div>
        <div class="topic-card"><div class="topic-title">2. Tuberculosis (Mycobacterium)</div><button class="btn btn-pdf" onclick="generatePDF('Tuberculosis', 'Microbiology', 'Morphology, pathogenesis, Mantoux test, and lab diagnosis.')">PDF 📄</button></div>
        <div class="topic-card"><div class="topic-title">3. Hospital Acquired Infections (HAI)</div><button class="btn btn-pdf" onclick="generatePDF('HAI', 'Microbiology', 'Common pathogens, prevention, and infection control protocols.')">PDF 📄</button></div>
        <div class="topic-card"><div class="topic-title">4. Immunity & Hypersensitivity</div><button class="btn btn-pdf" onclick="generatePDF('Immunity', 'Microbiology', 'Innate vs Acquired immunity, Types I-IV Hypersensitivity reactions.')">PDF 📄</button></div>
        <div class="topic-card"><div class="topic-title">5. Viral Hepatitis (HBV/HCV)</div><button class="btn btn-pdf" onclick="generatePDF('Hepatitis', 'Microbiology', 'Transmission, serological markers, and clinical features.')">PDF 📄</button></div>
        <button class="btn btn-back" onclick="showScreen('subjects-page')">⬅ Back to Subjects</button>
    </div>

    <!-- 6. BIOMECHANICS QUESTIONS -->
    <div id="biomechanics-page" class="hidden">
        <h1>🦴 Biomechanics Topics</h1>
        <div class="topic-card"><div class="topic-title">1. Gait Cycle Analysis</div><button class="btn btn-pdf" onclick="generatePDF('Gait Cycle', 'Biomechanics', 'Stance phase, Swing phase, spatial-temporal parameters, and pathological gaits.')">PDF 📄</button></div>
        <div class="topic-card"><div class="topic-title">2. Shoulder Complex Biomechanics</div><button class="btn btn-pdf" onclick="generatePDF('Shoulder Biomechanics', 'Biomechanics', 'Scapulohumeral rhythm, force couples, and joint stability.')">PDF 📄</button></div>
        <div class="topic-card"><div class="topic-title">3. Knee Joint & Locking Mechanism</div><button class="btn btn-pdf" onclick="generatePDF('Knee Biomechanics', 'Biomechanics', 'Screw-home mechanism, patellofemoral mechanics, and ligament constraints.')">PDF 📄</button></div>
        <div class="topic-card"><div class="topic-title">4. Levers & Mechanical Advantage</div><button class="btn btn-pdf" onclick="generatePDF('Levers in Human Body', 'Biomechanics', 'First, second, and third-class levers with human body examples.')">PDF 📄</button></div>
        <div class="topic-card"><div class="topic-title">5. Vertebral Column Mechanics</div><button class="btn btn-pdf" onclick="generatePDF('Vertebral Mechanics', 'Biomechanics', 'Curves of spine, load bearing, and intervertebral disc mechanics.')">PDF 📄</button></div>
        <button class="btn btn-back" onclick="showScreen('subjects-page')">⬅ Back to Subjects</button>
    </div>

    <!-- 7. ELECTROTHERAPY QUESTIONS -->
    <div id="electrotherapy-page" class="hidden">
        <h1>⚡ Electrotherapy Topics</h1>
        <div class="topic-card"><div class="topic-title">1. TENS (Pain Gate Theory)</div><button class="btn btn-pdf" onclick="generatePDF('TENS', 'Electrotherapy', 'Transcutaneous Electrical Nerve Stimulation, frequencies, and Gate Control Mechanism.')">PDF 📄</button></div>
        <div class="topic-card"><div class="topic-title">2. Ultrasound Therapy</div><button class="btn btn-pdf" onclick="generatePDF('Ultrasound Therapy', 'Electrotherapy', 'Thermal/non-thermal effects, attenuation, cavitation, and dosage.')">PDF 📄</button></div>
        <div class="topic-card"><div class="topic-title">3. IFT (Interferential Therapy)</div><button class="btn btn-pdf" onclick="generatePDF('IFT', 'Electrotherapy', 'Principle of beat frequency, electrode placement, and indications.')">PDF 📄</button></div>
        <div class="topic-card"><div class="topic-title">4. SD Curve (Strength Duration)</div><button class="btn btn-pdf" onclick="generatePDF('SD Curve', 'Electrotherapy', 'Rheobase, Chronaxie, and plotted curves for innervated vs denervated muscle.')">PDF 📄</button></div>
        <div class="topic-card"><div class="topic-title">5. SWD (Shortwave Diathermy)</div><button class="btn btn-pdf" onclick="generatePDF('SWD', 'Electrotherapy', 'Capacitive vs Inductive methods, thermal physiological effects, and contraindications.')">PDF 📄</button></div>
        <button class="btn btn-back" onclick="showScreen('subjects-page')">⬅ Back to Subjects</button>
    </div>

    <!-- 8. EXERCISE THERAPY QUESTIONS -->
    <div id="exercisetherapy-page" class="hidden">
        <h1>🏋️ Exercise Therapy Topics</h1>
        <div class="topic-card"><div class="topic-title">1. Passive & Active Movements</div><button class="btn btn-pdf" onclick="generatePDF('Movements', 'Exercise Therapy', 'Classification, principles, techniques, and therapeutic effects.')">PDF 📄</button></div>
        <div class="topic-card"><div class="topic-title">2. Stretching Techniques (PNF)</div><button class="btn btn-pdf" onclick="generatePDF('Stretching & PNF', 'Exercise Therapy', 'Hold-relax, Contract-relax, autogenic vs reciprocal inhibition.')">PDF 📄</button></div>
        <div class="topic-card"><div class="topic-title">3. Resisted Exercise (PRE)</div><button class="btn btn-pdf" onclick="generatePDF('PRE Regimens', 'Exercise Therapy', 'DeLorme, Oxford, and DAPRE progressive resistance exercise protocols.')">PDF 📄</button></div>
        <div class="topic-card"><div class="topic-title">4. Suspension Therapy</div><button class="btn btn-pdf" onclick="generatePDF('Suspension Therapy', 'Exercise Therapy', 'Axial vs Pendular suspension, pulleys, and muscle re-education.')">PDF 📄</button></div>
        <div class="topic-card"><div class="topic-title">5. Joint Mobilization (Maitland/Kaltenborn)</div><button class="btn btn-pdf" onclick="generatePDF('Joint Mobilization', 'Exercise Therapy', 'Grades of mobilization, convex-concave rule, and indications.')">PDF 📄</button></div>
        <button class="btn btn-back" onclick="showScreen('subjects-page')">⬅ Back to Subjects</button>
    </div>

    <!-- 9. YOGA QUESTIONS -->
    <div id="yoga-page" class="hidden">
        <h1>🧘 Yoga Topics</h1>
        <div class="topic-card"><div class="topic-title">1. Ashtanga Yoga (8 Limbs)</div><button class="btn btn-pdf" onclick="generatePDF('Ashtanga Yoga', 'Yoga', 'Yama, Niyama, Asana, Pranayama, Pratyahara, Dharana, Dhyana, Samadhi.')">PDF 📄</button></div>
        <div class="topic-card"><div class="topic-title">2. Pranayama Mechanics & Benefits</div><button class="btn btn-pdf" onclick="generatePDF('Pranayama', 'Yoga', 'Types (Anulom-Vilom, Kapalbhati), physiological effects on ANS and respiration.')">PDF 📄</button></div>
        <div class="topic-card"><div class="topic-title">3. Surya Namaskar Analysis</div><button class="btn btn-pdf" onclick="generatePDF('Surya Namaskar', 'Yoga', '12 poses, kinesiological muscle involvement, and physiological benefits.')">PDF 📄</button></div>
        <div class="topic-card"><div class="topic-title">4. Therapeutic Yoga in Back Pain</div><button class="btn btn-pdf" onclick="generatePDF('Yoga for Back Pain', 'Yoga', 'Indications, contraindications, and specific asanas for lumbar spine health.')">PDF 📄</button></div>
        <div class="topic-card"><div class="topic-title">5. Shatkarma (Cleansing Techniques)</div><button class="btn btn-pdf" onclick="generatePDF('Shatkarma', 'Yoga', 'Six yogic cleansing techniques (Neti, Dhauti, Nauli, Basti, Kapalbhati, Trataka).')">PDF 📄</button></div>
        <button class="btn btn-back" onclick="showScreen('subjects-page')">⬅ Back to Subjects</button>
    </div>

</div>

<script>
    // Screen Navigation Function
    function showScreen(screenId) {
        const screens = ['landing-page', 'subjects-page', 'pathology-page', 'pharmacology-page', 'microbiology-page', 'biomechanics-page', 'electrotherapy-page', 'exercisetherapy-page', 'yoga-page'];
        screens.forEach(id => document.getElementById(id).classList.add('hidden'));
        document.getElementById(screenId).classList.remove('hidden');
        window.scrollTo(0, 0);
    }

    // Dynamic PDF Generator Function using jsPDF
    function generatePDF(topicName, subjectName, content) {
        const { jsPDF } = window.jspdf;
        const doc = new jsPDF();

        // Header Style
        doc.setFillColor(26, 54, 93);
        doc.rect(0, 0, 210, 40, 'F');
        
        doc.setTextColor(255, 255, 255);
        doc.setFontSize(22);
        doc.text("Manoj Khant ki Notes", 105, 18, { align: "center" });
        
        doc.setFontSize(12);
        doc.text(`Subject: ${subjectName} | Topic: ${topicName}`, 105, 30, { align: "center" });

        // Content Body
        doc.setTextColor(30, 41, 59);
        doc.setFontSize(16);
        doc.text(`Topic: ${topicName}`, 14, 55);

        doc.setFontSize(11);
        doc.setTextColor(71, 85, 105);
        
        const splitText = doc.splitTextToSize(content, 180);
        doc.text(splitText, 14, 68);

        doc.setFontSize(10);
        doc.text("--------------------------------------------------------------------------------------------------", 14, 120);
        doc.text("Note: High-yield BPT exam revision points. Prepared for BPT Students.", 14, 130);

        // Footer
        doc.setFontSize(9);
        doc.setTextColor(148, 163, 184);
        doc.text("Generated via Manoj Khant Notes Web Portal", 105, 285, { align: "center" });

        // Save PDF
        doc.save(`${topicName.replace(/[^a-zA-Z0-0]/g, "_")}_Notes.pdf`);
    }
</script>

</body>
</html>
