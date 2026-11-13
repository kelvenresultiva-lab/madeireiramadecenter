# Contexto do projeto

Site institucional de madeireira, marca provisória Essência Madeiras. Continue a partir do código existente. Não refaça do zero e não converta para outro framework sem solicitação.

## Design aprovado

- Fundo branco, textos pretos e detalhes discretos em marrom madeira. Pouco verde.
- DM Sans é a fonte principal; preservar o uso de Playfair Display em destaque na hero.
- Preservar a tipografia atual de cada seção, inclusive localização.
- Cabeçalho branco, logo oficial em PNG, navegação e botão de orçamento. Altura 86px desktop e 74px celular. Menu em 15px/500 (14px até 1180, 13px até 1050, 17px no menu aberto do celular, itens com padding 7px — compactado a pedido em 13/11) — aumentado a pedido em 12/11.
- Fotos sem sombreado branco ou degradê branco. Preservar o contraste escuro discreto da hero.
- Cards de produtos alinhados, com fresta de 6px. Preservar comportamento de destaque e rolagem no celular.
- Sobre a empresa com duas imagens sobrepostas e texto ao lado.
- Introdução dos produtos sem caixa: “Encontre a madeira para o seu projeto.”
- Rodapé MARROM na cor da logo (#542a11, desde 13/11), logo clara `assets/logo-nova-madecenter-clara.png` (marrom→creme #f6ecdc, laranja #e0912f mantido), textos creme, destaques laranja. Seções, endereço, horário e telefone reais.
- Não restaurar as seções removidas: serviços, processo, faixa de categorias e CTA com deck “Da primeira peça ao último detalhe”.

## Seções e navegação

`#inicio`, `#sobre`, `#produtos`, `#por-que-escolher`, `#inspiracoes`, `#perguntas-frequentes`, `#localizacao` e rodapé.

## Funcionalidades

- Menu expansível no celular com aria-expanded e fechamento ao selecionar uma seção ou apertar Escape.
- Botões de orçamento abrem o mesmo diálogo.
- Cards abrem diálogo de produto e permitem preparar cotação da linha escolhida.
- Botões de orçamento (cabeçalho, hero, FAQ, rodapé, "cotação" das linhas/madeiras) abrem DIRETO o WhatsApp da empresa (wa.me/553132208948, fixo com WhatsApp Business confirmado em 13/11), SEM formulário — função openQuote(). Com madeira/linha, a mensagem cita o nome. O diálogo #contact-modal ficou no HTML mas não é mais aberto.
- FAQ usa details/summary.
- Rotas e mapa aguardam endereço real; não inventar localização funcional.
- Contatos do rodapé são fictícios e estão identificados como ilustrativos. Não atribuir um perfil ou número real sem dados do usuário.

## Trabalho no código

HTML, estilos e script estão em `index.html`. Há regras CSS acumuladas de ajustes anteriores; as regras finais prevalecem. Preserve o resultado visual ao reorganizar. Imagens locais estão em `assets/`; algumas fotos de versões anteriores foram preservadas por compatibilidade. Não remover arquivos sem checar referências no HTML e CSS.

Para conferir, rode `npm run dev` e verifique desktop e celular. Verifique navegação, menu, FAQ e modais ao alterar partes relacionadas. Não adicionar estatísticas, depoimentos, certificações ou promessas comerciais sem confirmação do usuário.

## Empresa real (desde 12/11/2026)

O site agora é da **Madeireira Nova Madecenter** (dados do perfil no Google Maps): R. Almerinda da Costa Ribeiro, 275 – Canadá, Contagem – MG, 32015-270 · telefone (31) 3220-8948 (fixo; WhatsApp não confirmado) · seg. a sex. 7h30–17h, sáb. e dom. fechado. Rotas (Google Maps/Waze) e mapa embutido estão ativos. Ainda sem e-mail, Instagram ou WhatsApp confirmados — não inventar. Fotos continuam ilustrativas.

Logo (12/11): símbolo de tronco cortado (casca escura, miolo cor de madeira, anéis irregulares e rachadura em cunha) em `assets/logo-madecenter.svg`, embutido no cabeçalho/rodapé e usado como favicon. Texto: "*Nova*" em Playfair itálico marrom + "Madecenter" DM Sans 600, linha de baixo "MADEIREIRA · CONTAGEM". Recusadas: anéis com "M" (parecia antena) e anéis concêntricos creme (parecia alvo).

Logo (12/11, atual): monograma **NM** (N e M dividem a haste do meio), traço creme num selo marrom arredondado com veios discretos — `assets/logo-nm.svg`, embutido no cabeçalho/rodapé e favicon. O tronco cortado (`assets/logo-madecenter.svg`) ficou guardado como alternativa.

Logo OFICIAL (12/11, enviada pelo cliente): "N" de vigas com ponta de tora + "NOVA" laranja / "MADECENTER" marrom. Original em `assets/logo-nova-madecenter-original.webp`; versão sem fundo `assets/logo-nova-madecenter.png` (1000x233) no cabeçalho (46px; 38px no celular) e rodapé (58px; 50px no celular); ícone da aba `assets/logo-nova-madecenter-icone.png` (só o "N"). Os SVGs logo-nm/logo-madecenter ficaram só como arquivo, não são mais usados.

Fotos (13/11): mosaico "A madeira transforma" (.corporate-photo) e foto do FAQ (.faq-portrait) agora COLORIDAS — filtro grayscale removido a pedido; não voltar ao preto e branco.

Seção #inspiracoes (13/11): MANTER O DESIGN DO MOSAICO (o usuário recusou trocar o layout por uma grade de cartões). Só as 5 fotos mudaram para madeiras: photo-1 eucalipto tratado, photo-2 cedrinho, photo-3 pinus, photo-4 angelim, photo-5 ipê (assets/madeiras/especies, créditos em IMAGENS.md; garapa.jpg baixada mas sem espaço). Espécies NÃO confirmadas pela empresa — descrições do diálogo trazem o aviso "consulte a equipe". Sem loading="lazy" nessas fotos.

Celular (13/11): selo "Da base ao acabamento" (.about-signature) escondido ≤600px. Letras do celular aumentadas ~2px (bloco "Letras maiores no celular" no fim do CSS): parágrafos 15px, textos de apoio 14px, etiquetas 11–13px. Não voltar aos 8–13px do template.

Celular (13/11): cartões de produto com painel compacto (descrição limitada a 2 linhas, título clamp 19–22px com text-wrap:balance). Títulos de seção no celular com text-wrap:balance; #sobre e #por-que-escolher em 26px; o <br> do título de #por-que-escolher some no celular (por isso há espaço antes dele no HTML).

Animações (13/11): dinâmica da Matos Stone, copiada do site da Perfect (Desktop/Essencia Madeiras): classe `js` no <html>, style#animacoes (hero em sequência, botão com pulso/brilho, [data-reveal] em cascata, fotos com cortina .rv-clip/.rv-cortina) e script antes de </body> com barra .progresso. Cor de destaque laranja da logo #e0912f. Revelação por verificação na rolagem + setInterval (IntersectionObserver não dispara com o painel oculto). Backup antes: scratchpad/index-antes-animacoes.html.

Hero legível (13/11, style#hero-legivel antes de style#animacoes): véu escuro radial atrás do texto (.hero:before), título peso 500 com sombra, frase 16–19px peso 400 branca com sombra, botão 15px/50px. Celular: título 38px, frase 16px, véu mais forte.

GitHub/Vercel (13/11): git próprio na pasta (aninhado no repo da home), remoto https://github.com/kelvenresultiva-lab/madeireiramadecenter (branch main). vercel.json (estático, sem build) + .vercelignore (server.mjs, CLAUDE.md, IMAGENS.md) iguais aos da Perfect. Prévia de WhatsApp: tags Open Graph apontando para https://madeireiramadecenter.vercel.app/assets/og-madecenter.jpg (1200x630, recorte da hero) — se o domínio final mudar (ex.: novamadecenter.com.br), trocar og:url/og:image.
