# Sazon-Night
index.html
style.css
game.js
/assets
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>OnlySazon Arcade</title>

  <script src="https://cdn.jsdelivr.net/npm/phaser@3/dist/phaser.js"></script>

  <style>
    body {
      margin: 0;
      background: black;
      overflow: hidden;
    }
  </style>
</head>
<body>

<script src="game.js"></script>

</body>
</html>
const config = {
    type: Phaser.AUTO,
    width: 400,
    height: 700,
    backgroundColor: '#000000',
    physics: {
        default: 'arcade',
        arcade: {
            gravity: { y: 800 }
        }
    },
    scene: {
        preload,
        create,
        update
    }
};

const game = new Phaser.Game(config);

let player;

function preload() {
    this.load.image('player', 'https://labs.phaser.io/assets/sprites/phaser-dude.png');
}

function create() {
    player = this.physics.add.sprite(200, 350, 'player');

    this.input.on('pointerdown', () => {
        player.setVelocityY(-300);
    });
}

function update() {

}