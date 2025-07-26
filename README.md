# Cursor Setup

A complete configuration setup for Cursor IDE with Model Context Protocol (MCP) servers and custom rules to optimize the development experience.

## 📋 Description

This project provides:

- **MCP Servers**: Configuration for Serena AI assistant and Postman API
- **Custom Prompts**: Detailed guidelines for AI development assistant
- **User Rules**: Rules and best practices for full-stack development

## 🚀 Installation

### System Requirements

- Cursor IDE
- Node.js (recommended version 18+)
- `uvx` package manager (for Serena MCP server)

### Install uvx (if not already installed)

```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

## 📁 Project Structure

```
cursor-setup/
├── mcp-server/
│   ├── serena.json      # Serena AI assistant configuration
│   └── postman.json     # Postman API configuration
├── prompts/
│   └── v0.md           # Detailed AI development guidelines
├── user-rules/
│   ├── best-practices.md        # Complete development rules
│   └── best-practices-short.md  # Summary development rules
└── README.md
```

## 📚 References

- [Cursor IDE Documentation](https://cursor.sh/docs)
- [Model Context Protocol](https://modelcontextprotocol.io/)
- [Serena AI Assistant](https://github.com/oraios/serena)
- [Postman API Documentation](https://learning.postman.com/docs/developer/intro-api/)

## 🤝 Contributing

1. Fork the project
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is distributed under the MIT License. See the `LICENSE` file for more details.

## 🆘 Support

If you encounter issues or have questions:

1. Check existing [Issues](../../issues)
2. Create a new issue with detailed description
3. Contact the maintainer via GitHub

---

**Note**: Make sure to update API keys and configuration according to your development environment.
