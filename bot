var Eris = require('eris');
var bot = new Eris(process.env.BOT_TOKEN);
var dEvent = [];
var eAndamento = false;
var dEtapa = 0;
var dStaffOrg = ['211962239433834498', '288021215535300608'];
bot.on("ready", () => {
    console.log("Ready!");
});

bot.on("messageCreate", (msg) => {
    var command = msg.content.toLowerCase();
    var args = msg.content.split(" ").slice(1);

    if (command == '!evento' && eAndamento == false) {
        bot.createMessage('300705416197701645', '``Evento iniciando! Use`` **!entrar** ``para participar!``')
        eAndamento = true;
    }
    if (command === "!entrar" && dEvent.length < 16 && dEvent.indexOf(msg.author.mention) == -1 && dEtapa == 0 && eAndamento == true) {
        msg.delete();
        dEvent.push(msg.author.mention);
        console.log(dEvent);
        setTimeout(function() {
            bot.createMessage('300705416197701645', msg.author.mention + " entrou!");
        }, 5000);
    }
    if (dEvent.length == 16 && dEtapa == 0) {
        dEtapa = 1;
        dEvent.push('noFlood');
        bot.createMessage('300705416197701645', {
            embed: {
                title: "Evento X",
                description: dEvent[0] + ' ⚔ ' + dEvent[1] + '\n' + dEvent[2] + ' ⚔ ' + dEvent[3] + '\n' + dEvent[4] + ' ⚔ ' + dEvent[5] + '\n' + dEvent[6] + ' ⚔ ' + dEvent[7] + '\n' + dEvent[8] + ' ⚔ ' + dEvent[9] + '\n' + dEvent[10] + ' ⚔ ' + dEvent[11] + '\n' + dEvent[12] + ' ⚔ ' + dEvent[13] + '\n' + dEvent[14] + ' ⚔ ' + dEvent[15],
                author: {
                    name: "Eliminations",
                    icon_url: 'https://cdn.discordapp.com/attachments/405426408597487618/445664611245621258/yggdrasil.png'
                },
                color: 0x00FF88,
                footer: { // Footer text
                    text: 'Yggdrasil eventos!'
                }
            }
        });
        console.log(dEvent);
        dEvent = [];
    }
    if (command.indexOf("!classificar") != -1 && args[0] != null && dEvent.indexOf(args[0]) == -1 && args[0].length == 21 && dEtapa == 1 && dStaffOrg.indexOf(msg.author.id) != -1) {
        msg.delete();
        dEvent.push(args[0]);
        console.log(dEvent);
    }
    if (dEvent.length == 8 && dEtapa == 1) {
        dEvent.push('noFlood');
        bot.createMessage('300705416197701645', {
            embed: {
                title: "Evento X",
                description: dEvent[0] + ' ⚔ ' + dEvent[1] + '\n' + dEvent[2] + ' ⚔ ' + dEvent[3] + '\n' + dEvent[4] + ' ⚔ ' + dEvent[5] + '\n' + dEvent[6] + ' ⚔ ' + dEvent[7],
                author: {
                    name: "Quarter finals",
                    icon_url: 'https://cdn.discordapp.com/attachments/405426408597487618/445664611245621258/yggdrasil.png'
                },
                color: 0x00FF88,
                footer: { // Footer text
                    text: 'Yggdrasil eventos!'
                }
            }
        });
        console.log(dEvent);
        dEvent = [];
        setTimeout(function() {
            dEtapa = 2;
        }, 100);
    }
    if (command.indexOf("!classificar") != -1 && args[0] != null && dEvent.indexOf(args[0]) == -1 && args[0].length == 21 && dEtapa == 2 && dStaffOrg.indexOf(msg.author.id) != -1) {
        msg.delete();
        dEvent.push(args[0]);
        console.log(dEvent);
    }
    if (dEvent.length == 4 && dEtapa == 2) {
        dEvent.push('noFlood');
        bot.createMessage('300705416197701645', {
            embed: {
                title: "Evento X",
                description: dEvent[0] + ' ⚔ ' + dEvent[1] + '\n' + dEvent[2] + ' ⚔ ' + dEvent[3],
                author: {
                    name: "Semi-final",
                    icon_url: 'https://cdn.discordapp.com/attachments/405426408597487618/445664611245621258/yggdrasil.png'
                },
                color: 0x00FF88,
                footer: { // Footer text
                    text: 'Yggdrasil eventos!'
                }
            }
        });
        console.log(dEvent);
        dEvent = [];
        setTimeout(function() {
            dEtapa = 3;
        }, 100);
    }
    if (command.indexOf("!classificar") != -1 && args[0] != null && dEvent.indexOf(args[0]) == -1 && args[0].length == 21 && dEtapa == 3 && dStaffOrg.indexOf(msg.author.id) != -1) {
        msg.delete();
        dEvent.push(args[0]);
        console.log(dEvent);
    }
    if (dEvent.length == 2 && dEtapa == 3) {
        dEvent.push('noFlood');
        bot.createMessage('300705416197701645', {
            embed: {
                title: "Evento X",
                description: dEvent[0] + ' ⚔ ' + dEvent[1],
                author: {
                    name: "Final",
                    icon_url: 'https://cdn.discordapp.com/attachments/405426408597487618/445664611245621258/yggdrasil.png'
                },
                color: 0x00FF88,
                footer: { // Footer text
                    text: 'Yggdrasil eventos!'
                }
            }
        });
        console.log(dEvent);
        dEvent = [];
        setTimeout(function() {
            dEtapa = 4;
        }, 100);
    }
    if (command.indexOf("!ganhador") !== -1 && args[0] != null && dEtapa == 4 && dStaffOrg.indexOf(msg.author.id) != -1) {
        msg.delete();
        bot.createMessage('300705416197701645', args[0] + ' **GANHOU!!**')
        setTimeout(function() {
            dEtapa = 0;
        }, 100);
        dEvent = [];
    }
});
bot.connect();
