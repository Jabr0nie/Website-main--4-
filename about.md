
<!DOCTYPE html>
<html lang="en">
	<head>
		<!-- Google tag (gtag.js) -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-VFJK8YLJ8C"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
    gtag('config', 'G-VFJK8YLJ8C');
</script>
		<link rel="icon" type="image/png" sizes="32x32" href="Images\DarkTealLogo.png">
		<meta charset="UTF-8" name="viewport"
			content="width=device-width, initial-scale=1.0">
		<title>NYKE</title>
		<link rel="stylesheet" href="https://fonts.googleapis.com/css?family=Sofia">
		<script language="javascript" type="text/javascript"
			src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
		<script language="javascript" type="text/javascript"
			src="web3.min.js"></script>
		<script language="javascript" type="text/javascript"
			src="getblock.config.js"></script>
		<script language="javascript" type="text/javascript"
			src="Connect.js"></script>
			<script src="https://cdn.ethers.io/lib/ethers-5.2.umd.min.js"
        type="application/javascript"></script>
		<script language="javascript" type="text/javascript" src="Abi.js"></script>
		<link href="Nyke.css" rel="stylesheet">
		<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">
		<link rel="stylesheet" href="/fonts/fontawesome-free-5.3.1-web/css/all.css">
	</head>
	<body class="body">
		<div class="root" id="root">
			<div style="clear: both;"></div>
			<div class="topnav" id="myTopnav">
				<div class="topNavRight">
					<button class="MetaMask" id="connectbutton" value="Connect Metamask">
						Connect Metamask</button>
					<div class="nykeInfo">
						<img id="ETCSwapLink" class="nNykeLogo" src="Images\NykeLogo.svg" width="20px"height="20px">
						<div class="nykePrice" id="nykePrice">$0.0000</div>
						<a href="https://swap.ethereumclassic.com/#/swap" class="ETClogowrapper">
							<img class="mobileMenuimg" src="Images\LinkIcon.png" width="15px"height="15px">
							</a>
					</div>
						</div>
					<div class="topNavLeft">
						<a href="https://nyke.finance/" class="logowrapper">
							<img id="logo" class="logo" src="Images\NykeTealBanner.svg" width="300px"
								height="80px">
							</a>
							<a href="https://nyke.finance/" class="mobilelogowrapper">
								<img id="logo" src="Images\DarkTealLogo.png" width="40px"
									height="40px">
								</a>
				</div>
			</div>
			<div class="rewardcontainer">
				<div class="rewardsinfo">Accrued Rewards</div>
				<div class="accruedRewards" id="accruedRewards">0.00 NYKE</div>
				<button class="claimRewards" id="claimRewards">Claim</button>
			</div>
			<div class="maincontent">
				<div style="clear: both;"></div>
				<div class="flex-container" id="flexcontainer">
					<div class = "UserDetails">
					<div class = "supplyshell">
						<div class="supplytextleft">
						<div class="UseBalanceText">Supplied Balance</div><div class="UserBalanceOutput" id="UserAssetBalance">$0.00</div>
						</div>
						<div class="supplytextright">
						<div class="UserMaxBorrowText">Net Base APR</div><div class="UserBorrowLimit" id="UserAPR"> 0%</div>
						</div>
					<div class="Supplied">
						<table class="UserSupplyTable">
							<tbody>
								<tr>
									<td></td>
									<td class="tdmobile" style="text-align: center;">Assets</td>
									<td>Supplied</td>
									<td>Base APR</td>
									<td>Reward APR</td>
									<td>Collateral</td>
								</tr>
								<tr>
									<td><img src="Images\ethereum-classic-etc-logo.png" alt="ETC Logo"
											width="25" height="25" style="display: inline-block;"></td>
							<td class="tdmobile">ETC</td>
							<td><div id="YourETCSupplied">-</div></td>
							<td><div id="ETCSupplyRateOutputSupply"><i class="fa fa-spinner fa-pulse"></i></div></td>
							<td><div id="ETCSupplyRateOutputSupply1"><i class="fa fa-spinner fa-pulse"></i></div></td>
							<td><label class="switch">
								<input type="checkbox" id="ETCCheckbox" onclick="CollateralStatus()">
								<span class="slider round"></span>
							  </label></td>		
						</tr>
						<tr>
							<td><img src="Images\usc-logo.png" alt="USC Logo" width="25" height="25"></td>
								<td class="tdmobile">USC</td>
								<td><div id="YourUSCSupplied">-</div></td>
								<td><div id="USCSupplyRateOutputSupply"><i class="fa fa-spinner fa-pulse"></i></div></td>
								<td><div id="USCSupplyRateOutputSupply1"><i class="fa fa-spinner fa-pulse"></i></div></td>
								<td><label class="switch">
									<input type="checkbox" id="USCCheckbox" onclick="CollateralStatusUSC()">
									<span class="slider round"></span>
								  </label></td></td>
						</tr>
					</tbody>
				</table>
				</div>
			</div>
			<div class="borrowshell">
				<div class="borrowtextleft">
				<div class="UserBalanceTextB">Borrowed Balance </div><div class="UserBalanceOutputB" id="UserLiabilityBalance">$0.00 </div>
				</div>
				<div class="borrowtextright">
				<div class="UserMaxBorrowText">Borrow Limit</div><div class="UserBorrowLimit" id="UserBorrowLimit"> 0%</div>
				</div>
				<div class="Borrowed">	
					<table class="borrowtable">
						<tbody>
							<tr class="userchildrow">
								<td></td>
								<td class="tdmobile" style="text-align: center;">Assets</td>
								<td>Borrowed</td>
								<td>Base APR</td>
								<td>Reward APR</td>
								
							</tr>
							<tr>
								<td><img src="Images\ethereum-classic-etc-logo.png" alt="ETC Logo"
										width="25" height="25" style="display: inline-block;"></td>
						<td class="tdmobile">ETC</td>
						<td><div id="UserETCBorrowed">-</div></td>
						<td><div id="ETCBorrowedRate1"><i class="fa fa-spinner fa-pulse"></i></div></td>
						<td><div id="ETCBorrowedRate2"><i class="fa fa-spinner fa-pulse"></i></div></td>
				
					</tr>
					<tr>
						<td><img src="Images\usc-logo.png" alt="USC Logo" width="25" height="25"></td>
							<td class="tdmobile">USC</td>
							<td><div id="USCBorrowedUser">-</div></td>
							<td><div id="USCBorrowRate1"><i class="fa fa-spinner fa-pulse"></i></div></td>
							<td><div id="USCBorrowRate2"><i class="fa fa-spinner fa-pulse"></i></div></td>

					</tr>
				</tbody>
			</table>
		</div>
	</div>
			</div>
				<div class="MarketDetails">


					<p class="MarketsText">Markets</p>

				<div class="Markets">
					<table id="table" class="Supply">
						<tbody>
							<tr>
								<td></td>
								<td class="tdmobile" style="text-align: center;">Assets</td>
								<td class=>Market Size</td>
								<td class=>Total Borrowed</td>
								<td class="tdmobile">Utilization Rate</td>
								<td class="tdmobile">Supply APR</td>
								<td class="tdmobile">Borrow APR</td>
							</tr>
							<tr>
								<td><img src="Images\ethereum-classic-etc-logo.png" alt="ETC Logo"
										width="30" height="30" style="display: inline-block;"></td>
						<td class="tdmobile">ETC</td>
						<td><div id="dataOutput"><i class="fa fa-spinner fa-pulse"></i></div></td>
						<td><div id="ETCBorrowed"><i class="fa fa-spinner fa-pulse"></i></div></td>
						<td class="tdmobile"><div id="ETCUtilization"><i class="fa fa-spinner fa-pulse"></i></div></td>
						<td class="tdmobile"><div id="rewards"><div id="ETCSupplyRateOutput"><i class="fa fa-spinner fa-pulse"></i></div></div>
							</td>
						<td class="tdmobile">
							<div id="rewards"><div id="ETCBorrowRateOutput"><i class="fa fa-spinner fa-pulse"></i></div></div>

							</td>
				

					</tr>
					<tr>
						<td><img src="Images\usc-logo.png" alt="USC Logo" width="30" height="30"></td>
							<td class="tdmobile">USC</td>
							<td><div id="USCSupply"><i class="fa fa-spinner fa-pulse"></i></div></td>
							<td><div id="USCBorrowed"><i class="fa fa-spinner fa-pulse"></i></div></td>
							<td class="tdmobile"><div id="USCUtilization"><i class="fa fa-spinner fa-pulse"></i></div></td>
							<td class="tdmobile">
								<div id="rewards"><div id="USCSupplyRateOutput"><i class="fa fa-spinner fa-pulse"></i></div></div>
								</td>
							<td class="tdmobile">
								<div id="rewards"><div id="USCBorrowRateOutput"><i class="fa fa-spinner fa-pulse"></i></div></div>

								</td>

					</tr>
				</tbody>
			</table>
		</div>
	</div>
		</div>

		<div id="modal-container" class="modal-container">

			<!-- Modal content -->
			<div id="modal-supply" class="modal-content">
				<img src="Images\ethereum-classic-etc-logo.png" class="image">
			<!--	<a class="modalclosebutton" onclick="closeModal()">
					<img class="modalclosebutton" src="Images\CloseTeal.svg" alt="close">
				</a> -->
				<div style="clear: both;"></div>
				<div class="modalnav">
					<a onclick="RepayModal()">Repay</a>
					<a onclick="BorrowModal()">Borrow</a>
					<a onclick="WithdrawlModal()">Withdraw</a>
					<a class="active" onclick="SupplyModal()">Supply</a>
				</div>
				<div style="clear: both;"></div>
				<div class="modalbody">
					<div class="WalletBalance">
						<div style="clear: both;"></div>
						<a>Wallet Balance: <div id="ETCBalance"
								style="display: inline-block; color:  #1eeadb;"><i class="fa fa-spinner fa-pulse"></i></div>
							ETC</a>
					</div>
					<div class="input">
						<input type="text" id="ETCDeposit" placeholder="Enter Amount Here...">
					</div>
					<div class="stats-container"><div class="Stats">Supply Rate</div><div class="Stats-Output" id="ETCSupplyRateModal"><i class="fa fa-spinner fa-pulse"></i></div></div>
					<div class="stats-container"><div class="Stats">Supply Balance</div><div class="Stats-Output" id="UserETCSupply2"><i class="fa fa-spinner fa-pulse"></i></div></div>
					<div class="stats-container"><div class="Stats">Collateral Factor</div><div class="Stats-Output"> 75%</div></div>
				</div>
				<div class="modalButton">
					<button id="ETCDepositButton">Supply</button>
				</div>
			</div>
			<div id="modal-withdrawl" class="modal-content">
				<img src="Images\ethereum-classic-etc-logo.png" class="image">
			
				<div class="modalnav">
					<a onclick="RepayModal()">Repay</a>
					<a onclick="BorrowModal()">Borrow</a>
					<a class="active" onclick="WithdrawlModal()">Withdraw</a>
					<a onclick="SupplyModal()">Supply</a>
				</div>
				<div style="clear: both;"></div>
				<div class="modalbody">
					<div class="WalletBalance">
						<div style="clear: both;"></div>
						<a>Supplied Balance: <div id="UserETCSupply"
								style="display: inline-block; color:  #1eeadb;"></div>
							</a>
					</div>
					<div class="input">
						<button type="SafeMax" id="SafeMax">MAX</button>
						<input type="value" id="ETCWithdrawl" placeholder="Enter Amount Here...">

					</div>
					<div class="stats-container"><div class="Stats">Supply Rate</div><div class="Stats-Output" id="ETCSupplyRateModal2"><i class="fa fa-spinner fa-pulse"></i></div></div>
					<div class="stats-container"><div class="Stats">Borrow Limit</div><div class="Stats-Output" id="BorrowLimit1"><i class="fa fa-spinner fa-pulse"></i></div></div>
					<div class="stats-container"><div class="Stats">Borrow Limit Used</div><div class="Stats-Output" id="BorrowLimitUsed1"><i class="fa fa-spinner fa-pulse"></i></div></div>
				</div>
				<div class="modalButton">
					<button id="ETCWithdrawlButton">Withdrawl</button>
				</div>
				
			</div>
			<div id="modal-borrow" class="modal-content">
				<img src="Images\ethereum-classic-etc-logo.png" class="image">
			
				<div class="modalnav">
					<a onclick="RepayModal()">Repay</a>
					<a class="active" onclick="BorrowModal()">Borrow</a>
					<a onclick="WithdrawlModal()">Withdraw</a>
					<a onclick="SupplyModal()">Supply</a>
				</div>
				<div style="clear: both;"></div>
				<div class="modalbody">
					<div class="WalletBalance">
						<div style="clear: both;"></div>
						<a>Borrow ETC</a>
					</div>
					<div class="input">
						<button type="SafeMax" id="SafeMaxBorrow">MAX</button>
						<input type="value" id="ETCBorrow" placeholder="Enter Amount Here...">
					</div>
					<div class="stats-container"><div class="Stats">Borrow Rate</div><div class="Stats-Output" id="ETCBorrowRateModal"><i class="fa fa-spinner fa-pulse"></i></div></div>
					<div class="stats-container"><div class="Stats">Borrow Balance</div><div class="Stats-Output" id="ETCBorrowBalanceModal"><i class="fa fa-spinner fa-pulse"></i></div></div>
					<div class="stats-container"><div class="Stats">Borrow Limit</div><div class="Stats-Output" id="BorrowLimit2"><i class="fa fa-spinner fa-pulse"></i></div></div>
					<div class="stats-container"><div class="Stats">Borrow Limit Used</div><div class="Stats-Output" id="BorrowLimitUsed2"> 75%</div></div>
				</div>
				<div class="modalButton">
					<button id="ETCBorrowButton">Borrow</button>
				</div>
			</div>
			
			<div id="modal-repay" class="modal-content">
				<img src="Images\ethereum-classic-etc-logo.png" class="image">
				
				<div class="modalnav">
					<a class="active" onclick="RepayModal()">Repay</a>
					<a onclick="BorrowModal()">Borrow</a>
					<a onclick="WithdrawlModal()">Withdraw</a>
					<a onclick="SupplyModal()">Supply</a>
				</div>
				<div style="clear: both;"></div>
				<div class="modalbody">
					<div class="WalletBalance">
						<div style="clear: both;"></div><a>Borrowed Balance: <div id="ETCBorrowBalance"
						style="display: inline-block; color:  #1eeadb;"><i class="fa fa-spinner fa-pulse"></i></div> ETC</a>
						
					</div>
					<div class="input">
						<button type="SafeMax" id="SafeMaxRepay">MAX</button>
						<input type="value" id="ETCRepay" placeholder="Enter Amount Here...">
					</div>
					<div class="stats-container"><div class="Stats">Borrow Rate</div><div class="Stats-Output" id="ETCBorrowRateModal1"><i class="fa fa-spinner fa-pulse"></i></div></div>
					<div class="stats-container"><div class="Stats">Borrow Limit</div><div class="Stats-Output" id="BorrowLimit3"><i class="fa fa-spinner fa-pulse"></i></div></div>
					<div class="stats-container"><div class="Stats">Borrow Limit Used</div><div class="Stats-Output" id="BorrowLimitUsed3"><i class="fa fa-spinner fa-pulse"></i></div></div>
				</div>
				<div class="modalButton">
					<button id="ETCRepayButton">Repay</button>
				</div>
			</div>
<!-- USC Modal content -->
<div id="USCmodal-supply" class="modal-content">
	<img src="Images\usc-logo.png" class="image">
	
	<div style="clear: both;"></div>
	<div class="modalnav">
		<a onclick="USCRepayModal()">Repay</a>
		<a onclick="USCBorrowModal()">Borrow</a>
		<a onclick="USCWithdrawlModal()">Withdraw</a>
		<a class="active" onclick="USCSupplyModal()">Supply</a>
	</div>
	<div style="clear: both;"></div>
	<div class="modalbody">
		<div class="WalletBalance">
			<div style="clear: both;"></div>
			<a>Wallet Balance: <div id="USCBalanceWallet"
					style="display: inline-block; color:  #1eeadb;"><i class="fa fa-spinner fa-pulse"></i></div>
				USC</a>
		</div>
		<div class="input">
			<input type="text" id="USCDeposit" placeholder="Enter Amount Here...">
		</div>
		<div class="stats-container"><div class="Stats">Supply Rate</div><div class="Stats-Output" id="USCSupplyRateModal1"><i class="fa fa-spinner fa-pulse"></i></div></div>
		<div class="stats-container"><div class="Stats">Supply Balance</div><div class="Stats-Output" id="UserUSCSupply2"><i class="fa fa-spinner fa-pulse"></i></div></div>
		<div class="stats-container"><div class="Stats">Collateral Factor</div><div class="Stats-Output"> 75%</div></div>
	</div>
	<div class="modalButton">
		<button class="ApproveButtons" id="USCApproveButton" style="display:inline-block; width: 43%; margin-left: 0%; margin-right: 2%;">
			<div class="Approve1">1</div>
			<div class="ApproveText">Approve</div></button>
		<button class="ApproveButtons" id="USCDepositButton" style="display:inline-block; width: 43%; margin-left: 2%; margin-right: 0%;">
			<div class="Approve1">2</div>
			<div class="ApproveText">Supply</div></button>
		</button>	
	</div>
</div>
<div id="USCmodal-withdrawl" class="modal-content">
	
	<img src="Images\usc-logo.png" class="image">
	<div class="modalnav">
		<a onclick="USCRepayModal()">Repay</a>
		<a onclick="USCBorrowModal()">Borrow</a>
		<a class="active" onclick="USCWithdrawlModal()">Withdraw</a>
		<a onclick="USCSupplyModal()">Supply</a>
	</div>
	<div style="clear: both;"></div>
	<div class="modalbody">
		<div class="WalletBalance">
			<div style="clear: both;"></div>
			<a>Supplied Balance: <div id="UserUSCSupply"
					style="display: inline-block; color:  #1eeadb;"><i class="fa fa-spinner fa-pulse"></i></div>
				USC</a>
		</div>
		<div class="input">
			<button type="SafeMax" id="SafeMaxUSC">MAX</button>
			<input type="value" id="USCWithdrawl" placeholder="Enter Amount Here...">
		</div>
		<div class="stats-container"><div class="Stats">Supply Rate</div><div class="Stats-Output" id="USCSupplyRateModal2"><i class="fa fa-spinner fa-pulse"></i></div></div>
		<div class="stats-container"><div class="Stats">Borrow Limit</div><div class="Stats-Output" id="BorrowLimit4"><i class="fa fa-spinner fa-pulse"></i></div></div>
		<div class="stats-container"><div class="Stats">Borrow Limit Used</div><div class="Stats-Output" id="BorrowLimitUsed4"><i class="fa fa-spinner fa-pulse"></i></div></div>
	</div>
	<div class="modalButton">
		<button id="USCWithdrawlButton">Withdrawl</button>
	</div>
	
</div>
<div id="USCmodal-borrow" class="modal-content">
	<img src="Images\usc-logo.png" class="image">
		
	<div class="modalnav">
		<a onclick="USCRepayModal()">Repay</a>
		<a class="active" onclick="USCBorrowModal()">Borrow</a>
		<a onclick="USCWithdrawlModal()">Withdraw</a>
		<a onclick="USCSupplyModal()">Supply</a>
	</div>
	<div style="clear: both;"></div>
	<div class="modalbody">
		<div class="WalletBalance">
			<div style="clear: both;"></div>
			<a>Borrow USC</a>
		</div>
		<div class="input">
			<button type="SafeMax" id="SafeMaxBorrowUSC">MAX</button>
			<input type="value" id="USCBorrow" placeholder="Enter Amount Here...">
		</div>
		<div class="stats-container"><div class="Stats">Borrow Rate</div><div class="Stats-Output" id="USCBorrowRateModal"><i class="fa fa-spinner fa-pulse"></i></div></div>
		<div class="stats-container"><div class="Stats">Borrow Balance</div><div class="Stats-Output" id="USCBorrowBalanceModal"><i class="fa fa-spinner fa-pulse"></i></div></div>
		<div class="stats-container"><div class="Stats">Borrow Limit</div><div class="Stats-Output" id="BorrowLimit5"><i class="fa fa-spinner fa-pulse"></i></div></div>
		<div class="stats-container"><div class="Stats">Borrow Limit Used</div><div class="Stats-Output" id="BorrowLimitUsed5"> 75%</div></div>
	</div>
	<div class="modalButton">
		<button id="USCBorrowButton">Borrow</button>
	</div>
</div>

<div id="USCmodal-repay" class="modal-content">
	<img src="Images\usc-logo.png" class="image">
	
	<div class="modalnav">
		<a class="active" onclick="USCRepayModal()">Repay</a>
		<a onclick="USCBorrowModal()">Borrow</a>
		<a onclick="USCWithdrawlModal()">Withdraw</a>
		<a onclick="USCSupplyModal()">Supply</a>
	</div>
	<div style="clear: both;"></div>
	<div class="modalbody">
		<div class="WalletBalance">
			<div style="clear: both;"></div><a>Borrowed Balance: <div id="USCBorrowBalance"
			style="display: inline-block; color:  #1eeadb;"><i class="fa fa-spinner fa-pulse"></i></div> USC</a>
			
		</div>
		<div class="input">
			<button type="SafeMax" id="SafeMaxRepayUSC">MAX</button>
			<input type="value" id="USCRepay" placeholder="Enter Amount Here...">
		</div>
		<div class="stats-container"><div class="Stats">Borrow Rate</div><div class="Stats-Output" id="USCBorrowRateModal2"><i class="fa fa-spinner fa-pulse"></i></div></div>
		<div class="stats-container"><div class="Stats">Borrow Limit</div><div class="Stats-Output" id="BorrowLimit6"><i class="fa fa-spinner fa-pulse"></i></div></div>
		<div class="stats-container"><div class="Stats">Borrow Limit Used</div><div class="Stats-Output" id="BorrowLimitUsed6"><i class="fa fa-spinner fa-pulse"></i></div></div>
	</div>
	<div class="modalButton">
			<button class="ApproveButtons" id="USCApproveRepayButton" style="display:inline-block; width: 43%; margin-left: 0%; margin-right: 2%;">
				<div class="Approve1">1</div>
				<div class="ApproveText">Approve</div></button>
			<button class="ApproveButtons" id="USCRepayButton" style="display:inline-block; width: 43%; margin-left: 2%; margin-right: 0%;">
				<div class="Approve1">2</div>
				<div class="ApproveText">Repay</div></button>
	</div>
</div>

		</div>



</div>

		</div>
			</div>
			<div class="footer">
				<a href="https://discord.gg/AjBX4KFMKN" class="footerwrapper">
				<img class="footericon" src="Images\DiscordTeal.svg" width="30px"
					height="30px">
				</a>
				<a href="https://x.com/NykeFinance" class="footerwrapper">
					<img class="footericon" src="Images\twitterlogo.svg" width="30px"
						height="30px">
					</a>
				<a href="https://github.com/Jabr0nie" class="footerwrapper">
					<img class="footericon" src="Images\GithubTeal.svg" width="30px"
						height="30px">
					</a>
					<a href="https://nyke.gitbook.io/nyke-finance/" class="footerwrapper">
						<img class="footericon" src="Images\GitbookTeal.svg" width="30px"
							height="30px">
						</a>
			</div>


		<script language="javascript" type="text/javascript"
			src="script.js"></script>

	</body>
</html>
