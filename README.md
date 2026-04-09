# React Password Generator

A simple and interactive Password Generator built using **React.js**.

This application allows users to generate secure passwords based on selected criteria such as length, symbols, numbers, and uppercase/lowercase letters.

Ideal for learning React fundamentals and demonstrating deployment using Docker and NIFE.

---

## Live Demo

👉 https://fervent-volhard-f2991a.netlify.app/

---

## Overview

* Generate strong, secure passwords
* Customize password length
* Include/exclude character types
* Responsive and fast UI
* Beginner-friendly React project

---

## Features

* Uppercase letters
* Lowercase letters
* Numbers
* Symbols
* Adjustable password length
* Instant generation

---

## Tech Stack

* React.js
* JavaScript (ES6+)
* HTML5 & CSS3
* Docker

---

## Quick Start

### Prerequisites

* Node.js (v14+)
* npm or yarn
* Git

---

### 1. Clone Repository

```bash id="rpg1"
git clone https://github.com/nifetency/react_password_generator.git
cd react_password_generator
```

---

### 2. Install Dependencies

```bash id="rpg2"
npm install
```

---

### 3. Run Application

```bash id="rpg3"
npm start
```

---

### 4. Open in Browser

```id="rpg4"
http://localhost:3000
```

---

## Docker Usage

### Build Image

```bash id="rpg5"
docker build -t react-password-generator .
```

---

### Run Container

```bash id="rpg6"
docker run -p 3000:3000 react-password-generator
```

---

## Deployment on NIFE

Deploy using NIFE UI:

**Source → Build → Resources → Review → Deploy**

---

### Method 1: Docker Image (Recommended)

#### Step 1: Build & Push Image

```bash id="rpg7"
docker build -t react-password-generator .
docker tag react-password-generator <username>/react-password-generator:latest
docker push <username>/react-password-generator:latest
```

---

#### Step 2: Configure in NIFE

* Source → Docker Image
* Image → `<username>/react-password-generator:latest`

**Ports**

* Internal → `3000`
* External → `80`

---

#### Step 3: Resources

* Region → `ap-south-1`
* CPU → selected

**Recommended**

* CPU → 250m–500m
* Memory → 512MB–1GB
* Replicas → 1–2

---

#### Step 4: Deploy

Click **Deploy**

---

### Method 2: Git Repository

#### Step 1: Source

* Select GitHub repo
* Branch → `main`

---

#### Step 2: Build

* Internal Port → `3000`
* External Port → `80`
* Enable **Auto-Dockerize with Runtime**

---

#### Step 3: Security

* SAST
* SCA
* Container Scan
* IaC Scan

---

#### Step 4: Resources & Deploy

* Configure resources
* Click **Deploy**

---

## Access Application

```id="rpg8"
https://<your-nife-url>
```

---

##  Install nifectl CLI (Windows)

Follow these steps to install and set up **nifectl**:

### 1. Download

 https://github.com/nifetency/nifectl/releases

Download:

```text id="rpg9"
nifectl-windows-amd64.zip
```

---

### 2. Extract

* Right-click → Extract All
* Open folder

---

### 3. Open Terminal

* Type `cmd` in address bar

OR

* Right-click → Open in Terminal

---

### 4. Verify

```bash id="rpg10"
nifectl --help
```

---

## Deployment using nifectl (CLI)

### Prerequisites

* nifectl installed
* NIFE account

---

### Step 1: Login

```bash id="rpg11"
nifectl auth login
```

---

### Step 2: Initialize

```bash id="rpg12"
nifectl init
```

* Source → Repository
* Provider → GitHub
* Branch → `main`

---

### Step 3: Configure

* Deployment → Deployment
* Resource → CPU
* Replicas → 1

**Ports**

* Internal → `3000`
* External → `80`

---

### Step 4: Deploy

```bash id="rpg13"
nifectl deploy
```

---

### Step 5: Select Region

* Choose region (e.g., Mumbai)

---

### Step 6: Monitor

* Build → Release → Deploy

---

### Step 7: Access

* Open generated URL

---

## Dependencies

| Dependency | Purpose            |
| ---------- | ------------------ |
| React      | Frontend framework |
| Node.js    | Runtime            |
| npm        | Package manager    |

---

## Environment Variables

| Variable | Description | Default |
| -------- | ----------- | ------- |
| PORT     | App port    | 3000    |

---

## Troubleshooting

| Issue             | Solution                       |
| ----------------- | ------------------------------ |
| npm install fails | Check Node version             |
| App not starting  | Run `npm start`                |
| Port in use       | Change port                    |
| Docker issues     | Start Docker                   |
| Build fails       | Clear node_modules & reinstall |
| ImagePullErr      | Make Docker image public       |
| Blank screen      | Check browser console          |
