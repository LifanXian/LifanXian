# 👋 Hi there, I'm Muhamad Ifan Fahrian

<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=28&duration=3000&pause=500&color=00D9FF&center=true&vCenter=true&width=500&height=50&lines=Computer+Science+Student;Full-Stack+Web+Developer;Code+%26+Coffee+Enthusiast;Lifelong+Learner;Problem+Solver" alt="Typing SVG" />
</p>

<p align="center">
  <img src="https://komarev.com/ghpvc/?username=ifanfahrian&label=Profile%20Views&color=0e75b6&style=flat" alt="Profile Views" />
  <img src="https://img.shields.io/github/followers/ifanfahrian?label=Followers&style=social" alt="Followers" />
  <img src="https://img.shields.io/github/stars/ifanfahrian?label=Stars&style=social" alt="Stars" />
</p>

---

## 🎓 About Me

<img align="right" src="https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExdDh6dDkyOTgxZnZwd2JwbWtrZ2dva3QxZ3FpNHVxY3Nha3ptNzJnaCZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/L1R1tvI9svkIWwpVYr/giphy.gif" width="280" />

I'm a **Computer Science student** at **Universitas Muhammadiyah Sukabumi (UMMI)** with a burning passion for web development. I believe in the power of technology to solve real-world problems and I'm on a mission to become a full-stack developer who creates impactful digital experiences.

### 💡 What I'm Up To
- 🔭 **Currently building:** Cafe management system with Laravel
- 🌱 **Learning:** Advanced PHP, API development, and UI/UX principles
- 💡 **Interested in:** Open source, clean code, and building scalable applications
- ⚡ **Fun fact:** I can debug faster with a cup of coffee ☕
- 📍 **Based in:** Sukabumi, Indonesia

### 🎯 2026 Goals
- [x] Build a complete cafe management system
- [x] Deploy machine learning model to Hugging Face
- [ ] Create 5+ full-stack projects
- [ ] Contribute to open source
- [ ] Learn React Native for mobile development

---

## 🛠️ Tech Stack

### 💻 Frontend Development
<p align="center">
  <img src="https://skillicons.dev/icons?i=html,css,js,bootstrap,tailwind,react,vue" />
</p>

### ⚙️ Backend & Database
<p align="center">
  <img src="https://skillicons.dev/icons?i=php,mysql,laravel,postgresql,nodejs,express" />
</p>

### 🧰 Tools & Environment
<p align="center">
  <img src="https://skillicons.dev/icons?i=git,github,vscode,postman,linux,docker,figma" />
</p>

### 📊 Data Science & ML
<p align="center">
  <img src="https://skillicons.dev/icons?i=python" />
  <img src="https://img.shields.io/badge/Scikit--learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white" />
  <img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white" />
  <img src="https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white" />
  <img src="https://img.shields.io/badge/Gradio-FF6B6B?style=for-the-badge&logo=gradio&logoColor=white" />
</p>

---

## 🚀 Featured Projects

### 🏪 1. Cafe Management System
[![Cafe Management](https://img.shields.io/badge/Repository-Cafe_Management-4CAF50?style=for-the-badge&logo=github)](https://github.com/ifanfahrian/cafe-management)

**A complete cafe management system built with Laravel**

| Features | Technologies |
|----------|--------------|
| POS System | Laravel 10 |
| Inventory Management | MySQL |
| Employee Management | Bootstrap 5 |
| Sales Reports | JavaScript |
| Menu Management | Tailwind CSS |

```php
// Example: Cafe POS System
public function processOrder(Request $request) {
    $order = Order::create([
        'customer_id' => $request->customer_id,
        'total' => $request->total,
        'payment_method' => $request->payment_method
    ]);
    
    foreach($request->items as $item) {
        $order->items()->create($item);
        $this->updateStock($item['product_id'], $item['quantity']);
    }
    
    return response()->json(['order' => $order, 'message' => 'Order processed']);
}
