const playerArray = [];

// Player making function
const playerCreator = (name, money) => {
    const name = {
        chips: money * 100,
        hand: [],
        chipsBet: 0,
        chipsRaised: 0,
        bet(betSize) {
            this.chipsRaised = chipsBet - playerArray[playerArray.indexOf(name) - 1].chipsBet;
            if (playerArray[playerArray.indexOf(name) - 1].chipsRaised >= this.chipsRaised) {
                this.chipsBet = betSize;
            } else {
                this.chipsRaised = 0;
                return 'Raise size must be greater than or equal to preceeding raise.';
            }
        },
        fold() {
            this.hand.pop();
            this.hand.pop();
        },
        call() {
            this.chipsBet = playerArray[playerArray.indexOf(name) - 1].chipsBet;
        }
    };
    playerArray.push(name);
}

// Making a fresh deck
const suite = [A, K, Q, J, 10, 9, 8, 7, 6, 5, 4, 3, 2];
const hearts = suite.map(x => x+h);
const diamonds = suite.map(x => x+d);
const spades = suite.map(x => x+s);
const clubs = suite.map(x => x+c);
let newDeck = hearts + diamonds + spades + clubs;

// creating a shuffled deck function
const shuffledDeck = [];
function shuffle() {
    shuffledDeck.length = 0;
    for (let i = 0; i < 52; i++) {
        let Card = newDeck[Math.floor(Math.random() * newDeck.length)];
        shuffledDeck.push(Card);
        newDeck.splice(newDeck.indexOf(Card));
    }
    newDeck = hearts + diamonds + spades + clubs;
};

// Dealing function
function dealCards() {
    for (let i = 0; i < playerArray.length; i++) {
        playerArray[i].hand.push(shuffledDeck.shift());
        playerArray[i].hand.push(shuffledDeck.shift());
    }
};

