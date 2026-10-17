# 👋 Hi there, I'm Muhamad Ifan Fahrian

<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=28&duration=3000&pause=500&color=00D9FF&center=true&vCenter=true&width=500&height=50&lines=Computer+Science+Student;Full-Stack+Web+Developer;Code+%26+Coffee+Enthusiast;Business-Driven+Developer;Problem+Solver" alt="Typing SVG" />
</p>

<p align="center">
  <img src="https://komarev.com/ghpvc/?username=LifanXian&label=Profile%20Views&color=0e75b6&style=flat" alt="Profile Views" />
  <img src="https://img.shields.io/github/followers/LifanXian?label=Followers&style=social" alt="Followers" />
  <img src="https://img.shields.io/github/stars/LifanXian?label=Stars&style=social" alt="Stars" />
</p>

---

## 🎓 About Me

<img align="right" src="https://raw.githubusercontent.com/MartinHeinz/MartinHeinz/master/wave.gif" width="200" alt="Waving animation" />

I'm a **Computer Science student** at **Universitas Muhammadiyah Sukabumi (UMMI)** who bridges the gap between technical complexity and business needs. I don't just write code; I build solutions that streamline operations, improve user experiences, and solve real-world problems. 

Whether it's developing a full-stack web application or deploying machine learning models, I focus on clean architecture, effective communication, and measurable impact.

### 💡 What I'm Up To
- 🔭 **Currently building:** A comprehensive Cafe Management System (Laravel) to automate F&B operations.
- 🌱 **Learning:** Advanced PHP, API architecture, and translating data insights into business strategies.
- 🤝 **Collaboration:** Actively looking for open-source projects and team collaborations.
- ⚡ **Fun fact:** I can debug faster with a cup of coffee and a good lo-fi playlist ☕
- 📍 **Based in:** Sukabumi, Indonesia

### 🎯 2026 Goals
- [x] Build and deliver a complete cafe management system
- [x] Deploy a machine learning model to Hugging Face
- [ ] Collaborate on cross-functional team projects
- [ ] Contribute to 3+ open-source repositories
- [ ] Learn React Native to expand multi-platform capabilities

---

## 🧠 Mindset & Soft Skills
- **🗣️ Communication:** Able to translate complex technical jargon into simple business terms for stakeholders.
- **📈 Business Acumen:** Focused on creating features that actually provide value to users and optimize workflow.
- **🤝 Team Player:** Familiar with Git collaboration, code reviews, and pair programming concepts.

---

## 🛠️ Tech Stack

### 💻 Frontend Development
<p align="left">
  <img src="https://skillicons.dev/icons?i=html,css,js,bootstrap,tailwind,react,vue" />
</p>

### ⚙️ Backend & Database
<p align="left">
  <img src="https://skillicons.dev/icons?i=php,mysql,laravel,postgresql,nodejs,express" />
</p>

### 🧰 Tools & Environment
<p align="left">
  <img src="https://skillicons.dev/icons?i=git,github,vscode,postman,linux,docker,figma" />
</p>

### 📊 Data Science & ML
<p align="left">
  <img src="https://skillicons.dev/icons?i=python" />
  <img src="https://img.shields.io/badge/Scikit--learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white" />
  <img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white" />
  <img src="https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white" />
  <img src="https://img.shields.io/badge/Gradio-FF6B6B?style=for-the-badge&logo=gradio&logoColor=white" />
</p>

---

## 🚀 Featured Projects

### 🏪 1. Cafe Management System (POS)
[![Cafe Management](https://img.shields.io/badge/Repository-Cafe_Management-4CAF50?style=for-the-badge&logo=github)](https://github.com/LifanXian/cafe-management)

A full-stack web application designed to digitalize local F&B businesses.

*   **⚠️ The Problem:** Local cafes often struggle with manual order tracking, mismatched inventory, and difficulty in generating accurate monthly sales reports.
*   **💡 The Solution:** Built a centralized Point of Sale (POS) and inventory system using **Laravel 10** and **MySQL**, featuring an intuitive UI with **Tailwind CSS**.
*   **📈 The Impact:** Streamlines daily operations, prevents stockouts through real-time inventory updates, and provides owners with clear financial insights.

<details>
<summary>💻 Peek at the core logic (Order Processing)</summary>

```php
// Ensuring seamless order transaction and real-time inventory deduction
public function processOrder(Request $request) {
    DB::beginTransaction();
    try {
        $order = Order::create([
            'customer_id' => $request->customer_id,
            'total' => $request->total,
            'payment_method' => $request->payment_method
        ]);
        
        foreach($request->items as $item) {$order->items()->create($item);$this->deductInventoryStock($item['product_id'],$item['quantity']); // Business logic to prevent stockouts
        }
        
        DB::commit();
        return response()->json(['order' => $order, 'message' => 'Transaction successful!']);
    } catch (\Exception $e) {
        DB::rollBack();
        return response()->json(['error' => 'Transaction failed. Please try again.'], 500);
    }
}
