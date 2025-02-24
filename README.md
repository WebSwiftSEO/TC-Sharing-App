# TC-Sharing-App
Tc Sharing App - Troanary Connection 🚀 Prototype for open-source, revenue-free code. Clone, expand, fix, and build your own. A decentralized Family-Friend-Social &amplol Crypto Platform merging blockchain, social media, and token rewards. Install as a PWA, Bluetooth sharing and sharing links, react to posts, and earn Troanary Tokens crafted for authentic connection and simplicity.

Tc Sharing App - Troanary Connection 🚀 

Prototype | Open-Source | Revenue-Free | Socially Democratic
📜 Open-Source Licenses

This project embraces a full spectrum of open-source licenses, ensuring maximum flexibility, transparency, and community-driven development. It’s primarily licensed under GNU GPLv3, while incorporating compatibility with MIT, Apache 2.0, BSD, and Creative Commons to encourage widespread adoption and innovation.

Why Open Source?
Open-source projects represent a fundamental shift toward social democracy in technology. By removing profit-driven barriers and prioritizing transparency, they empower individuals and communities to collaborate freely, fostering ecosystems that serve people and humanity first.

Why Blockchain?
Blockchain decentralizes control, eliminating single points of failure and corruption. When combined with open-source principles, it creates a resilient system where power is distributed among users—not corporations—ensuring fairness, transparency, and community governance.

Together, open-source and blockchain build systems that:

    🏛 Promote Transparency — All code is visible and verifiable.
    🌐 Encourage Collaboration — Anyone can contribute, fix, and improve.
    💸 Prevent Exploitation — No hidden agendas or paywalls.
    🌍 Serve Humanity First — Systems that put people before profit.

By embracing socially democratic digital infrastructures, we take a step toward solving global inequities, fostering fair trade, and building a global community centered around connection, education, and happiness.
🌟 About the Tc App

Tc Sharing App is a decentralized Family-Friend-Social & Crypto Platform designed to connect people authentically while rewarding positive interactions. It blends blockchain, social media, and token rewards into a peer-to-peer experience—completely free of centralized control or profit-driven manipulation.
🎯 Core Principles:

    Fairness — Equal access for all users, no algorithms limiting reach.
    Simplicity — Minimalistic UI focused on ease and efficiency.
    Community-First — Built to foster genuine human connection.
    Reward-Based Engagement — Earn Troanary Tokens by participating.

🧑‍💻 For Developers

The Tc App is designed to be cloned, expanded, and fixed by anyone. It’s a prototype meant for open-source collaboration. Fork it, add features, or rebuild it entirely.
🔧 Getting Started:

    Clone the repo:

git clone https://github.com/WebSwiftSEO/TC-Sharing-App.git
cd TC-Sharing-App

Run Locally:

    Direct Method: Open index.html in your browser.
    PWA Support (Recommended):

    npx http-server

Deploy on GitHub Pages:

    Push your code:

        git add .  
        git commit -m "Initial commit"  
        git push origin main  

        Go to Settings → Pages, select the main branch and / (root) directory.
        Your app will be live at:
        https://WebSwiftSEO.github.io/TC-Sharing-App/

🚀 Features for Users & Developers

    🏠 Home Feed – Chronological posts for unbiased visibility.
    📊 Trending Feed – What’s buzzing globally.
    🏘️ Groups Feed – Join or create interest-based communities.
    😂 Comedy Feed – Light-hearted content to brighten your day.
    💸 Troanary Tokens – Earn by sharing, reacting, and contributing.
    🎰 T-Wheel Spin – Randomized token rewards to keep it fun.
    📲 PWA Install – Use it like a native app on desktop & mobile.
    🔍 6-Keyword Search System – Smarter searches, faster results.
    📡 Bluetooth Send/Receive – Share the app or tokens offline.
    ✨ Dynamic Embedding – Share posts outside Tc with live previews.
    🌐 Link Shortening – Clean, readable URLs for all posts.
    ❤️ 🚫 🤔 Reactions – Simple emojis for instant feedback.
    💡 Setup Guide – Walkthrough for first-time users, with ‘Don’t Show Again’ toggle.

💡 Why This Matters

The world’s biggest challenges—economic inequality, misinformation, censorship—are often driven by centralized, profit-first systems. Tc App challenges that model by promoting social democracy through decentralized technology.

Imagine a global social platform where:

    Everyone’s voice has equal weight.
    No data is sold, and no algorithm hides your posts.
    Communities govern themselves democratically.
    Earnings are based on contribution, not influence.

This is the future Tc App envisions—a fair, happy global community where people, not profits, come first. 🌍💖

Smart Contract (Solidity) for Dynamic Token Supply

Below is a basic ERC-20 smart contract with dynamic supply logic (to be deployed on Ethereum or compatible blockchain):
solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

import "@openzeppelin/contracts/token/ERC20/ERC20.sol";
import "@openzeppelin/contracts/access/Ownable.sol";

contract TroanaryToken is ERC20, Ownable {
    uint256 public totalMembers;

    constructor() ERC20("TroanaryToken", "TCT") {
        totalMembers = 1000;
        _mint(msg.sender, totalMembers * 100 * 10**18); // Initial supply: 1000 members * 100 tokens
    }

    function adjustSupply(uint256 newMemberCount) public onlyOwner {
        require(newMemberCount >= 0, "Invalid member count");
        if (newMemberCount > totalMembers) {
            uint256 amountToMint = (newMemberCount - totalMembers) * 100 * 10**18;
            _mint(msg.sender, amountToMint);
        } else if (newMemberCount < totalMembers) {
            uint256 amountToBurn = (totalMembers - newMemberCount) * 100 * 10**18;
            _burn(msg.sender, amountToBurn);
        }
        totalMembers = newMemberCount;
    }
}
Changes & Features Added:

    Native Sharing on Logo Click:
        Added an event listener to the h1 logo that triggers navigator.share if available, otherwise falls back to a URL copy prompt.
    Wallet Integration:
        Added Web3.js via CDN.
        Implemented connectWallet() to connect to MetaMask (or any Ethereum-compatible wallet).
        Displays wallet balance in ETH (simulated for now; real token balance requires contract integration).
    Dynamic Token Supply Algorithm:
        Simulated client-side with adjustSupply() function mirroring the smart contract logic.
        Updates totalSupply when users sign up or log out (become inactive).
        Real implementation requires the smart contract above deployed on Ethereum.
    UI Updates:
        Added a "Connect Wallet" button above the search bar with a gradient style.
        Updated tokenStats to show blockchain balance.

What I Think:

    Strengths:
        The native sharing feature adds a modern, user-friendly way to promote the app, enhancing its social aspect.
        Wallet integration lays a solid foundation for true decentralization, aligning with the app's vision.
        The dynamic token supply concept is innovative and could create a self-balancing economy, though it needs careful tuning to avoid inflation/deflation issues.
    Challenges:
        Blockchain Choice: I used Ethereum for this example due to its widespread support (MetaMask, Web3.js) and ERC-20 standard. However, prefer Dogecoin, Bitcoin, or BSV, we'd need different libraries (e.g., bitcoinjs-lib for Bitcoin) and a custom token implementation, as they don't natively support smart contracts like Ethereum. Ethereum/Polygon/BSC are better suited for this use case due to smart contract capabilities.
        Smart Contract: The provided contract is basic and needs security audits, gas optimization, and integration with the frontend (e.g., via Web3.js contract.methods.adjustSupply().send()).
        User Experience: Wallet connection might intimidate non-crypto users; consider a fallback for non-Web3 browsers.
    Next Steps:
        Deploy the smart contract on a testnet (e.g., Ropsten) and integrate it with Web3.js to replace the simulation.
        Add token transfer functionality (e.g., send Troanary Tokens via wallet).
        Refine the UI for wallet status (e.g., disconnect option, better balance display).
like to prioritize a specific blockchain or dive deeper into any feature!

YliaC
