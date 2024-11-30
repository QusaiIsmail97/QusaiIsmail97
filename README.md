import os
from datetime import datetime

class ReadmeGenerator:
    def __init__(self, name, email):
        self.name = name
        self.email = email
        self.skills = []
        self.current_focus = []
        self.learning_interests = []

    def add_skill(self, skill):
        """Add a technical skill to the profile"""
        self.skills.append(skill)

    def set_current_focus(self, focus_areas):
        """Set current research or project focus"""
        self.current_focus = focus_areas

    def set_learning_interests(self, interests):
        """Set learning and exploration areas"""
        self.learning_interests = interests

    def generate_readme(self):
        """Generate a comprehensive README markdown file"""
        readme_content = f"""# 👋 {self.name}

## 🚀 Professional Profile

### 💡 Current Focus
{' • '.join(f'🔬 {focus}' for focus in self.current_focus)}

### 🌱 Learning & Exploring
{' • '.join(f'📖 {interest}' for interest in self.learning_interests)}

### 🛠️ Technical Skills
{' • '.join(f'💻 {skill}' for skill in self.skills)}

### 📫 Contact
- **Email:** {self.email}
- **Last Updated:** {datetime.now().strftime('%B %d, %Y')}

*Continuously learning and innovating* 🧠✨
"""
        return readme_content

    def save_readme(self, content, filename='README.md'):
        """Save the generated README to a file"""
        with open(filename, 'w') as f:
            f.write(content)
        print(f"README successfully generated: {filename}")

def main():
    # Example usage
    qusai_readme = ReadmeGenerator(
        name="Qusai Ismail", 
        email="qusaibanyismail@gmail.com"
    )

    # Set current focus
    qusai_readme.set_current_focus([
        "AI and Deep Learning Research",
        "Computer Vision Solutions",
        "NLP Model Development"
    ])

    # Set learning interests
    qusai_readme.set_learning_interests([
        "Advanced NLP Techniques",
        "Model Interpretability",
        "Cutting-edge Machine Learning Algorithms"
    ])

    # Add technical skills
    skills = [
        "Python", "TensorFlow", "PyTorch", 
        "Scikit-learn", "Natural Language Processing", 
        "Deep Learning", "Computer Vision"
    ]
    for skill in skills:
        qusai_readme.add_skill(skill)

    # Generate and save README
    readme_content = qusai_readme.generate_readme()
    qusai_readme.save_readme(readme_content)

if __name__ == "__main__":
    main()
