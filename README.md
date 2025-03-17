# 📌 API Documentation: Hirepilot.io | AI-Powered Employee-Employer Matchmaking
🚀 **Version:** 1.0  
📅 **Last Updated:** March 2025  
🌐 **Base URL:** `https://api.hirepilot.io/v1/`  

---

## 📖 Table of Contents
1. [Authentication & User Management](#1-authentication--user-management)
2. [AI-Powered Matchmaking](#2-ai-powered-matchmaking)
3. [Shortlisting & Interview Scheduling](#3-shortlisting--interview-scheduling)
4. [AI-Powered Resume Parsing & Job Analysis](#4-ai-powered-resume-parsing--job-analysis)
5. [Notifications & Messaging](#5-notifications--messaging)
6. [Postman & API Testing](#6-postman--api-testing)

---

## 1️⃣ Authentication & User Management
### 1.1 Register a New Employer or Candidate
```http
POST https://api.hirepilot.io/v1/auth/register
```
#### Request Body:
```json
{
  "name": "John Doe",
  "email": "john@example.com",
  "password": "SecurePass123",
  "role": "employer",
  "company": "Tech Corp",
  "industry": "Software Development"
}
```
#### Response:
```json
{
  "user_id": "12345",
  "message": "User registered successfully.",
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI..."
}
```

---

### 1.2 User Login
```http
POST https://api.hirepilot.io/v1/auth/login
```
#### Request Body:
```json
{
  "email": "john@example.com",
  "password": "SecurePass123"
}
```
#### Response:
```json
{
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI...",
  "user_id": "12345",
  "message": "Login successful"
}
```

---

### 1.3 Generate API Key
```http
POST https://api.hirepilot.io/v1/auth/generate-key
```
#### Request Body:
```json
{
  "user_id": "12345",
  "scope": "read_write"
}
```
#### Response:
```json
{
  "api_key": "ak12345abcdef67890",
  "expires_in": "2026-01-01T00:00:00Z"
}
```

---

## 2️⃣ AI-Powered Matchmaking
### 2.1 Get AI-Recommended Jobs for a Candidate
```http
GET https://api.hirepilot.io/v1/match/jobs/{candidate_id}
```
#### Response:
```json
{
  "candidate_id": "12345",
  "recommended_jobs": [
    {
      "job_id": "JOB678",
      "title": "Senior Software Engineer",
      "company": "Google",
      "location": "San Francisco, CA",
      "match_score": 94.5,
      "skills_matched": ["Python", "Machine Learning", "TensorFlow"]
    }
  ]
}
```

---

### 2.2 Get AI-Recommended Candidates for a Job
```http
GET https://api.hirepilot.io/v1/match/candidates/{job_id}
```
#### Response:
```json
{
  "job_id": "JOB678",
  "recommended_candidates": [
    {
      "candidate_id": "CAND123",
      "name": "Alice Johnson",
      "experience": "5 years",
      "skills": ["Python", "Deep Learning", "TensorFlow"],
      "match_score": 96.0
    }
  ]
}
```

---

## 3️⃣ Shortlisting & Interview Scheduling
### 3.1 Fetch Employer’s Shortlist for a Specific Job
```http
GET https://api.hirepilot.io/v1/shortlist/{employer_id}/{job_id}
```
#### Response:
```json
{
  "employer_id": "EMP789",
  "job_id": "JOB678",
  "shortlisted_candidates": [
    {
      "candidate_id": "CAND123",
      "name": "Alice Johnson",
      "status": "Interview Scheduled"
    }
  ]
}
```

---

### 3.2 Schedule an Interview
```http
POST https://api.hirepilot.io/v1/interview/schedule
```
#### Request Body:
```json
{
  "candidate_id": "CAND123",
  "employer_id": "EMP789",
  "job_id": "JOB678",
  "interview_slot": "2025-03-20T10:00:00Z",
  "calendar_type": "Google"
}
```
#### Response:
```json
{
  "message": "Interview scheduled successfully.",
  "calendar_event_link": "https://calendar.google.com/event?eid=xyz"
}
```

---

## 4️⃣ AI-Powered Resume Parsing & Job Analysis
### 4.1 Parse Resume for Skill Extraction
```http
POST https://api.hirepilot.io/v1/ai/resume-parse
```
#### Request Body:
```json
{
  "resume_pdf": "base64_encoded_file"
}
```
#### Response:
```json
{
  "candidate_name": "Alice Johnson",
  "skills_extracted": ["Python", "Machine Learning", "TensorFlow"]
}
```

---

### 4.2 Analyze Job Description for AI Matching
```http
POST https://api.hirepilot.io/v1/ai/job-description-analyze
```
#### Request Body:
```json
{
  "job_description_text": "We are looking for a Machine Learning Engineer with Python and TensorFlow experience."
}
```
#### Response:
```json
{
  "required_skills": ["Machine Learning", "Python", "TensorFlow"],
  "ai_insights": "The job prefers candidates with strong AI/ML experience."
}
```

---

## 5️⃣ Notifications & Messaging
### 5.1 Send Message to a Candidate
```http
POST https://api.hirepilot.io/v1/messages/send
```
#### Request Body:
```json
{
  "sender_id": "EMP789",
  "receiver_id": "CAND123",
  "message": "We would like to invite you for an interview."
}
```
#### Response:
```json
{
  "status": "sent",
  "timestamp": "2025-03-17T12:34:56Z"
}
```

---

## Support
   - Email: `support@hirepilot.io`  

---
