<template>
  <div id="instructions">
    <p>In Enchanted Stones, you play as a sorcerer that controls a magic dueling rock. The goal of the game is to reduce your opponents life total to zero, while playing and countering spells that alter movement.</p>

    <h2>Turn Structure</h2>
<p>Each turn consists of three phases. During each phase you must declare an action: pass, move, attack, or play a spell. Every action you declare goes onto the "stack". Every time you declare an action, priority is passed to your opponent and they have the option to either play a spell or pass priority back to you. When priority is passed twice in a row the stack is resolved in a LIFO (last in, first out) fashion, similar to Magic: the Gathering (see below for more detail).</p>
    <h2>Spells</h2>
<p>Throughout the game, you are able to play up to eight spells. Once a spell is played, it is removed from your hand and you cannot play it again. The spells available to you are:</p>
<ul>
    <li>Confusion: Your opponent cannot play a spell during their next turn.</li>
    <li>Teleport: Move your opponent back to the square they occupied previously.</li>
    <li>Retreat: Move to the square you occupied previously.</li>
    <li>Stutter: You and your opponent move to the square you occipied previously.</li>
    <li>Time Warp: You and your opponent move back to the space you occupied on the beginning of your first turn.</li>
    <li>Counter attack: Attacks opponent back, but still take damage.</li>
    <li>Block: Negates an attack on the stack.</li>
    <li>Counter Spell: Negates a spell on the stack.</li>
  </ul>
    <h2>The Stack</h2>
    <p>The stack is resolved in a LIFO (Last In, First Out) fashion.<p>
    <p>This means that if a phase goes like so:</p>
    <ol>
    <li>You declare an attack on your opponent.</li>
    <li>Your opponent plays Counter Attack in response.</li>
    <li>You play Counter Spell in response to their Counter Attack.</li>
    </ol>
    <p>The result is this:</p>
    <ol>
    <li>Your Counter Spell resolves and negates your opponents Counter Attack (it's removed from the stack).</li>
    <li>Your attack resolves and your opponent loses one life.</li>
    </ol>
    <button @click="goHome">Home</button>
  </div>
</template>

<script>
export default {
  methods: {
    goHome: function() {
      this.$router.push("/");
    }
  }
};
</script>
