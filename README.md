// ==Script de Usuário==
// @name Khan resposta reveladora
// @versão 1.0
// @description Khan hack
// @autor IlyTobias (github@ilytobias)
// @match https://*.khanacademy.org/*
// @grant nenhum
// ==/Script do Usuário==

deixe n = JSON.parse;
JSON.parse = função (t) {
    deixe e = n(t);
    tentar {
        deixe t = JSON.parse(e.data.assessmentItem.item.itemData);
        t.question.content = t.question.content + "[[☃ explicação 2]]";
        console.log(t);
        t.question.widgets["explicação 2"] = {
            alinhamento: "padrão"
            , classificado: verdadeiro
            , opções: {
                explicação: t.hints[t.hints.length - 1].content
                , ocultarPrompt: "Ocultar"
                , showPrompt: "Responder"
                , estático: falso
                , widgets: t.hints[t.hints.length - 1].widgets
            }
            , estático: falso
            , tipo: "explicação"
            , versão: {
                principal: 0
                , menor: 0
            }
        };
        e.data.assessmentItem.item.itemData = JSON.stringify(t)
    } pegar (t) {}
    retornar e
}
