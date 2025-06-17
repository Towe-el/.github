# Towe-el is a project designed for Hackathon AI in Action

## Emotional clarity helper
Emotional challenges are more common and more overlooked than ever. Nearly 1 in 8 people globally live with a mental health condition, and numbers continue to rise rapidly. Yet many people lack the tools or language to understand their feelings, let alone seek support. Emotional clarity is a missing layer in everyday mental health. Toweel was created to fill this gap, offering an accessible space to pause, reflect, and understand emotions. 

## Key Features
- Voice input and text input
- AI sentiment analysis
- Visual sentiment wheel
- Personalised reflection suggestions

## System Flow Overview
```pgsql
[User Input] 
    |
    |---> [Frontend (React + Firebase Hosting)]
             |
             |---> Input Capture & Processing:
             |    • Text input (JavaScript event handling)
             |    • Speech-to-text (Web Speech API)
             |    • UI styling & layout (Tailwind CSS)
             |    • Input animations (GSAP)
             |
             |---> Sends processed input to backend
                      ↓
    [Backend API (FastAPI on Cloud Run)]
             |
             |---> Step 1: Quality Check (Gemini API - Vertex AI)
             |         - Emotional depth
             |         - Clarity
             |         - Contextual completeness
             |         - Personal voice
             |
             |---> Step 2: If passed, vectorize input
             |         - Use text-embedding-005
             |
             |---> Step 3: Vector Search in MongoDB Atlas
             |         - Search top 30 similar sentences
             |
             |---> Step 4: RAG (Gemini API again)
             |         - Combine user input + retrieved docs
             |         - Use VA model filtering
             |         - Output 3 emotions + percentages
             |
             |---> Step 5: Final Report Generation (Gemini)
             |         - Emotion definitions
             |         - Evidence from user input
             |         - Reflection + Action Suggestions
             |
             ↓
        [Response Sent to Frontend]
             |
             |---> Result Rendering & Display:
             |    • Show 3 Emotion Cards on Wheel (React components)
             |    • Wheel animations & transitions (GSAP)
             |    • Summary Report layout (Tailwind CSS)
             |    • User interaction handling (JavaScript)
             |    • Save input in MongoDB (query collection)
```

## Team
We're a small, independent team of girls based across Europe, building Toweel with care, empathy, and a deep belief in the power of emotional understanding.

We're currently exploring job and collaboration opportunities in tech, mental wellness, AI application, and creative technology.

If our work resonates with you, or if you have any questions or suggestions, we'd love to hear from you.

[**Jingchang**](https://github.com/EleanorWho) - back-end engineer

[**Yufei**](https://github.com/Siwi0w0) - front-end engineer

[**Qing**](https://www.linkedin.com/in/qing-yang-a75189270) - product designer

## Future Plan
### User Account
The first thing we want to add is user accounts, so people can track their emotional patterns over time and across devices. Right now, the demo stores queries in local storage only, which is great for privacy, but limits continuity.
    
### Voice Input
We also plan to extend voice input beyond just transcription. By analyzing vocal tone and pitch using datasets such as RADVESS, we aim to incorporate richer emotional signals. This would enable Toweel to respond not just to what users say, but also to how they sound.
    
### Mobile Responsive
We plan to refine the mobile experience further by optimising layout scaling, touch interactions, and animation performance on smaller screens. This will ensure users can fully engage with voice input, emotion cards, and reports seamlessly, whether on a desktop or mobile device.
