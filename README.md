# Exploradores DevOps – Demonstração do Trivy (DevSecOps)

## Introdução
O **Trivy** é um scanner de segurança focado em encontrar vulnerabilidades (CVEs) e falhas de configuração em alvos como imagens de contêineres, repositórios Git e arquivos de Infraestrutura como Código (IaC).

### Principais Recursos
* Detecção de vulnerabilidades em pacotes do SO e dependências de código.
* Varredura de configurações incorretas (Misconfigurations).
* Extremamente rápido e sem necessidade de configurações complexas de banco de dados.

---

## Instalação e Execução Local

### Passo 1: Instalação (Exemplo no Linux/Ubuntu ou WSL)
```bash
sudo apt-get install wget apt-transport-https gnupg lsb-release
wget -qO - [https://aquasecurity.github.io/trivy-repo/deb/public.key](https://aquasecurity.github.io/trivy-repo/deb/public.key) | gpg --dearmor | sudo tee /usr/share/keyrings/trivy.gpg > /dev/null
echo "deb [signed-by=/usr/share/keyrings/trivy.gpg] [https://aquasecurity.github.io/trivy-repo/deb](https://aquasecurity.github.io/trivy-repo/deb) $(lsb_release -sc) main" | sudo tee /etc/apt/sources.list.d/trivy.list
sudo apt-get update
sudo apt-get install trivy
