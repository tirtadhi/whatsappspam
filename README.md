const input = document.querySelectorAll("[contenteditable='true']")[1];

function dispatch(input, message) {
  var evt = new InputEvent('input', {
    bubbles: true,
  });
  input.innerHTML = message;
  input.dispatchEvent(evt);
  document.querySelector('span[data-icon="send"]').click();
}

function lyricsPrank(text) {
  text.split(' ').map((word) => dispatch(input, word));
}

function bombPrank(message, count) {
  let i = 0;
  while (i < count) {
    dispatch(input, message);
    i++;
  }
}

// example lyricsPrank
// let text = 'Uh, summa-lumma, dooma-lumma, you assumin Im a human What I gotta do to get it through to you Im superhuman? Innovative and Im made of rubber So that anything you say is ricochetin off of me And itll glue to you and Im devastating, more than ever demonstrating How to give a motherfuckin audience A feeling like its levitating Never fading, and I know the haters are forever waiting For the day that they can say I fell off, theyll be celebrating Cause I know the way to get em motivated I make elevating music'

// lyricsPrank(text); // will send each word of the text

// example bombPrank
// bombPrank('i love you', 100) // will send 'i love you' 100 times
