# Flash Loan Arbitrage Base

This repository contains a high-performance smart contract for executing **Flash Loans** via Aave V3. Flash loans allow users to borrow any amount of assets without collateral, provided the liquidity is returned to the protocol within the same transaction block.

## Workflow
1. **Request**: Contract calls Aave's `flashLoanSimple`.
2. **Execute**: The `executeOperation` function is triggered. This is where your custom logic (Arbitrage, Swap, Refinance) lives.
3. **Repay**: The contract automatically approves Aave to pull the original amount plus a small premium (0.05% - 0.09%).

## Technical Stack
- **Solidity 0.8.20**
- **Aave V3 Core**
- **OpenZeppelin Access Control**

## Security Warning
Flash loans are powerful tools. Ensure your logic handles slippage and price impact to avoid losing the "premium" fee if the trade is not profitable.

## License
MIT
