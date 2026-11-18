# TaskBoard — versão estática para GitHub Pages

## O que é esta versão

Esta versão funciona sem backend, sem Supabase e sem banco de dados remoto. O próprio navegador armazena os dados usando `localStorage`.

- Arquivo principal: `index.html`.
- Dependências de interface: Bootstrap 5, Bootstrap Icons, jQuery e JavaScript nativo carregados por CDN.
- Persistência: `localStorage` do navegador.
- Autenticação local demonstrativa: usuários, empresas, perfis e convites são mantidos no armazenamento local.

## Primeiro acesso

- Usuário: `admin`
- Senha: `admin`

Entre e clique em **Empresas** para cadastrar uma empresa. O código inicial é mostrado após o cadastro. O primeiro usuário que criar uma conta usando esse código será o administrador da empresa. O administrador da empresa poderá gerar códigos individuais em **Convidar usuário**.

Cada cartão pode ser criado, editado, excluído, movido entre colunas e atribuído a usuários da mesma empresa no armazenamento local.

## Publicar no GitHub Pages

1. Crie um repositório no GitHub.
2. Coloque `index.html` na raiz do repositório.
3. No repositório, abra **Settings → Pages**.
4. Em **Build and deployment**, escolha **Deploy from a branch**.
5. Selecione a branch `main` e a pasta `/ (root)` e salve.
6. Acesse o endereço publicado pelo GitHub Pages.

Não há etapa de build.

## Limitações importantes

Esta versão é adequada para demonstração, uso individual ou protótipo local. Ela **não é um sistema multiusuário seguro**:

- Os dados ficam no navegador e no dispositivo em que foram cadastrados.
- Outro computador ou navegador terá um banco local independente; não existe sincronização entre funcionários.
- `admin/admin` é uma credencial pública de demonstração.
- Como o HTML e o JavaScript são públicos, usuários com conhecimento técnico podem inspecionar ou alterar os dados locais e contornar as telas de login.
- O hash de senha no navegador não transforma a autenticação em autenticação segura de servidor.
- Não armazene dados pessoais sensíveis, segredos ou informações empresariais confidenciais nesta versão.

Para transferir um quadro entre dispositivos, use **Exportar JSON** no quadro de origem e **Importar JSON** no dispositivo de destino. Esse processo transfere apenas o quadro e seus cartões; contas, empresas e senhas permanecem no navegador original.

## Onde os dados ficam

A chave de armazenamento é `taskboard.local.database.v1`. Para apagar tudo neste navegador, use as ferramentas de desenvolvimento do navegador ou limpe os dados do site. Essa ação remove empresas, usuários, convites e quadros salvos neste navegador.
