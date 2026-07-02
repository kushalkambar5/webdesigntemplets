1. Logging
2. Rate limiting 
3. Caching 
4. Rollback strategy
5. Alerts
6. Database indexes - index the fields you query most
7. Markdown file for agents/bots - (in Headers accept - text/markdown)
    - ex:
        
        ```powershell
        # WisprType — Voice to text, anywhere on macOS
        
        > A native macOS dictation app powered by on-device AI. Hold a key, speak,
        > and your words appear wherever you type. Private by default, blazingly
        > fast on Apple Silicon.
        
        - **Website:** https://wisprtype.com
        - **Platform:** macOS 12+ (Apple Silicon)
        - **License/Pricing:** Free during early access
        - **Download:** https://wisprtype.com/WisprType_1.0.0_aarch64.dmg
        - **Privacy policy:** https://wisprtype.com/privacy-policy
        - **Contact:** contact@wisprtype.com — https://wisprtype.com/contact
        
        ## How it works
        
        1. Hold the configured push-to-talk hotkey (Right ⌘ by default).
        2. Speak naturally. Audio is captured locally.
        3. Speech-to-text runs on-device via WhisperKit (Apple Silicon, Core ML).
        4. Optional Smart Typing post-processing removes filler words, fixes
           self-corrections, and applies punctuation.
        5. The cleaned transcript is pasted into the focused application.
        
        ## Engines
        
        WisprType supports both local and cloud speech-to-text engines.
        
        ### Local (default, private)
        
        | Model                   | Approx. size | Notes                  |
        | ----------------------- | ------------ | ---------------------- |
        | Whisper Tiny            | ~75 MB       | Fastest, lightest      |
        | Whisper Base            | ~150 MB      | Default — recommended  |
        | Whisper Small           | ~500 MB      | Better accuracy        |
        | Whisper Medium          | ~1.5 GB      | High accuracy          |
        | Whisper Large v3        | ~3 GB        | Best accuracy          |
        | Distil-Whisper Large v3 | —            | Distilled variant      |
        
        ### Cloud (optional, opt-in)
        
        | Provider | Default STT model        |
        | -------- | ------------------------ |
        | OpenAI   | gpt-4o-transcribe        |
        | Groq     | whisper-large-v3-turbo   |
        | Deepgram | nova-3                   |
        
        Cloud providers are never used unless you explicitly configure an API key
        in Settings → Models. Keys are stored locally and only used to authenticate
        requests you initiate.
        
        ## Smart Typing
        
        AI-powered transcript cleanup that removes filler words, fixes
        self-corrections, and improves punctuation/formatting.
        
        - **Local mode (default):** Runs Llama 3.2 3B locally via Apple's MLX
          framework. No transcript data leaves your machine.
        - **Cloud mode:** Reuses your configured cloud provider for cleanup. Raw
          transcript text and dictionary words are sent to that provider only.
        
        ## Custom dictionary
        
        Add domain-specific words across categories — `Name`, `Technical`,
        `Medical`, `Legal`, `Other` — to bias recognition. The dictionary is
        stored locally and never transmitted.
        
        ## Privacy summary
        
        - Speech-to-text runs entirely on-device by default.
        - No audio, transcripts, or personal content are sent to WisprType
          servers.
        - Anonymous, opt-in usage telemetry only (PostHog, no IP, no transcript
          text).
        - Cloud providers are opt-in and use API keys you supply.
        - See the full Privacy Policy.
        
        ## System permissions
        
        - **Microphone** — to capture audio for transcription.
        - **Accessibility** — for the global hotkey and paste automation.
        - **Audio Input** — entitlement for audio device access.
        - **Apple Events** — to paste text into the active application.
        
        ## Discovery for agents
        
        - API catalog (RFC 9727): https://wisprtype.com/.well-known/api-catalog
        - Sitemap: https://wisprtype.com/sitemap.xml
        - Web app manifest: https://wisprtype.com/manifest.webmanifest
        - Agent skills index: https://wisprtype.com/.well-known/agent-skills/index.json
        - Markdown via content negotiation: send `Accept: text/markdown` to any
          HTML route on this site.
        ```
        
8. Debouncing and Throttling
9. List Virtualization
10. Code Splitting
11. Memorization

# Tools, Libraries for Web Dev

- Better Auth - Auth
- Zod - Input Validation
- Lazy Loading
- BetterDB/Signoz - Frontend Logging
- Winston - Logging
- Corsair - Alternative for MCP
- Groq/OpenRouter - LLM APIs
- mem0 - memory for LLM
- Qdrant - VectorDB
- Cloudinary - Media DB
- Posthog - Analytics
- Boneyard - Skeleton screens
- Caching
- Image Optimisation (Use WebP format for 30% reduced size)
- Pagination
- Avoid Overfetching
- react-helmet-async - different titles for every page, SEO
- Add to Google search console
- Google tag manager
- add robots.txt, sitemap.xml
- add to google search concole also there add pages in sitemaps
- 
- 
- 
- Create Websites for AI Agents
    - Here is the prompt to make your site agent friendly.
        
        You are an expert web developer optimizing a website to be fully AI-agent-friendly, following Google's 2026 "Build Agent-Friendly Websites" guidelines from web.dev. Refactor and build the entire website with the following non-negotiable standards:
        
        1. SEMANTIC HTML FIRST
        - Replace all styled <div> and <span> elements with proper semantic tags: <header>, <nav>, <main>, <section>, <article>, <aside>, <footer>, <button>, <a>, <ul>, <ol>, <figure>, etc.
        - Never use <div onClick> for buttons — always use <button>.
        - Use proper heading hierarchy (h1 → h2 → h3) without skipping levels.
        1. ACCESSIBLE FORMS
        - Every <input>, <select>, and <textarea> must have a matching <label> connected via the "for" attribute and matching "id".
        - Add descriptive placeholder text and aria-label where needed.
        - Group related fields with <fieldset> and <legend>.
        - Mark required fields with the required attribute and aria-required.
        1. INTERACTIVE ELEMENT CLARITY
        - Add cursor: pointer to all clickable elements in CSS.
        - Use aria-label, aria-describedby, and role attributes on all interactive components.
        - Ensure focus states are visible and keyboard navigation works end-to-end.
        - Add aria-live regions for dynamic content updates.
        1. STABLE & PREDICTABLE LAYOUT
        - Keep navigation, header, and footer structurally identical across all pages.
        - Use consistent class naming and component structure.
        - Avoid layout shifts — reserve space for images, ads, and async content.
        - Make sure key actions (CTA buttons, search, login) are in predictable locations.
        1. METADATA & STRUCTURED DATA
        - Add complete meta tags: title, description, OpenGraph, Twitter cards.
        - Implement JSON-LD structured data (Schema.org) for all relevant content types: Organization, Product, Article, BreadcrumbList, FAQPage, etc.
        - Include canonical URLs and proper hreflang tags if multilingual.
        1. MACHINE-READABLE CONTENT
        - Use descriptive alt text on every image.
        - Add transcripts or captions for video/audio.
        - Use <time datetime=""> for dates, <address> for contact info.
        - Ensure prices, ratings, availability use Schema.org markup.
        1. WEBMCP-READY ARCHITECTURE
        - Structure key user actions (search, add to cart, contact, book, subscribe) as discrete, well-named functions/endpoints that could be exposed as agent tools.
        - Document all primary user flows in code comments.
        - Keep URLs clean, RESTful, and human-readable.
        1. PERFORMANCE & ROBUSTNESS
        - Server-render or pre-render content when possible (avoid pure client-side rendering for critical content).
        - Ensure the site works without JavaScript for core content.
        - Add a robots.txt and sitemap.xml.
        - Allow AI crawlers explicitly in robots.txt.
        
        Audit the entire codebase against these standards, refactor every page, and output the cleaned, agent-friendly version. After refactoring, give me a checklist showing what was changed in each category.
        
- **AI-Driven Testing Workflow (Copilot + Opus)**
    
    **Overview**
    
    This workflow helps you design a complete testing strategy for any application using AI before writing or running tests. It separates planning from execution to reduce blind spots and improve test coverage.
    
    **Step 1: Meta-Prompt (Prompt-1)**
    
    Use the following prompt to generate the Copilot-ready prompt:
    
    You are a prompt engineer. Generate a single, clear prompt that will be given to GitHub Copilot (using Claude Opus) and instruct Opus to read and understand the entire application codebase and available documentation, then create a comprehensive implementation plan for testing the application. The plan must focus strictly on strategy and planning, not on executing tests or writing test code, and should cover core testing phases, edge cases, load and scalability concerns, async vs sync behavior, concurrency issues, failure scenarios, and data consistency risks. The generated Copilot prompt must be concise, structured, IDE-friendly, divided into clear phases, explain what to test and why (not how), be reusable for any application, and output only the final Copilot prompt text with no explanations or commentary.
    
    **Step 2: Copilot Prompt (Prompt-2)**
    
    Paste the generated prompt into GitHub Copilot (Claude Opus).
    
    Copilot will:
    
    - Read the entire codebase and documentation
    - Analyze system behavior and architecture
    - Generate a phase-wise testing implementation plan
    
    No tests are executed at this stage.
    
    **Step 3: Testing Implementation Plan**
    
    The plan typically covers:
    
    - Functional testing scope
    - Edge cases and boundary conditions
    - Load and scalability risks
    - Async vs sync and concurrency issues
    - Failure scenarios and recovery paths
    - Data consistency and integrity
    
    Each phase explains what to test and why, not how to write tests.
    
    **Step 4: Execution**
    
    Once the plan is ready, you can:
    
    - Follow it manually, or
    - Use Copilot to execute or generate tests one phase at a time
    
    Execution is intentionally decoupled from planning.
    
    **Why This Workflow Works**
    
    - Forces thinking before execution
    - Reduces missed edge cases
    - Works for any stack or app size
    - Turns Copilot into a planning partner, not just a code tool

# Optionals

- Add a real faces of human(founder/etc) to build trust
- Add the your reels/yt embeddings
- Our results and works
- Clients testimonials(Videos if possible)
- Design Patterns - https://docs.google.com/document/d/15HQRLUMUIBp5NpnwF6BTcF-iHpdIeZHt/edit
- Guidelines to make good and trust worthy websites - https://drive.google.com/file/d/1REwkO7lCBbtV-3V--fM0fMAWLLYML-Nl/view?usp=sharing

# Optional Animations

- Scroll Animation (Pizza Animation)
    
    ```powershell
    1) Gemini Prompt
    
    Create a high-quality product image using the uploaded pizza photo.
    Place the pizza floating in the center of the frame with a slight natural angle, similar to premium food and fast-casual pizza brand ads.
    Use soft, clean studio lighting with subtle highlights on the cheese and ingredients to make the pizza look appetizing, warm, and premium.
    Keep all original surface details, textures, toppings, and colors sharp and realistic.
    
    STYLE:
    • Modern DTC food-brand aesthetic
    • Minimal, bold visual look
    • Clean color separation
    • Slight vignette but no visible gradients
    
    BACKGROUND:
    • Pure solid black (#000000)
    • No reflections
    • No textures
    • No crumbs, smoke, or extra effects unless naturally formed on pizza
    
    FRAMING:
    • Full vertical frame
    • Pizza centered and floating
    • Enough margins for future motion-tracking and animation use
    
    OUTPUT:
    • High-resolution still image
    • Black background for easy masking
    • Maintain exact pizza shape, toppings layout, colors, and proportions from the original uploaded image
    
    2) Whisk Prompt
    
    Pizza Final Frame Image
    Using the uploaded pizza product image, generate the final frame of a food animation.
    The pizza should appear floating and tilted slightly forward, while multiple pizza ingredients burst dynamically around it.
    
    INGREDIENT BURST:
    • Surround the pizza with floating ingredient pieces (cheese shreds, tomato slices, basil, olives, pepperoni, vegetables, etc.) arranged in a dynamic outward explosion
    • Include a high-energy sauce splash (matching the pizza flavor — cheese stretch or tomato sauce swirl) wrapping partially around the pizza
    • Ingredients must look like high-speed food photography: sharp, crisp, suspended in mid-air
    • Keep the pizza surface and toppings clearly visible and unobstructed
    
    STYLE:
    • Clean, soft commercial food-advertising lighting
    • Bright appetizing highlights on cheese and toppings
    • Extremely sharp ingredient details — no motion blur
    • Energetic composition similar to premium pizza brand key visuals
    
    PRODUCT POSITION:
    • Center of the frame
    • Slight forward tilt for a powerful hero-shot angle
    • Ingredients positioned around the pizza with natural spacing for animation
    
    BACKGROUND:
    • Pure solid black (#000000)
    • No gradients, textures, fog, crumbs, or shadows
    • Optimized for masking and compositing in video
    
    OUTPUT:
    • High-resolution final frame
    • Pizza centered with dynamic bursting ingredient effects
    • Completely black background
    • Preserve the exact shape, proportions, textures, and colors of the uploaded pizza image
    
    3)Pizza Transition Prompt
    
    Create a dynamic transition from the mid-spin frame to the final ingredient-burst frame using the uploaded pizza product image.
    Begin with the pizza tilted left in mid-rotation against a pure black background.
    
    As the rotation continues, gradually introduce pizza ingredients entering the frame from behind and around the pizza.
    Increase the number of floating ingredients (cheese strands, tomato slices, basil leaves, olives, pepperoni, vegetables, etc.) as the motion progresses, building toward a full explosive ingredient burst.
    
    Add a high-energy pizza sauce or cheese splash emerging from behind the pizza and wrapping partially around it as the ingredients appear.
    All elements must look sharp, crisp, and suspended in high-speed motion — no motion blur.
    
    Ensure the pizza remains well-lit, centered, visually dominant, and unobstructed.
    Background must remain pure solid black (#000000) with no gradients, textures, fog, shadows, or extra effects.
    
    End the transition in the fully exploded ingredient-burst hero composition.
    
    4) Website Prompt — React JS (No Next.js)
    
    Design a premium, single-page parallax pizza website built using React.js only (no Next.js).
    
    Users must be able to dynamically configure:
    
    Pizza Name (e.g., “Cherry Pepper Pizza”)
    
    Subtitle (1–3 words)
    
    Description (1–3 sentences)
    
    Theme Color
    
    Dark / Light Mode
    
    Multiple WebP background parallax pizza animation sequences
    (one sequence per pizza variant)
    
    Hero Layout & Visual Style
    
    Create a full-screen hero section.
    
    Background
    
    Full-screen WebP image sequence
    
    Plays forward when scrolling down
    
    Plays backward when scrolling up
    
    Motion must feel cinematic, smooth, and responsive to scroll
    
    Use optimized React rendering for performance
    
    Overlay Text Block (Left Side)
    
    Displayed on top of the animated background:
    
    Large bold uppercase Pizza Name
    Example: “CHERRY PEPPER”
    
    Subtitle below (lighter weight)
    Example: “WOOD-FIRED PIZZA”
    
    Short description paragraph
    
    Two rounded CTA buttons side-by-side:
    
    Left: Transparent background, white text
    
    Right: Filled background (brand theme), black or white text depending on mode
    
    Center Area
    
    Keep visually clean
    
    No UI clutter
    
    Animation is the hero
    
    Right-Side Variant Navigation
    
    Vertically centered:
    
    Large flavor index number (01, 02, 03…)
    
    Slim navigation strip:
    
    “PREV” + arrow
    
    Divider line
    
    “NEXT” + arrow
    
    On click:
    
    Update pizza name, subtitle, description
    
    Change theme color
    
    Apply dark/light mode (if overridden)
    
    Swap WebP sequence
    
    Animate text fade out / fade in
    
    Update index number
    
    Theme & Mode
    
    Default: Dark cinematic mode
    
    Background nearly black
    
    Bright contrasting text
    
    Provide a toggle:
    
    Dark Mode
    
    Black / charcoal UI
    
    White / gray text
    
    Light Mode
    
    Off-white UI
    
    Dark text
    
    Theme color applies to:
    
    Buttons
    
    UI accents
    
    Active indicators
    
    Subtle highlights
    
    Parallax Scroll Behavior
    
    Scroll position maps to frame index
    
    Scroll down → forward frames
    
    Scroll up → reverse frames
    
    NOT autoplay
    
    Must feel physically tied to scroll
    
    Smooth, responsive React animation handling
    
    FPS stability is important
    
    Multiple Pizza Variants Support
    
    Each pizza variant has:
    
    Name
    
    Subtitle
    
    Description
    
    Theme Color
    
    Dark/Light Mode override (optional)
    
    WebP Sequence Frames Path
    
    Frame Count
    
    Loading Experience
    
    Since sequences are heavy:
    
    Before showing hero
    
    Full-screen loading overlay
    
    Brand name or logo
    
    Horizontal loading bar
    
    Optional percentage (ex: “Loading 72%”)
    
    When switching variants
    
    Show a small loading indicator near PREV/NEXT
    
    Avoid flicker
    
    Load smoothly
    
    Navigation & Sections
    
    Sticky top navbar:
    
    Left:
    
    Brand name/logo
    
    Right:
    
    Smooth-scroll links:
    
    Product
    
    Ingredients
    
    Nutrition
    
    Reviews
    
    FAQ
    
    Contact
    
    Dark/Light toggle
    
    Below Hero Sections
    
    1️⃣ Product / About the Pizza
    2️⃣ Ingredients & Benefits
    3️⃣ Nutrition Facts (styled like pizza nutrition card)
    4️⃣ Reviews / Social Proof
    5️⃣ FAQ Accordion
    6️⃣ Final CTA Section
    
    Footer
    
    Brand name/logo
    
    Links (About, Contact, Privacy, Terms)
    
    Social Icons
    
    Copyright
    
    Must visually match dark cinematic theme
    
    Black background
    
    In Short
    
    Build a cinematic scroll-controlled parallax pizza website in React.js, with WebP scroll animation backgrounds, variant switching, theme control, polished UI, and customizable pizza data.
    
    Pizza Variant Data (From You)
    
    Pizza Name: Cherry Pepper Pizza
    Subtitle: Wood-Fired Pizza
    Description:
    A bold modern take on classic pepper pizza, with a perfect balance of spice and nostalgic flavor.
    WebP Sequence Path URL:
    Frame Count: 240
    
    5) CTA Image Prompt — Converted to Pizza
    
    Create a square CTA promotional image for Cherry Pepper Pizza.
    
    Bold monochrome deep red / cherry-pepper inspired background
    
    Smooth studio gradient
    
    Clean minimal composition
    
    Pizza centered, floating or upright hero presentation
    
    Sharp premium food lighting
    
    Soft realistic shadow
    
    Surround the bottom area with:
    
    Fresh glossy red peppers
    
    Pepper slices
    
    Maybe light cheese strands
    
    Arranged like luxury food advertising
    
    Vibrant & appetizing
    
    Style:
    
    Pop-art energy
    
    High contrast
    
    Clean modern aesthetic
    
    Slight reflections
    
    Crisp edges
    
    No Memphis patterns
    
    Simple, bold color-blocked composition
    
    Mood:
    
    Playful
    
    Premium
    
    Vibrant
    
    Clean
    ```