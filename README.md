import random
import string
from datetime import datetime

def generate_random_color():
    return "#{:06x}".format(random.randint(0, 0xFFFFFF))

def generate_typing_svg(text_lines):
    base_url = "https://readme-typing-svg.herokuapp.com"
    params = [
        f"font=Fira+Code",
        f"size=32",
        f"duration=2800",
        f"pause=2000",
        f"color=" + generate_random_color()[1:],
        f"center=true",
        f"vCenter=true",
        f"width=940",
    ]
    lines = "&lines=" + ";".join([line.replace(" ", "+") for line in text_lines])
    return f"{base_url}?{'&'.join(params)}{lines}"

def generate_github_stats(username):
    return (
        f'<img width="49%" src="https://github-readme-stats.vercel.app/api?username={username}&show_icons=true&theme=tokyonight&hide_border=true" />\n'
        f'<img width="49%" src="https://github-readme-streak-stats.herokuapp.com/?user={username}&theme=tokyonight&hide_border=true" />\n'
        f'<img src="https://github-readme-activity-graph.vercel.app/graph?username={username}&theme=react-dark&hide_border=true&bg_color=0D1117&line=00faff&point=ffffff" width="100%"/>'
    )

def generate_shields():
    shields = [
        f'![Working_With](https://img.shields.io/badge/Working_With-Web_Development-{generate_random_color()}?style=for-the-badge)',
        f'![Loves](https://img.shields.io/badge/Loves-JavaScript-{generate_random_color()}?style=for-the-badge)',
        f'![Prefers](https://img.shields.io/badge/Prefers-Dark_Mode-{generate_random_color()}?style=for-the-badge)',
    ]
    return "\n".join(shields)

def generate_tech_stack():
    tech_stack = {
        "Frontend": ["HTML5", "CSS3", "JavaScript", "React", "Vue.js", "TailwindCSS"],
        "Backend": ["Laravel", "PHP"],
        "Database": ["MySQL"],
        "Tools": ["Git", "Docker", "VS Code", "Figma"],
    }
    sections = []
    for category, technologies in tech_stack.items():
        badges = [
            f'![{tech}](https://img.shields.io/badge/{tech.replace(" ", "%20")}-{"%23" + generate_random_color()[1:]}.svg?style=for-the-badge)'
            for tech in technologies
        ]
        sections.append(f"### {category}\n{' '.join(badges)}")
    return "\n\n".join(sections)

def generate_featured_project(username, repo):
    return (
        f'[![{repo}](https://github-readme-stats.vercel.app/api/pin/?username={username}&repo={repo}&theme=tokyonight&hide_border=true)](https://github.com/{username}/{repo})'
    )

def generate_footer():
    current_year = datetime.now().year
    return (
        f'<div align="center">\n'
        f'  <img src="https://raw.githubusercontent.com/Trilokia/Trilokia/379277808c61ef204768a61bbc5d25bc7798ccf1/bottom_header.svg" />\n'
        f'  ![Made with ❤️ by Mahdi](https://img.shields.io/badge/Made%20with%20%E2%9D%A4%EF%B8%8F%20by-Mahdi-{generate_random_color()}?style=for-the-badge)\n'
        f'  <p>© {current_year} Mahdi - All Rights Reserved</p>\n'
        f'</div>'
    )

def generate_readme(username, repo_name):
    typing_text = [
        "🌟 Welcome to My Tech Universe!",
        "🚀 Full Stack Developer & Innovator",
        "✨ Building Amazing Web Experiences",
        "⚡ Let's Create Something Extraordinary Together!",
    ]

    readme_content = (
        '<div align="center">\n'
        f'  [![Typing SVG]({generate_typing_svg(typing_text)})]\n'
        '  <img src="https://raw.githubusercontent.com/platane/snk/output/github-contribution-grid-snake-dark.svg" width="100%">\n'
        '</div>\n\n'
        '<p align="center">\n'
        f'{generate_shields()}\n'
        '</p>\n\n'
        '# 🌟 Welcome to My Digital Garden!\n\n'
        '<img align="right" alt="GIF" src="https://raw.githubusercontent.com/rahul-jha98/rahul-jha98/main/techstack.gif" width="360px"/>\n\n'
        '## 🚀 Quick Facts About Me\n'
        '- 🎯 Crafting cutting-edge web experiences\n'
        '- 💡 Exploring futuristic web technologies\n'
        '- 🌐 Building scalable and robust applications\n'
        '- 🎮 Passionate gamer when not coding\n'
        '- 🎵 Coding with music boosts productivity\n'
        '- ⚡ Fun fact: I debug faster with coffee ☕\n\n'
        '## 🛠️ My Favorite Tech Stack\n'
        f'{generate_tech_stack()}\n\n'
        '## 📊 My GitHub Journey\n'
        f'<div align="center">\n{generate_github_stats(username)}</div>\n\n'
        '## 🌟 Featured Projects\n'
        f'<div align="center">{generate_featured_project(username, repo_name)}</div>\n\n'
        '## 🤝 Let\'s Connect and Build Together!\n'
        '<div align="center">\n'
        '  [![Portfolio](https://img.shields.io/badge/Portfolio-%23000000.svg?style=for-the-badge&logo=firefox&logoColor=#FF7139)](https://your-portfolio-url)\n'
        '  [![LinkedIn](https://img.shields.io/badge/LinkedIn-%230077B5.svg?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/your-linkedin)\n'
        '  [![Twitter](https://img.shields.io/badge/Twitter-%231DA1F2.svg?style=for-the-badge&logo=Twitter&logoColor=white)](https://twitter.com/your-twitter)\n'
        '  [![Discord](https://img.shields.io/badge/Discord-%237289DA.svg?style=for-the-badge&logo=discord&logoColor=white)](https://discordapp.com/users/your-discord)\n'
        '</div>\n\n'
        '## 📈 Visitor Count\n'
        '<div align="center">\n'
        '  ![Profile Views](https://komarev.com/ghpvc/?username={username}&color=blueviolet&style=for-the-badge)\n'
        '  [![GitHub Followers](https://img.shields.io/github/followers/{username}?style=for-the-badge&label=Followers)](https://github.com/{username})\n'
        '  [![GitHub Stars](https://img.shields.io/github/stars/{username}?style=for-the-badge&label=Stars)](https://github.com/{username})\n'
        '</div>\n\n'
        f'{generate_footer()}'
    )
    return readme_content

# Example Usage
if __name__ == "__main__":
    username = "Mahdi732"
    repo_name = "Luxury_V2"
    readme_output = generate_readme(username, repo_name)
    with open("README.md", "w", encoding="utf-8") as file:
        file.write(readme_output)
