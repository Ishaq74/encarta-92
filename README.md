
# Encarta MindMaze 95 - Project Documentation

## 🎮 Game Controls

### Single Player / Classic Mode
- **Mouse**: Click to select answers.
- **Navigation**: Follow on-screen buttons.

### Contest Mode (Local Multiplayer)
This mode is designed for two players sharing the same keyboard (Hotseat/Split-keyboard).
**Native support for AZERTY keyboards is included (no Shift required).**

**Player 1 (Left Side)**
- **Join Lobby**: Press `1` or `&`
- **Answers**:
  - Option A: `1` or `&`
  - Option B: `2` or `é`
  - Option C: `3` or `"`
  - Option D: `4` or `'`

**Player 2 (Right Side)**
- **Join Lobby**: Press `0` or `à`
- **Answers**:
  - Option A: `7` or `è`
  - Option B: `8` or `_`
  - Option C: `9` or `ç`
  - Option D: `0` or `à`

---

## ⚠️ Current Limitations

As requested, here is a rigorous list of current technical limitations in this version:

1.  **Local Only**: The multiplayer mode is strictly **local** (same browser window). There is no WebSocket or WebRTC implementation for remote play over the internet.
2.  **Input Conflicts**: On some non-mechanical keyboards, pressing too many keys simultaneously (ghosting) might prevent an answer from registering if both players press at the exact same millisecond.
3.  **Static Database**: The question pool is currently static (located in `geminiService.ts`). It does not fetch live data from an external API, meaning questions will eventually repeat.
4.  **No Persistence**: Scores and progress are not saved to `localStorage` or a database. Refreshing the page resets the game.
5.  **Mobile Support**: Contest mode is extremely difficult on mobile devices due to the requirement of a physical keyboard for simultaneous inputs.

## 📝 Todo / Roadmap

- [ ] **Networked Multiplayer**: Implement PeerJS or Socket.io to allow players to join from different devices via a Room Code.
- [ ] **Dynamic Content**: Connect to the Gemini API properly to generate infinite questions based on user prompts.
- [ ] **Leaderboards**: Add a persistent high-score table.
- [ ] **Sound Effects**: Add retro 90s sound effects for correct/incorrect answers and lobby interactions.
- [ ] **Accessibility**: Improve contrast ratios and add screen reader support for the questions.
