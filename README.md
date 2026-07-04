# 🤖 AI Kubernetes Troubleshooting Agent

An AI-powered platform that automatically investigates Kubernetes failures, analyzes logs, events, and cluster state, identifies root causes, and suggests fixes — all through a live, deployable dashboard.

---

## 📌 Overview

Debugging a broken pod usually requires manually running multiple commands like:

* `kubectl describe`
* Checking logs
* Inspecting events
* Reviewing deployment YAMLs

This project **automates the entire debugging workflow**.

---

## 🚀 Key Features

* 🔍 Automatically investigates Kubernetes failures
* 📊 Analyzes logs, events, and live cluster state
* 🧠 Uses LLMs to identify root causes
* 🛠️ Suggests concrete fixes (kubectl commands / YAML updates)
* 🗂️ Stores investigation history for future reference
* 🌐 Deployable as a real, publicly accessible application

---

## 🏗️ Architecture

The system is organized into multiple layers:

* **Kubernetes Cluster**
  Source of truth — pods, deployments, services, events, logs

* **Investigation Layer**
  Collects evidence using:

  * Pod Inspector
  * Logs Collector
  * Events Analyzer
  * Deployment Inspector
  * Network Inspector

* **AI Kubernetes Agent**
  Builds prompts, reasons using LLMs, identifies root cause, and assigns confidence score

* **Backend (InsForge)**
  Handles authentication, APIs, investigation history, and real-time updates

* **Frontend Dashboard**
  Triggers investigations and displays results (root cause, fixes, progress)

* **Deployment (InsForge)**
  Deploys application and generates a public URL



<img width="882" height="1280" alt="WhatsApp Image 2026-07-04 at 17 42 07" src="https://github.com/user-attachments/assets/2a0441e6-f9a9-4499-b08e-bd7c5d47940a" />











🔄 End-to-End Workflow


User triggers an investigation from the dashboard
Investigation Layer collects cluster data
AI Agent processes evidence using LLM
Root cause is identified with confidence score
Suggested fixes are generated
Results are displayed in real-time on dashboard
Investigation is stored for future reference



## 🧪 Example: Failure Investigation

**Issue:** Payment service unavailable

### 🔍 Agent Investigation Steps

* ✅ Pod status checked
* ✅ Logs collected
* ✅ Events analyzed

### 🚨 Detected Problem

`CrashLoopBackOff`

### 🧠 Root Cause

Missing `DATABASE_URL` environment variable

### 📊 Confidence

**94%**

### 🛠️ Suggested Fix

Update `deployment.yaml` and add the missing secret reference

### 🛡️ Prevention

Add startup validation checks

---

## 🛠️ Supported Kubernetes Problems

* CrashLoopBackOff
* ImagePullBackOff
* OOMKilled
* Pending Pods
* Resource Exhaustion
* Deployment Rollout Failures
* Service Selector Mismatch
* DNS Resolution Issues
* Readiness / Liveness Probe Failures
* Networking Issues

---

## ⚙️ Tech Stack

* **Orchestration:** FastAPI
* **Cluster Access:** Kubernetes API / `kubectl`
* **AI Reasoning:** OpenRouter (Claude, GPT, DeepSeek)
* **Backend / Auth / Realtime / Storage:** InsForge
* **Deployment:** InsForge (Public URL generation)





