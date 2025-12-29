# Solana TikTok Clone

A decentralized TikTok-like video sharing platform built on the Solana blockchain. Users can upload videos, like content, comment, and interact with videos through a Web3 interface powered by Solana wallets.

## 🚀 Features

- **Wallet Authentication**: Connect using Solana wallets (Phantom)
- **User Profiles**: Create and manage user profiles on-chain
- **Video Upload**: Upload videos with descriptions (stored on-chain)
- **Social Interactions**: 
  - Like videos (max 5 likes per video)
  - Comment on videos
  - Video approval/disapproval system
  - Content moderation (videos can be censored based on community feedback)
- **Decentralized Storage**: All user data, videos metadata, and interactions stored on Solana blockchain

## 🏗️ Architecture

This project consists of two main components:

### 1. Solana Program (`tiktok-clone/`)
- Built with **Anchor Framework** (Rust)
- Handles on-chain logic for:
  - User account creation
  - Video creation and management
  - Comments system
  - Like functionality
  - Content moderation

### 2. Frontend (`frontend/`)
- Built with **Next.js** and **React**
- Uses **Solana Wallet Adapter** for wallet connections
- Material-UI components for UI
- Tailwind CSS for styling

## 📋 Prerequisites

- **Node.js** (v14 or higher)
- **Rust** (latest stable version)
- **Solana CLI** (v1.10.0 or higher)
- **Anchor Framework** (v0.24.0 or higher)
- A Solana wallet (Phantom recommended)

## 🛠️ Installation

### 1. Clone the repository

```bash
git clone <your-repo-url>
cd tiktok-clone-youtube-main
```

### 2. Install Frontend Dependencies

```bash
cd frontend
npm install
```

### 3. Install Solana Program Dependencies

```bash
cd ../tiktok-clone
npm install
```

### 4. Build the Solana Program

```bash
anchor build
```

## 🚀 Getting Started

### Deploy the Solana Program

1. **Configure your Solana CLI** (if not already done):
```bash
solana config set --url devnet
```

2. **Get airdrop** (for devnet):
```bash
solana airdrop 2
```

3. **Deploy the program**:
```bash
anchor deploy
```

4. **Update Program ID** in `frontend/utils/const.js` with your deployed program ID

### Run the Frontend

1. **Navigate to frontend directory**:
```bash
cd frontend
```

2. **Set environment variables** (create `.env.local`):
```env
REACT_APP_CLUSTER=devnet
REACT_APP_SOLANA_API_URL=https://api.devnet.solana.com
```

3. **Start the development server**:
```bash
npm run dev
```

4. **Open your browser**:
Navigate to [http://localhost:3000](http://localhost:3000)

## 📁 Project Structure

```
.
├── frontend/                 # Next.js frontend application
│   ├── components/          # React components
│   │   ├── video.js        # Video player component
│   │   ├── mainview.js     # Main view component
│   │   ├── signup.js       # User signup component
│   │   ├── UploadModal.js  # Video upload modal
│   │   └── ...
│   ├── hooks/              # Custom React hooks
│   │   ├── useAccount.js   # Account management
│   │   └── useTiktok.js    # TikTok functionality
│   ├── context/            # React context providers
│   ├── utils/              # Utility functions
│   └── pages/              # Next.js pages
│
└── tiktok-clone/           # Solana program
    ├── programs/
    │   └── tiktok-clone/
    │       └── src/
    │           └── lib.rs  # Main program logic
    ├── Anchor.toml         # Anchor configuration
    └── tests/              # Program tests
```

## 🔑 Key Program Functions

### On-Chain Functions

- `create_state()` - Initialize the program state
- `create_user()` - Create a new user account
- `create_video()` - Upload a new video
- `create_comment()` - Add a comment to a video
- `like_video()` - Like a video (max 5 likes)
- `approve()` - Approve a video
- `disapprove()` - Disapprove a video (for moderation)

## 🌐 Supported Networks

- **Devnet** (default)
- **Testnet**
- **Localnet** (for local development)
- **Mainnet** (production)

Configure the network in `frontend/utils/const.js` or via environment variables.

## 🧪 Testing

### Test the Solana Program

```bash
cd tiktok-clone
anchor test
```

## 📝 Environment Variables

Create a `.env.local` file in the `frontend` directory:

```env
REACT_APP_CLUSTER=devnet
REACT_APP_SOLANA_API_URL=https://api.devnet.solana.com
```

## 🔧 Configuration

### Program ID

The program ID is configured in:
- `tiktok-clone/Anchor.toml`
- `frontend/utils/const.js`

Make sure both match your deployed program ID.

## 🎨 Tech Stack

### Frontend
- **Next.js** 12.1.5
- **React** 18.0.0
- **Solana Web3.js** 1.39.1
- **Anchor** 0.24.2
- **Material-UI** 4.12.4
- **Tailwind CSS** 3.0.24

### Backend
- **Anchor Framework** 0.23.0
- **Solana Web3.js** 1.40.0
- **Rust**

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📄 License

This project is open source and available under the MIT License.

## ⚠️ Important Notes

- This is a demonstration project for educational purposes
- Videos are stored off-chain (URLs are stored on-chain)
- Maximum 5 likes per video
- Content moderation system is implemented for community governance
- Ensure you have sufficient SOL in your wallet for transaction fees

## 🐛 Troubleshooting

### Common Issues

1. **Wallet connection fails**: Make sure Phantom wallet is installed and unlocked
2. **Transaction fails**: Check that you have sufficient SOL for transaction fees
3. **Program not found**: Verify the program ID matches your deployed program
4. **Build errors**: Ensure all dependencies are installed and Rust/Anchor are up to date

## 📚 Resources

- [Solana Documentation](https://docs.solana.com/)
- [Anchor Framework](https://www.anchor-lang.com/)
- [Solana Web3.js](https://solana-labs.github.io/solana-web3.js/)
- [Next.js Documentation](https://nextjs.org/docs)

## 👤 Author

Built as a Web3 demonstration project showcasing Solana blockchain integration.

---

**Note**: This project is for educational purposes. For production use, ensure proper security audits and optimizations.

