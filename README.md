# -solana-dao-toolkit-
// lib.rs  
#[program]  
pub mod sdt_voting {  
    use super::*;  
    pub fn create_proposal(ctx: Context<CreateProposal>, title: String) -> Result<()> {  
        let proposal = &mut ctx.accounts.proposal;  
        proposal.title = title;  
        proposal.votes = 0;  
        Ok(())  
    }  
    pub fn vote(ctx: Context<Vote>) -> Result<()> {  
        let proposal = &mut ctx.accounts.proposal;  
        proposal.votes += 1;  
        Ok(())  
    }  
}  
// VoteButton.js  
const VoteButton = ({ proposalId }) => {  
  const { publicKey, signTransaction } = useWallet();  
  const handleVote = async () => {  
    await program.methods.vote().accounts({ proposal: proposalId }).rpc();  
  };  
  return <button onClick={handleVote}>Vote Now</button>;  
};  
# Install Git first: https://git-scm.com/downloads
git clone https://github.com/Gabriel22243/solana-dao-toolkit.git
cd solana-dao-toolkit
git add .
git commit -m "Initial MVP commit: voting module"
git push
# Solana DAO Toolkit (SDT) MVP  
A minimal voting module for DAOs on Solana.  
## Features  
- Connect wallet (Phantom)  
- Create/vote on proposals  
## Links  
  
- 
