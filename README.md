# Publicar site no HostGator (deploy via GitHub)

Passos rápidos para publicar este site no HostGator usando GitHub Actions (FTP):

1. Criar um repositório no GitHub e enviar todos os arquivos do projeto (branch `main`).
2. No cPanel do HostGator: crie uma conta FTP (cPanel > FTP Accounts).
   - Anote: host/servidor (pode ser seu domínio ou o host fornecido), usuário e senha.
   - Defina o diretório remoto como `public_html` (ou uma subpasta, se for subdomínio).
3. No GitHub do repositório: vá em `Settings > Secrets and variables > Actions` e adicione os secrets:
   - `FTP_HOST` = host/servidor (ex: ftpupload.net ou seu domínio)
   - `FTP_USERNAME` = usuário FTP
   - `FTP_PASSWORD` = senha FTP
   - `FTP_REMOTE_DIR` = diretório remoto (ex: `/public_html/`)
4. Após configurar os secrets, faça um push para a branch `main` — o workflow `.github/workflows/deploy.yml` será executado e fará o upload via FTP.

Alternativa manual (cPanel):
- Entre no cPanel > File Manager > public_html
- Faça upload do `site.zip` e extraia ou envie os arquivos diretamente.

Observações:
- Se preferir deploy automático por Git nativo, verifique se seu plano HostGator oferece integração Git no cPanel.
- Posso gerar e commitar automaticamente os arquivos e instruções Git localmente se quiser — diga se deseja que eu crie os commits e os comandos `git` prontos.
