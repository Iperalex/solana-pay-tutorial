# Take payments IRL with Solana Pay

    Code from https://www.pointer.gg/tutorials/solana-pay-irl-payments/

1   git clone -b start https://github.com/pointer-gg/solana-pay-tutorial

2   # install dependencies
    npm install
    # run the app locally
    npm run dev
  
3   npm install @solana/web3.js @solana/wallet-adapter-react @solana/wallet-adapter-react-ui @solana/wallet-adapter-base @solana/wallet-adapter-wallets
  
4   npm install @solana/pay@0.2.0

5   npm install react-circular-progressbar



Questo è un sistema di pagamento in solana che permette di collegare il wallet e comprare dei prodotti.

E' impostato in devnet, per lavorare in mainnet:
    pages\_app.tsx  riga 16: const network = WalletAdapterNetwork.Devnet; ---> const network = WalletAdapterNetwork.Mainnet.
    pages\api\makeTransaction.ts riga 48 const network = WalletAdapterNetwork.Mainnet
    
E' necessario agiungere la pubblic key del wallet che riceve i pagamenti:
    lib\addresses.ts  riga 4 export const shopAddress = new PublicKey('...') // immettere eindirizzo wallet al posto di ...
    
Per aggiungere o rimuovere e modificare il prezzo dei prodotti in vendita:
    lib\products.ts
    
Per aggiungere la possibilita di connettersi con altri wallet:
    pages\_app.tsx riga 27 new NomewalletWalletAdapter(),
    I wallet disponibili si trovano su node_modules\@solana\

