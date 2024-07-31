import random
import time
import os
import subprocess

user_input = input()
if user_input == "jan-ken":
    userjenken = input("Kies steen, papier of schaar: ").lower()
    botjklijst = ["steen", "papier", "schaar"]
    secretbotjanken = random.choice(botjklijst)
    print(f"Jouw keuze: {userjenken}")
    print(f"Bot keuze: {secretbotjanken}")
    
    if secretbotjanken == userjenken:
        print("Gelijkspel")
    if userjenken not in botjklijst:
        print("ongeldige optie")
    elif (secretbotjanken == "steen" and userjenken == "schaar") or \
         (secretbotjanken == "papier" and userjenken == "steen") or \
         (secretbotjanken == "schaar" and userjenken == "papier"):
        print("De bot wint")
   
    else:
        print("Jij wint")

if user_input == "raad nummer":
    moeilijknummer = int(input("wat is het hoogste dat het nummer kan zijn?")) 
    secnummer = random.randint(1,moeilijknummer)
    def radennummer():
        raadnummer = int(input("raad het nummer"))
        if raadnummer == secnummer:
            print("ja dat was het nummer")
            return
        if raadnummer > secnummer:
            print("te hoog")
            radennummer() 
        if raadnummer < secnummer:
            print("te laag")
            return radennummer()
    radennummer()
if user_input == "speed typing":
    alphabet_typen = "abcdefghijklmnopqrstuvwxyz"
    input("druk enter en typ zo snel mogelijk het alphabet")
    
    tijdspts = time.time()
    alphabettypuser = input("typ het alphabet\n")
    eindtypspstop = time.time()
    finaltime = eindtypspstop-tijdspts
    if alphabettypuser == alphabet_typen:
        print(f"je score is {finaltime} sec")
    if alphabettypuser != alphabet_typen:
        print(f"***ONGELDIGE SCORE***\n anders {finaltime} maar is ongeldig vanwege reden 1: niet het alphabet")
    if finaltime <1:
        print(f"***ONGELDIGIGE SCORE***\n anders {finaltime} maar is ongeldig vanwege reden 2: plakken of automatisch")
if user_input == "onthoud":
    onthoud = 1
    score = 0
    for _ in range (99999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999):
        onthoudgroter = onthoud*2
        onthoud += random.randint(1,onthoudgroter)

        lengte = 1
        print(onthoud)
        time.sleep(lengte)
        print("\n"*100)
        
        user_onthoud = int(input("typ het nummer dat je net zag"))
        if user_onthoud == onthoud:
            print("goed")
            score += 1
            lengte += 0.2
        else:
            print("fout")
            print(f"je score was: {score}\n het laatste getal was {onthoud}")
            break
if user_input == "casino1":
    rood_zwart = ["rood","zwart"]
    casinoeen = random.choice(rood_zwart)
    casinoinput = input("kies je rood of zwart")
    bling = 0
    def wincasino (bling):
        hoeveelheid = int(input("hoeveel wil je inzetten"))
        print("het is...")
        time.sleep(3)
        print(f"{casinoeen}")
        time.sleep(0.5)
        print("je hebt gewonnen")
        nieuwebling = hoeveelheid*1.9
        print(f"je hebt {nieuwebling} gewonnen")
        bling += nieuwebling
        print(f"je nieuwe saldo is {bling}")

    def verliescasino (bling):
        hoeveelheid = int(input("hoeveel wil je inzetten"))
        print("het is...")
        time.sleep(3)
        print(f"{casinoeen}")
        time.sleep(0.5)
        print("je hebt verloren")
        nieuwebling = hoeveelheid
        print(f"je hebt {nieuwebling} verloren")
        bling -= nieuwebling
        print(f"je nieuwe saldo is {bling}")

    if casinoeen == "rood" and casinoinput == "rood":
        wincasino (bling)
    if casinoeen == "zwart" and casinoinput == "rood":
        verliescasino (bling)
    if casinoeen == "rood" and casinoinput == "zwart":
        verliescasino (bling)
    if casinoeen == "zwart" and casinoinput == "zwart":
        wincasino (bling)  
if user_input == "even":
    hoeveeleven = int(input("wat is het hoogste dat het getal kan zijn"))
    hoeveelzeker = hoeveeleven/2
    getaleven = random.randint(1,hoeveelzeker)
    getaleven = getaleven*2
    print(f"je even getal is {getaleven}")
if user_input == "oneven":
    hoogteoneven = int(input("wat is het hoogste dat het getal kan zijn"))
    
    onevengetal = random.randint(1,hoogteoneven)
    if onevengetal%2 == 0:
        onevengetal-=1
        print(f"je oneven getal is {onevengetal}")
    else:
        print(f"je oneven getal is {onevengetal}")
    if user_input == "stop":
        print("Tot ziens!")
if user_input == "aftellen":
    tijd1 = int(input("Hoe veel seconden wil je aftellen? "))
    for i in range(tijd1, 0, -1):
        print(i)
        time.sleep(1)
if user_input == "loterij":
    spelers1 = int(input("Hoe veel spelers doen er mee? "))
    spanning1 = int(input("Van 1 tot 10, hoeveel spanning wil je? "))
    uitslag1 = random.randint(0, spelers1)
    if spanning1 < 6:
            print("De winnaar van de loterij is...")
            time.sleep(spanning1)
            print("Nummer........ ")
            time.sleep(0.7)
            print(uitslag1)

        
    else:
            print("De uitslag van de loterij wordt bekend gemaakt\n")
            denken1 = str(input("Maar eerst mogen jullie raden wie het was, het nummer is: "))
            if denken1 == str(uitslag1):
                print("Jullie zullen het over een paar seconden weten...")
                time.sleep(spanning1)
                print("Hadden jullie gelijk?")
                time.sleep(spanning1)
                print("Jullie hadden gelijk, de winnaar is\n" + str(uitslag1))
            else:
                print("Jullie zullen het over een paar seconden weten...")
                time.sleep(spanning1)
                print("Hadden jullie gelijk?")
                print("Jullie hadden niet gelijk, de winnaar is\n " + str(uitslag1))
if user_input == "k":
    print("| |/ / ")
    print("| ' / ")
    print("|  < ") 
    print("|_|\_\ \n")
if user_input == "verhaal":
    naamv = input("wat is de naam van de hoofdpersoon?\n de naam is___")
    leeftijdv = input("wat is de leeftijd van de hoofdpersoon in jaren?\n de persoon is ___ jaar oud")
    omgevingv = input("in welke omgeving speelde het verhaal zich af?\n het verhaal speelde zich af in de ___")
    weerv = input("wat voor een weer is het in het verhaal?\n het weer is ___")
    tweedepersoonv = input("hoe heet de tweede hoofpersoon?\n de tweede hoofdpersoon heet___")
    eerste_lijst = ["op een normale dag ging de hoofdpersoon van dit verhaal naar buiten, de hoofdpersoon heet "+naamv, "op een drukke dag liep de hoofdpersoon van dit verhaal naar huis van school, de hoofdpersoon heet "+naamv]
    tweede_lijst = [naamv+" is "+leeftijdv+" jaar oud", naamv+" is dus "+leeftijdv+" jaar oud"]
    derdelijst = ["het was "+weerv+" weer en het speelt zich allemaal af in de "+omgevingv, "het verhaal is in de "+omgevingv+" en het weer is "+weerv]
    vierdelijst = ["opeens kwam er een persoon genaamd "+tweedepersoonv, tweedepersoonv+" kwam uit het niets"]
    vijdelijst = ["lang niet gezien! zei "+tweedepersoonv, "dat is lang geleden! zei "+tweedepersoonv]
    willekeurig_ding_eerste = random.choice(eerste_lijst)
    willekeurig_ding_tweede = random.choice(tweede_lijst)
    willekeurigekeuzederdec = random.choice(derdelijst)
    willekeurigekeuzevierde = random.choice(vierdelijst)
    willekeurigekeuzevijfdelijst = random.choice(vijdelijst)
    print(f"{willekeurig_ding_eerste}")
    print(f" {willekeurig_ding_tweede}")
    print (f" {willekeurigekeuzederdec}")
    print("alles was saai, tot dat er iets gebeurde")
    print(f"{willekeurigekeuzevierde}")
    print(f"{willekeurigekeuzevijfdelijst}")
if user_input == "woord zoeker":
    def zoek_woord(text, woord):
            posities = []
            index = text.find(woord)
            while index != -1:
                posities.append(index)
                index = text.find(woord, index + 1)
            if posities:
                return posities
            else:
                return f"'{woord}' niet gevonden in de tekst."
            
    tekst = input("wat is de tekst?")
    woord = input("welk woord moet ik zoeken?")

    resultaat = zoek_woord(tekst, woord)
    print(resultaat)
if user_input == "letters":
    def vervang_letters(tekst):
            vertaalmap = str.maketrans({
                'a': 'ä',
                'b': 'B',
                'c':'©',
                'd':'ð',
                'e':'ë',
                'f':'|=',
                'g':'9',
                'h':'|-|',
                'i':'ï',
                'j':'J',
                'k':'|<',
                'l':'ø',
                'm':'µ',
                'n':'ñ',
                'o':'ó',
                'p':'ö',
                'q':'ä',
                'r':'®',
                's':'ß',
                't':'þ',
                'u':'ú',
                'v':'\/',
                'w':'\/\/',
                'x':'><',
                'y':'ü',
                'z':'æ',
                ' ':' ',
                })
            vertaalde_tekst = tekst.translate(vertaalmap)
            return vertaalde_tekst
    ingevoerde_tekst = input("Voer een tekst in: ")
    vertaalde_tekst = vervang_letters(ingevoerde_tekst)
    print("Vertaald: ", vertaalde_tekst)
if user_input == "suggestion":
        sugg1 = input("wat is je suggestion?")
        if "▓" in sugg1:
            print("je deed het onmogelijke!!!")
        else:
            print("manier laden...\n")
            time.sleep(0.1)
            onderwerp = input("wat is het onderwerp van de mail?\n")
            time.sleep(0.2)
            naammail = input("wat is je naam en achternaam?")
            time.sleep(0.3)
            print("\n\n\n\n\n\n")
            time.sleep(0.4)
            print("ivoheeg@gmail.com\n"+onderwerp+"\n Beste meneer Heeg.\n Ik heb een suggestie voor de pythonbot -gpt1.py-.\n mijn suggestie is "+sugg1+".\nHopelijk vind u het een goede suggestie en maakt u het.\n Met vriendelijke groet "+naammail+"\n")
if user_input == "nette mail":
        persoonmail = input("wat is de achternaam van de persoon?")
        zeggenmail = input("wat is de HELFT van de mail? ")
        anderhelftmail = input("wat is de laatste helft?")
        naammailzelf = input("wat ios je volledige naam?")
        herkenbaarmailzelf= input("wat is iets waar de persoon joui uit kan herkennen bijvoorbeeld\n klas\n school\n vak\n enzovoort?")
        geslachtmail = input("is de persoon een meneer of een mevrouw of iets anders")
        time.sleep(0.1)
        print("mail aan het maken")
        time.sleep(1.2)
        print("beste "+geslachtmail+" "+persoonmail+".\n\n"+zeggenmail+".\n "+anderhelftmail+".\n\n Met vriendelijke groeten "+naammailzelf+" "+herkenbaarmailzelf+".\n")
if user_input == "spammer":
        spamzin = input("welke zin wil je spammen?")
        hoeveelspam = int(input("hoeveel keer wil je dat hebben?"))
        print(spamzin*hoeveelspam)
if user_input == "info":
        print("maker: Ivo Heeg\n naam; gpt1.py\n maker, user: & C:/Users/ivohe/AppData/Local/Microsoft/WindowsApps/python3.7.exe c:/Users/ivohe/Downloads/gpt1.py\n studio: vs code/visual studio code\n makergmail: ivoheeg@gmail.com ")
if user_input == "zelf schrijven":
        verhaal = input("schrijf hier je verhaal:\n")
        tekst = verhaal
        os.system(f'echo {tekst} | clip')
if user_input == "vraag":
        vraagvraag1 = input("wat is je vraag?")
        lijst8ball = ["ja", "nee", "missschien","tuurlijk","tuurlijk niet","wie weet","wat boeit dat nou"]
        uitkomstvraag = random.choice(lijst8ball)
        print("sit was je vraag: "+ vraagvraag1+ " en dit is de uitkomst ")
        print(uitkomstvraag)
if user_input == "kies":

        veelheidkies = int(input("hoeveel keuzes?"))
        lijstmetkieskeuzes = []
        for i in range(veelheidkies):
            keuze = input(f"Voer keuze {i+1} in: ")
            lijstmetkieskeuzes.append(keuze)
        if lijstmetkieskeuzes:
            uitkomstkies = random.choice(lijstmetkieskeuzes)
            print("De uitkomst is...\n")
            time.sleep(1)
            print(uitkomstkies)
        else:
            print("Je hebt geen keuzes ingevoerd.")
if user_input == "typ snelheid":
        print ("typ het alfabet zo snel mogelijk")
        time.sleep(0.5)
        print("3")
        time.sleep(1)
        print("2")
        time.sleep(1)
        print("1")
        time.sleep(1)
        print("start!")
        start_time = time.time()
        alfabetsnelheid = input()
        end_time = time.time()
        if alfabetsnelheid == "abcdefghijklmnopqrstuvwxyz":
            print("goed gedaan")
            elapsed_time = end_time - start_time
            print(f": De verstreken tijd is {elapsed_time} seconden")
        else:
            print("jammer, dat was niet het alfabet!")
if user_input == ":)":
        print("0            0")
        print("      |       ")
        print("{            }")
        print("  {        }  ")
        print("    ______    ")
if user_input == "lopen":
        schoenen1 = ["👟: 100 km","👞: 80 km","👠: 10 km","🥿: 30 km","🥾: 90 km","👢: 20 km","👡: 40 km"]
        randomscheon1 = random.choice(schoenen1)
        print(randomscheon1)
if user_input == "letter weg":
        tekstmetletter = input("geef je tekst op\n")
        letterletterweg = input("welke letter moet weg?")
        if letterletterweg in tekstmetletter:
            print("dit was eerst de tekst: "+tekstmetletter)
            uitkomstletterwegv = tekstmetletter.replace(letterletterweg,"")
            print("dit is de nieuwe tekst\n"+uitkomstletterwegv)
if user_input == "denken":
        dnkmaar = input("waar wil je over denken\n ")
        lijstmetdenken = {"appel": " lekker eten",
                          "kaas":"ja, nog al kazig zeg",
                          "ivo":"de beste persoon op aarde al zeg ik het zelf",
                          "kat":"een dier dat miauw zegt",
                          "":"spatie..."}
        if dnkmaar in lijstmetdenken:
            print(lijstmetdenken[dnkmaar])
        else:
            print("is er helaas nog niet, probeer - suggestion - te typen om een mail op te stellen aan mij om het toe te voegen.")
if user_input == "cat piano":
        songcat = input("I am a cat playing piano.\n what song should I play?")
        print("sure I am playing "+songcat)
        time.sleep(1)
        listnotes = '♬','♭','♮','𝅘𝅥𝅮','♩','♪','𝄞'
        notenvoegsel = random.choice(listnotes)
        print(notenvoegsel+" ♩ ♪ ♫ ♬ ♭ ♮ ♯")
        time.sleep(0.8)
        happyornot = input("was it good? \n yes or no?")
        if happyornot == "yes":
            print("thnx")

        elif happyornot == "no":
            print(":(")

        else:
            print("you should say yes or no")
if user_input == "start de tijd":
        start_time = time.time()
        print (": druk enter om de tijd te stoppen")
        input()



        end_time = time.time()


        elapsed_time = end_time - start_time

        print(f": De verstreken tijd is {elapsed_time} seconden")
if user_input == "stickman generator":
        headstick = ["(+-+)","[*-*]","|^-^|"]
        bodystick = ["/ |/"," ( | )","([ ])"]
        voetensti = [" )(","   [  ] ","| | "]
        hoofdus = random.choice(headstick)
        bodyus = random.choice(bodystick)
        voeus = random.choice(voetensti)
        print("random stickman:\n")
        print(hoofdus)
        print(bodyus)
        print(voeus)
if user_input == "push ups pr":
        maxpu = int(input("wat was je oude pr?"))
        inkomenpu = maxpu/2
        russianinkpu = maxpu/10
        nieuwpr = maxpu+5
        print(f"we beginnen met {inkomenpu} push ups")
        print(f"nu doe je {russianinkpu} russian push ups")
        print(f"dit word je pr, nu doe je {nieuwpr} push ups")
if user_input == "work out":
        watwork = input("wat wil je doen? \n 1 armen\n2 benen\n3 buik\n4 schouders & rug")
        if watwork == "1":
            niveawo = int(input("hoeveel push ups kan je doen max"))
            pushnivwo = niveawo/2
            pushupswo = print(f"doe {pushnivwo} push ups")
            russian = niveawo/5
            print(f"doe {russian} russian push ups")
            print("neem een korte pauze van ongeveer 2 min en doe het nog een keer")
        if watwork == "2":
            gevordbenen = int(input("hoe lang kan je rennen in minuten?"))
            print(f" doe {gevordbenen} squads")
            loopsnel = gevordbenen/10
            gevordbenenkeertwee = gevordbenen*2
            print(f"probeer je tenen met gestrekte benen aant te raken voor {gevordbenenkeertwee} sec")
            print (f"doe een lunch met je ene been voor {gevordbenen} sec\n daarna met je andere been")
            print(f"doe een sprintje van {loopsnel} min ")
        if watwork == "3":
            print("doe 10 sit ups\n 10 sit upd met je benen omhoog\n 10 keer sit ups met 1 been omhoog en 10 keer met het andere been\n nog 10 sit ups\n 20 keer scharen\n 1 min in de lucht fietsen")

        if watwork == "4":
            print("doe 10 wide push ups\n 10 schouder-van-de-grond dingen\n 10 wijde schoulder push ups\n 20 sec rust\n 10 wijde schoulders push ups\n 10 schouder omhoog dingen")

        else:
            print("kies 1 van de keuzes")
if user_input == "woorden":
        woordennep = "nep"
if user_input == "rapper naam":
        naamrealrn = input("wat is je naam\n")
        voorrn = ["lil","rapper",""]
        achternaamrp = ["kleine", "de grote",""]
        uiitomstrn1 = random.choice(voorrn) 
        tweedeuitkomstrpn = random.choice(achternaamrp)
        print(f"{uiitomstrn1} {naamrealrn} {tweedeuitkomstrpn}")
if user_input == "cool":
        eentennullenc = ["0", "1"]
        resultaat = ""
        bitsveelhied = int(input("hoeveel bits?"))
        miljoenen2 = 2000000
        bpsr = bitsveelhied/miljoenen2
        print(f"het aantal seconden dat dit gaat duren is {bpsr} seconden")
        

        time.sleep(2)
        print("nu aan het berekenen")

        for _ in range(bitsveelhied):
            resultaat += random.choice(eentennullenc)

        print(resultaat)
if user_input == "cool snel":
        secbits = int(input("hoeveel sec?"))
        bits = " 100101001201010101010110010010100101010100010101110100101010010101010010101001010110101010111010101011110"
        honderdb = 30000
        tijdomteprinten = secbits/honderdb
        print(f"de tijd om het te printen is {tijdomteprinten}")
        time.sleep(2)
        print("print nu!")
        print (bits*secbits)
if user_input == "versie":
        bestandnaam = "kunkbot.py"
        versie = "1"
        print(f" {bestandnaam} {versie}\n je kan alles vinden in 'info' ")
if user_input == "dobbel":
        zijdendsn = int(input("hoeveel zijden heeft de dobbelsteen?"))
        dobbeluitkomst = random.randint(1,zijdendsn)
        timelseeprdmd = random.randint(1,3)
        time.sleep(timelseeprdmd)
        print(f"de uitkomst is :{dobbeluitkomst} ")
if user_input == "geluk":
        succesrateg = random.randint(1,10)
        if  succesrateg<7:
            print(f" je gelukt is maar {succesrateg}, maar dat zegt niks")
        else:
            print(f"lekker! je geluk is {succesrateg} vandaag moet je het doen het kan niet fout gaan")
if user_input == "cijfer password":
        passwordcf = int(input("hoeveel cijfers moet je password hebben?"))
        def passwordmake (passwordcf):
            for _ in range (passwordcf):
                rcf = random.randint(1,10)
                print(rcf, end="")
            if passwordcf <1:
                print("invalid number")
        print("ga ik doen ...")
        passwordmake(passwordcf) 
        print("\n")           
if user_input == "generate problem":
        probleeme = input("klik enter om een probleem te maken")
        print(probleeme/0) 
if user_input == "raad getal 1":
        grens = int(input(" tussen de 1 en hoeveel mag het getal zijn?"))
        secretgetal = random.randint(1,grens)
        def raad():
            gok = int(input(f"raad het getal tussen de 1 en {grens}"))
            if gok<secretgetal:
                print("te laag")
                return raad()
            if gok>secretgetal:
                print("te hoog")
                return raad ()
            if gok == secretgetal:
                print(f"ja {secretgetal} was het getal")
            else:
                print("ongeldige invoer?")
        
        raad()
if user_input == "zin afmaken":
        def zin_afmaken (zinam):
            print("ik doe het 2e deel van de zin")
            lijstmetvoegzinnen = ["omdat dat niet zo is",
                                  "omdat ik dat wil",
                                  "behalve gister",
                                  "maar niet op die manioer bedoeld",
                                  "zo heb ik dat gedaan",
                                  "en ik heb er nog steeds een goed gevoel over",
                                  "toch is het niet waar",
                                  "ik weet alleen niet waarom"]
            zinam = input("wat is hete eerste deel van de zin?")
            time.sleep(0.1)
            tweedezin = random.choice(lijstmetvoegzinnen)
            time.sleep(0.2)
            print(f"de zin is geworden:\n {zinam}, { tweedezin}")
            time.sleep(0.3)
        zin_afmaken (zinam="")
if user_input == "random weetje":
        random_weetjes = ["Wist je dat -89,2 °C de laagste buitentemperatuur ooit gemeten is?",
"Wist je dat 57,7 °C de hoogste buitentemperatuur ooit gemeten is?",
"Wist je dat alleen vrouwelijke muggen steken?",

"Wist je dat als je een goudvis in een donkere kamer opsluit, hij wit wordt?",

"Wist je dat als je je rechteroog sluit nooit over je rechterschouder kunt kijken?",

"Wist je dat Bill Gates in 2010 en 2008 niet de rijkste man is?",

"Wist je dat Coca-Cola oorspronkelijk groen was?",

"Wist je dat Coca-Cola vroeger cocaïne bevatte?",

"Wist je dat de meeste vrouwen het vaak kouder hebben dan mannen?",

"Wist je dat een varken fysiek niet in staat is om naar de lucht te kijken?",

"Wist je dat net zoals de vingerafdruk ook de tongafdruk bij ieder mens uniek is?",

"Wist je dat de aansteker al werd uitgevonden voor de lucifers?",

"Wist je dat de aarde ongeveer 6.000.000.000.000.000.000.000.000 kilogram weegt?",

"Wist je dat de gemiddelde chauffeur 15.250 keer toetert in zijn leven?",

"Wist je dat de hoogste golf ooit gemeten 64 meter boven de zeespiegel uitkwam?",

"Wist je dat de kolibrie achteruit kan vliegen?",

"Wist je dat de langste hartstilstand die iemand overleefde 4 uur duurde?",

"Wist je dat de Nijl de langste rivier ter wereld is?",

"Wist je dat de omtrek van de aarde wel 40.000 kilometer is?",

"Wist je dat de oudste boom ter wereld meer dan 4700 jaar oud is?",

"Wist je dat de rijkste man aller tijden John D. Rockefeller is?",

"Wist je dat de sterkste spier van het menselijk lichaam de tong is?",

"Wist je dat de strepen van een zebra voor verkoeling zorgen?",

"Wist je dat de totale lengte van je bloedvaten wel 100.000 kilometer is?",

"Wist je dat de zandtijgerhaai zijn broers en zussen opeet voordat hij geboren wordt?",

"Wist je dat de zon vlammen uitstoot van 20 tot 50 miljoen graden?",

"Wist je dat dieren ook humor hebben?",

"Wist je dat dolfijnen en walvissen met één oog open slapen?",

"Wist je dat Donald Duck strips verboden waren in Finland, omdat hij geen broek draagt?",

"Wist je dat een blinde geen hoogtevrees kan hebben?",

"Wist je dat een giraffe net zoveel nekwervels heeft als een mens?",

"Wist je dat een kakkerlak 9 dagen in leven kan blijven zonder zijn hoofd?",

"Wist je dat een kat meer dan 32 spieren in elk oor heeft?",

"Wist je dat een krokodil zijn tong niet kan uitsteken?",

"Wist je dat een meerval ruim 27.000 smaakpapillen heeft?",

"Wist je dat een mens gemiddeld 6000 scheten per jaar laat?",

"Wist je dat een slak drie jaar kan slapen?",

"Wist je dat een vlo 350 maal zijn lichaamslengte kan springen?",

"Wist je dat een vrouw gemiddeld 2 jaar van haar leven in een badkamer doorbrengt?",

"Wist je dat een worm maar liefst 10 harten heeft?",

"Wist je dat een zeester geen hersens heeft?",

"Wist je dat er 0,3 procent van de Sahara nodig is om Europa te voorzien van stroom?",

"Wist je dat er gemiddeld 100 mensen per jaar stikken in een balpen?",

"Wist je dat er niet één normaal Nederlands woord rijmt op het woord twaalf?",

"Wist je dat er op zijn minst 9 miljoen mensen jarig zijn op dezelfde dag als jij?",

"Wist je dat heet water sneller bevriest dan koud water?",

"Wist je dat het absolute nulpunt -273 graden is?",

"Wist je dat het bekende spel “Tetris” in 14 dagen is gemaakt?",

"Wist je dat het grootste zwembad ter wereld wel 1013 meter lang is?",

"Wist je dat het hart bij de mens in het midden van de borstkas zit en niet links?",

"Wist je dat het langste woord dat je kunt typen op de linkerhelft van je tobo verbeteraarsters is?",

"Wist je dat het langste woord dat je met de bovenste rij letters kunt maken topprioriteit is?",

"Wist je dat het oog van een struisvogel groter is dan zijn hersens?",

"Wist je dat het woord ‘van’ de meeste betekenissen heeft?",

"Wist je dat ijsberen linkspotig zijn?",

"Wist je dat je in de morgen langer bent dan in de avond?",

"Wist je dat je niest met een luchtsnelheid van ruim 150 kilometer per uur?",

"Wist je dat je niet je ellebogen kunt likken?",

"Wist je dat je voet even groot is als de binnenkant van je onderarm?",

"Wist je dat meer dan 50 procent van de wereldbevolking nog nooit heeft getelefoneerd?",

"Wist je dat mensen die jongleren grotere hersens hebben?",

"Wist je dat mensen met rood haar minder pijn voelen?",

"Wist je dat Mohammed de meest voorkomende naam is in de wereld?",

"Wist je dat olifanten de enige dieren zijn die niet kunnen springen?",

"Wist je dat olifanten elkaar vanaf 5 kilometer afstand kunnen ruiken?",

"Wist je dat ratten en paarden niet kunnen overgeven?",

"Wist je dat rechtshandigen gemiddeld 9 jaar langer leven dan linkshandigen?",

"Wist je dat slechts 20 procent van de Sahara uit zand bestaat?",

"Wist je dat te hard niezen kan resulteren in een gebroken rib?",

"Wist je dat verdrinking het grootste gevaar is in de woestijn?",

"Wist je dat vlinders met hun poten proeven?",

"Wist je dat vrijdag de 17e een ongeluksdag is in Italië?",

"Wist je dat vrouwen bijna twee keer zoveel met hun ogen knipperen als mannen?",

"De melk van de nijlpaard is licht roze.",

"De zeester is het enige dier dat zijn maag binnenste buiten kan draaien.",

"Een kwal heeft geen hersenen.",

"Winston Churchill is geboren in het damestoilet tijdens een dans.",

"Pinda’s zijn één van de ingrediënten van dynamiet.",

"Tweederde van alle aubergines is gegroeid in New Jersey.",

"De stad met de meeste Rolls Royce is Hong Kong.",

"Geen 1 woord in de Engelse taal rijmt op ‘month’ – ‘orange’ – ‘silver’ – ‘purple’.",

"Er zijn meer kippen dan mensen in de wereld.",

"Als er geen kleurstof in cola zat dan was het groen.",

"Turkse handdoeken komen uit Frankrijk en Indische inkt uit China.",

"Het woord ‘Yo-yo’ eigenlijk ‘come-come’ betekent.",

"Het langste woord dat met de linkerkant van het toetsenbord gespeld kan worden is stewardess.",

"Het enige 15 letterwoord dat gespeld kan worden zonder dat je letters herhaalt is ‘uncopyrightable’.",

"Het Hawaiiaanse alfabet heeft 12 letters.",

"Rubberen banden gaan langer mee als ze gekoeld zijn.",

"Sneeuwwitje van Disney is eigenlijk met blond haar ontworpen.",

"Mel Blanc (stem van Bugs Bunny) is allergisch voor wortels.",

"Bert en Ernie zijn genoemd naar Bert de agent en Ernie de taxichauffeur in Frank Capra’s ‘It’s a Wonderful Life’.",

"De gemiddelde vrouw eet 20 kg lipstick in haar leven.",

"Net zoals vingerafdrukken is de tong-afdruk identiek.",

"1 in de 2.5 van de huwelijken eindigt in een scheiding.",

"Als je gilt voor 8 jaren, 7 maanden en 6 dagen heb je genoeg geluidsenergie geproduceerd om een kopje koffie op te warmen.",

"Het oudste stukje kauwgom is 9000 jaar oud.",

"Marilyn Monroe had 6 tenen.",

"Een slak kan 3 jaar slapen.",

"Een zoen van 1 minuut verbrandt 26 calorieën."]
        print(random.choice(random_weetjes))
if user_input == "random object":
        random_objecten = ["kaas","wc","big mac","muts","lepel","1 schoen","vork","1 oortje","een tv zonder scherm"]
        print(f"je object is {random.choice(random_objecten)}")
if user_input == "nummer":
        tussenhoog = int(input("wat is het hoogste getal dat gekozen kan worden?"))
        
        print(f"je nummer is {random.randint(1,tussenhoog)}")
if user_input == "maak een nieuw tijdperk":
        tijdperknaam = input("wat is het voor een nieuw tijdperk?")
        print(f"oke welkom in het tijdperk van {tijdperknaam}")
        time.sleep(2)
        for _ in range (10000):
            print("___________________________________________________________________________________________________________________________________________________________________________________________________")
if user_input == "in welk tijdperk zijn we?":
        print(f"we zijn in het tijdperk van {tijdperknaam}")
if user_input == "rad":
        def rad10 ():
            keuze1 = input("wat is de volgende keuze?(1)")
            keuze2 = input("wat is de volgende keuze?(2)")
            keuze3 = input("wat is de volgende keuze?(3)")
            keuze4 = input("wat is de volgende keuze?(4)")
            keuze5 = input("wat is de volgende keuze?(5)")
            keuze6 = input("wat is de volgende keuze?(6)")
            keuze7 = input("wat is de volgende keuze?(7)")
            keuze8 = input("wat is de volgende keuze?(8)")
            keuze9 = input("wat is de volgende keuze?(9)")
            keuze10 = input("wat is de volgende keuze?(10)")
            keuzesrad = [keuze1,keuze2,keuze3,keuze4,keuze5,keuze6,keuze7,keuze8,keuze9,keuze10	]
            raduitkomst = random.choice(keuzesrad)
            for _ in range(10000):
                spanningrad = random.choice(keuzesrad)
                print("___"+spanningrad+"___")
                
            time.sleep(2.5)
            print("de keuze is....")
            
            print(raduitkomst)
        print("het rad heeft 10 keuzes")
        rad10()
if user_input == "tijd nu":
        huidige_tijd = time.strftime("%H:%M:%S")
        print("De huidige tijd is:", huidige_tijd)
if user_input == "geheime code":
        print("wow, je hebt niets ontdekt EN je moet nog 20 seconden wachten!\n hoe leuk is dat")      
        time.sleep(20)
if user_input == "goed wachtwoord":
        zelfstandignaamwoordgw= ["boom",
                                "kaas",
                                "fiets",
                                "deur",
                                "lamp",
                                "plafond"]
        leestekensgw = ["[]",
                        "%",
                        "!",
                        "@",
                        "#",
                        "$",
                        "%",
                        "^",
                        "&",
                        "*",
                        "()",
                        "_",
                        "-"]
        cijfersgw1 = random.randint(1,999)
        cijfersgw2 = random.randint(1,999)
        cijfersgw3 = random.randint(1,999)
        allecijfersgw = cijfersgw1,cijfersgw2,cijfersgw3
        alleleestekensgw = random.choice(leestekensgw)
        zelfstandignaamwoordgw1 = random.choice(zelfstandignaamwoordgw)
        zelfstandignaamwoordgw2 = random.choice(zelfstandignaamwoordgw)
        zelfstandignaamwoordgw3 = random.choice(zelfstandignaamwoordgw)
        allezesfstandignaamwoorden = zelfstandignaamwoordgw1,zelfstandignaamwoordgw2,zelfstandignaamwoordgw3
        print(f"je wachtwoord is:\n {allezesfstandignaamwoorden}{alleleestekensgw}{allecijfersgw}")
if user_input == "sterk password":
        caractersmp = "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ1234567890!@#$%^&*()_+|}{:|><?-=[];'\.,/"
        passwordlengtesp = int(input("hoe lang moet je sterke password zijn?"))
        huidige_passwordps = ""
        for _ in range (passwordlengtesp):
            huidige_passwordps += random.choice(caractersmp)
        print(f"je sterke password van {passwordlengtesp} tekens is:\n {huidige_passwordps}")
if user_input == "wifi wachtwoord":
     subprocess.Popen(['cmd', '/K', 'netsh wlan show profiles'], shell=True)
