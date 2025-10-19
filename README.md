🧠 AI Career Coach – Your Personalized AI-Powered Career Assistant

An intelligent full-stack web app that helps users plan, grow, and accelerate their careers using AI-driven insights, personalized guidance, and real-time learning recommendations.

✨ Features

✅ AI-Powered Career Guidance – Uses Google Gemini API to analyze user skills, goals, and job trends.
✅ Interactive Dashboard – Track progress, insights, and AI recommendations.
✅ Resume Review & Optimization – Upload your resume and get instant AI feedback.
✅ Job Fit Analysis – Compare your profile with market requirements using Gemini embeddings.
✅ Learning Path Generator – Suggests tailored learning paths based on your skills.
✅ Clerk Authentication – Secure sign-in with Google, GitHub, or email.
✅ Real-Time AI Tasks – Automated async tasks powered by Inngest (background career data fetching, periodic updates).
✅ PostgreSQL Database – Hosted on NeonDB, managed via Prisma ORM.
✅ Beautiful UI/UX – Built with Shadcn UI and Tailwind CSS for a sleek, responsive interface.

🏗️ Tech Stack
Category	Technology
Frontend	React 19, Next.js 15, TypeScript
Styling	Tailwind CSS, Shadcn UI
Authentication	Clerk
Database	NeonDB (PostgreSQL)
ORM	Prisma
Background Jobs	Inngest
AI Integration	Google Gemini API
Deployment	Vercel / Railway
🧩 Folder Structure
ai-career-coach/
│
├── app/
│   ├── (auth)/          # Clerk auth pages
│   ├── dashboard/       # User dashboard pages
│   ├── api/             # Route handlers (Next.js API routes)
│   └── layout.tsx       # Root layout
│
├── components/
│   ├── ui/              # Shadcn UI components
│   ├── charts/          # Data visualizations
│   └── ai/              # Gemini-powered features
│
├── lib/
│   ├── prisma.ts        # Prisma client setup
│   ├── inngest.ts       # Inngest setup
│   ├── auth.ts          # Clerk middleware
│   └── gemini.ts        # Gemini API configuration
│
├── prisma/
│   └── schema.prisma    # Database schema
│
├── public/
│   └── assets/          # Logos, icons, etc.
│
├── .env.example         # Environment variables template
├── package.json
├── README.md
└── tailwind.config.js

⚙️ Environment Variables

Create a .env file in the root directory and configure the following:

# Database
DATABASE_URL="your_neondb_connection_string"

# Clerk Authentication
NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY="your_clerk_publishable_key"
CLERK_SECRET_KEY="your_clerk_secret_key"

# Gemini AI
GEMINI_API_KEY="your_google_gemini_api_key"

# Inngest
INNGEST_API_KEY="your_inngest_api_key"
INNGEST_EVENT_KEY="your_inngest_event_key"

# Next.js
NEXT_PUBLIC_APP_URL="http://localhost:3000"

🚀 Installation
1️⃣ Clone the repository
git clone https://github.com/yourusername/ai-career-coach.git
cd ai-career-coach

2️⃣ Install dependencies
npm install

3️⃣ Set up Prisma & Database
npx prisma generate
npx prisma migrate dev --name init

4️⃣ Run the development server
npm run dev


The app will be available at 👉 http://localhost:3000

🧠 AI Workflows (Gemini + Inngest)

Career Insight Workflow:
Periodically fetches new job trend data and suggests new learning paths.

Resume Optimization Workflow:
Takes resume text → Sends to Gemini → Returns actionable feedback → Updates dashboard.

Skill Gap Analysis Workflow:
Compares user skill set with trending roles → Recommends top 3 improvement areas.

🛢️ Database (Prisma + NeonDB)

Example schema.prisma snippet:

model User {
  id          String  @id @default(cuid())
  email       String  @unique
  name        String?
  careerGoal  String?
  skills      String[]
  insights    Json?
  createdAt   DateTime @default(now())
  updatedAt   DateTime @updatedAt
}

🔐 Authentication (Clerk)

Login with Google / GitHub / Email

Session management handled automatically

Middleware applied to protect routes like /dashboard and /api/*

🪄 UI & Styling

Built using Shadcn UI components and Tailwind CSS utilities.

Example button component:

import { Button } from "@/components/ui/button";

export function AIButton() {
  return <Button className="bg-gradient-to-r from-indigo-500 to-blue-600 text-white">Ask AI</Button>;
}

📡 Deployment

You can easily deploy to Vercel:

vercel deploy


Make sure your environment variables are added to Vercel → Project Settings → Environment Variables.

For Inngest, connect the project at https://inngest.com
 and configure your deployed URL.



💡 Future Enhancements

🧭 Integrate LinkedIn job scraping API

🗂️ Add “Interview Coach” with AI roleplay

📈 Include career growth analytics

🎯 Personalized goal tracker with weekly updates

📜 License

This project is licensed under the MIT License – feel free to use, modify, and distribute.
