# 🚀 Quick Start Guide - Physical AI Textbook

## For Developers

### Prerequisites
- Python 3.9+ 
- Node.js 18+
- Docker (optional, for backend)

### Backend Setup (FastAPI)

```bash
# Navigate to backend
cd backend

# Create virtual environment
python -m venv venv

# Activate virtual environment
# On Windows:
venv\Scripts\activate
# On macOS/Linux:
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt

# Set environment variables (create .env file)
cat > .env << EOF
GEMINI_API_KEY=your_key_here
QDRANT_API_KEY=your_key_here
QDRANT_HOST=your_host_here
DATABASE_URL=your_db_url_here
EOF

# Run server locally
python main.py
# Server runs on http://localhost:8000
# API docs: http://localhost:8000/docs
```

### Frontend Setup (React + Docusaurus)

```bash
# Navigate to frontend
cd frontend/my-website

# Install dependencies
npm install

# Set environment variables
cat > .env.local << EOF
VITE_API_URL=http://localhost:8000
EOF

# Run development server
npm run start
# Site runs on http://localhost:3000
```

### Environment Variables Needed

**Backend (.env)**
```
GEMINI_API_KEY=sk-xxxx...
QDRANT_API_KEY=xxxxx...
QDRANT_HOST=https://xxxxx-xxxxx.qdrant.io
DATABASE_URL=postgresql://user:pass@host:5432/db
CORS_ORIGINS=http://localhost:3000,https://vercel-domain.com
```

**Frontend (.env.local)**
```
VITE_API_URL=http://localhost:8000
VITE_API_TIMEOUT=30000
```

---

## Project Structure

```
├── backend/              # FastAPI server
│   ├── main.py          # Entry point
│   ├── src/
│   │   ├── api/         # API routes
│   │   ├── services/    # Business logic
│   │   ├── models/      # Data models
│   │   └── middleware/  # CORS, error handling
│   └── requirements.txt
│
└── frontend/            # React + Docusaurus
    └── my-website/
        ├── docs/        # Course content (Weeks 1-13)
        ├── src/
        │   ├── components/  # React components
        │   ├── pages/       # Custom pages
        │   └── hooks/       # Custom hooks
        └── package.json
```

---

## Key Features to Test

### 1. RAG Chatbot
- Open chatbot widget (bottom right)
- Ask: "What is ROS2?"
- Should get answer with source citations

### 2. Text Selection
- Highlight any text on page
- Click "🤔 Ask about this" button
- Chat will show scoped answer

### 3. Mobile Responsiveness
- Open on mobile browser
- All content should be readable
- Chat widget should be accessible

---

## Deployment

### Frontend (Vercel)
```bash
# Push to GitHub
git add .
git commit -m "Your message"
git push

# Vercel auto-deploys on push
# Check: https://speckit-book-hackathon-io.vercel.app/
```

### Backend (Hugging Face Spaces)
1. Update repo on Hugging Face
2. HF auto-deploys Docker image
3. Check: https://ashnaali22-hackhathon-backend.hf.space/docs

---

## Troubleshooting

### Backend Issues
```bash
# Check if port 8000 is already in use
netstat -an | grep 8000

# Check dependencies
pip list | grep -E "fastapi|qdrant|google"

# View detailed logs
python main.py --log-level debug
```

### Frontend Issues
```bash
# Clear npm cache
npm cache clean --force

# Reinstall dependencies
rm -rf node_modules package-lock.json
npm install

# Check build
npm run build
```

### API Connection Issues
- Verify `VITE_API_URL` points to correct backend
- Check CORS settings in backend
- Browser console should show any API errors
- Use Network tab in DevTools to debug requests

---

## Next Steps (Optional)

1. **Add User Authentication**
   - Implement Better-Auth
   - Add login/register pages

2. **Multi-language Support**
   - Add Urdu translations
   - Implement i18n library

3. **Progress Tracking**
   - Save user bookmarks
   - Track completed sections

---

**Questions?** Check the docs or raise an issue! 🚀
