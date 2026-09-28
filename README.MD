# Clean.sh - Script de Limpeza Profunda para Linux

Este repositório contém o script `Clean.sh`, uma ferramenta de automação desenvolvida em Bash para realizar uma limpeza abrangente e liberar espaço em sistemas Linux. 

## O que este script faz?

O script executa uma série de comandos otimizados para remover arquivos temporários e caches desnecessários do sistema. Abaixo estão as principais ações realizadas:

*   **Gerenciamento de Pacotes:** Remove dependências e pacotes órfãos não utilizados, e limpa o cache de pacotes locais do `apt` (`autoremove`, `autoclean`, `clean`).
*   **Limpeza de Logs:** Reduz e exclui logs antigos do sistema (`journalctl`), logs do `apt` e relatórios de sessão (`.xsession-errors`).
*   **Privacidade e Histórico:** Apaga o histórico de comandos digitados no terminal (`.bash_history`).
*   **Arquivos Temporários e Lixeira:** Esvazia os diretórios de arquivos temporários (`/tmp`, `/var/tmp`), relatórios de travamentos (`/var/crash/`), arquivos de spool, e a lixeira do usuário.
*   **Otimização de Navegadores:** Limpa os caches de navegadores como Google Chrome, Mozilla e Min.
*   **Manutenção Específica:**
    *   Apaga miniaturas de imagens em cache (`thumbnails`) e o cache de fontes do sistema.
    *   Remove arquivos temporários e de cache gerados pelo emulador Wine.
    *   Limpa o cache de pacotes do Python via `pip3`.
*   **Rede:** Esvazia e reseta o cache de resolução de DNS do sistema (`systemd-resolved`).
*   **Repositórios:** Ao final, o script adiciona novamente os repositórios `multiverse` e `universe`.

## Como usar

1.  Clone este repositório ou baixe o arquivo `Clean.sh`.
2.  Abra o terminal na pasta onde o arquivo está localizado.
3.  Dê permissão de execução ao script com o comando:
    ```bash
    chmod +x Clean.sh
    ```
4.  Execute o script como administrador (necessário para a maioria das operações de limpeza):
    ```bash
    sudo ./Clean.sh
    ```

## Avisos Importantes

*   **Exclusão de Histórico:** Este script apaga o histórico do Bash (`~/.bash_history*`) e esvazia a lixeira automaticamente. Se você costuma buscar comandos antigos no terminal ou guardar arquivos na lixeira como backup temporário, revise o código antes de rodar.
*   **Uso de Caches:** Limpar caches de navegadores e thumbnails pode fazer com que páginas da web e pastas com imagens demorem um pouco mais para carregar na primeira vez em que forem abertas após a limpeza.
