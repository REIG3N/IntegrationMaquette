<template>
  <head>
    <link rel="stylesheet" type="text/css" href="https://maxcdn.bootstrapcdn.com/font-awesome/4.3.0/css/font-awesome.min.css">
  </head>
  <nav>
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link>
  </nav>
  <router-view/>
  <body>

  <div class="menuBar">
    <div class="menuTitle">
      <img src="../src/assets/Logo.svg" alt="B">
    </div>
    <div class="dashboard">
        <navbarLink imgTitle="Dashboard" TextColor="black"/>
    </div>
    <div class="menuNav">
      <navbarLink imgTitle='Invoices' TextColor="white"/>
      <navbarLink imgTitle='Clients' TextColor="white"/>
      <navbarLink imgTitle='Products' TextColor="white"/>
      <navbarLink imgTitle='Messages' TextColor="white"/>
      <navbarLink imgTitle='Settings' TextColor="white"/>
      <navbarLink imgTitle='Help' TextColor="white"/>
    </div>
    <div class="logout1">
      <div class="logout">
        <navbarLink imgTitle='LogOut'/>
      </div>
    </div>

  </div>

  <div class="mainbar">
    <div class="mainHeader">
      <h1 class="mainHeaderTitle">Hi, Rogers </h1>
      <div class="mainHeaderSearchBar">
        <input type="text" class="mainHeaderInput" placeholder="Search">
      </div>
      <div class="UserBurger">
        <img src="../src/assets/user2.png" alt="zd">
      </div>

    </div>
    <div class="mainMenu">
      <div class="mainBalance">
        <SectionTitle SectionTitle="Total Balance" ></SectionTitle>
        <div class="mainBalanceSection">
          <div class="mainBalanceValue">
            <p>0.97894652</p>
            <img src="../src/assets/BitcoinTag.svg" alt="BitcoinTag">
          </div>
          <span class="mainBalanceMoney">$40,123.56</span>
        </div>

      </div>
      <div class="mainTabs">
        <SectionTitle SectionTitle=""></SectionTitle>
        <div class="mainTabBox">
          <input type="radio" name="tabs" id="tab1" checked />
          <label for="tab1">Portfolio</label>
          <input type="radio" name="tabs" id="tab2" />
          <label for="tab2">Funding</label>
          <input type="radio" name="tabs" id="tab3" />
          <label for="tab3">Assets</label>
          <input type="radio" name="tabs" id="tab4" />
          <label for="tab4">P2P</label>
        </div>
      </div>
    </div>
     <div class="mainGraph">
        <canvas id="graph"></canvas>

    </div>
    <div class="mainTransactions">
      <div class="mainTransactionsHead">
        <SectionTitle SectionTitle="Recent Transactions"></SectionTitle>

        <a href="#">See all coins</a>
      </div>
      <MainTransactions imgSrc="BitCoin2" CurrencyTitle="Bitcoin" CurrencyAcronym="BTC" CapValueColor="#1970D6" CurrencyCapValue="$40,243.70" ChangeValueColor="#4AD619" CurrencyChangeValue="+1,56" CurrencyCurve="Curve1"></MainTransactions>
      <MainTransactions imgSrc="Etherium2" CurrencyTitle="Etherum" CurrencyAcronym="ETH" CapValueColor="#6C1182" CurrencyCapValue="$40,243.70" ChangeValueColor="#D61919" CurrencyChangeValue="+1,56" CurrencyCurve="Curve2"></MainTransactions>
    </div>

    </div>
  <div class="sidebar">
    <div class="sideIcons">
      <SideIcons imgSrc="Notifications"></SideIcons>
      <SideIcons imgSrc="ProfilePicture"></SideIcons>
    </div>
    <div class="TransactionSection">
      <SectionTitle SectionTitle="Recent Transaction"></SectionTitle>
      <SideTransactions imgSrc="Classic" CurrencyTitle="Usdt" CurrencyStatus="Recieved" CurrencyValue="+$3,546" ValueColor="green" CurrencyDateTime="Today, 13:45 pm"></SideTransactions>
      <SideTransactions imgSrc="BinanceCoin" CurrencyTitle="BNB" CurrencyStatus="Buy" CurrencyValue="+ 0.7546" ValueColor="green" CurrencyDateTime="Today, 5:45 am"></SideTransactions>
      <SideTransactions imgSrc="LiteCoin" CurrencyTitle="Lite Coin" CurrencyStatus="Withdrawal" CurrencyValue="+ 0.7546" ValueColor="red" CurrencyDateTime="Today 7:55 am"></SideTransactions>
      <SideTransactions imgSrc="BitCoin" CurrencyTitle="Bitcoin" CurrencyStatus="Recieved" CurrencyValue="+ 2.7546" ValueColor="green" CurrencyDateTime="Today 8:55 am"></SideTransactions>
      <SideTransactions imgSrc="Etherium" CurrencyTitle="Etherum" CurrencyStatus="Recieved" CurrencyValue="+ 1.646" ValueColor="green" CurrencyDateTime="Today 10:02 am"></SideTransactions>
    </div>

    <div class="AssetsSection">
      <SectionTitle SectionTitle="Assets"></SectionTitle>
      <SideAsset imgSrc="BitCoin3" CurrencyTitle="Bitcoin" CurrencyValue="121,6450.45"
                 CurrencyAcronym="BTC"
                 BackgroundColor="linear-gradient(98.73deg, #611D8D 35.75%, #2F7EC1 73.26%)"
                 TextColor="white" ></SideAsset>
      <SideAsset imgSrc="Etherium3" CurrencyTitle="Etherum" CurrencyValue="143,850.45"
                 CurrencyAcronym="ETH"
                 BackgroundColor="linear-gradient(99.56deg, #FAFF00 35.82%, #29ABE2 64.75%, rgba(255, 255, 255, 0.7) 91.33%)"
                 TextColor="black" ></SideAsset>

    </div>
  </div>
  </body>
</template>
<script>
import navbarLink from "@/components/NavbarLink";
import SideIcons from "@/components/SideIcons";
import SectionTitle from "@/components/SectionTitle";
import SideTransactions from "@/components/SideTransactions";
import MainTransactions from "@/components/MainTransactions";
import SideAsset from "@/components/SideAsset";

import Chart from "chart.js";
export default {
  components: {navbarLink,SideIcons,SectionTitle,SideTransactions,MainTransactions,SideAsset},
  mounted() {
    let graph = document.getElementById('graph').getContext('2d');
    new Chart(graph, {
      type: 'line',
      data:{
        labels: ['5nov', '6nov', '7nov', '8nov', '9nov', '10nov', '11nov',
          '12nov', '13nov', '14nov', '15nov',],
        datasets:[
          {
            label: 'ETH',
            data: [700, 100, 700, 200, 50, 300, 600, 500, 400, 700,100,],
            borderColor:'blue',
          },
          {
            label: 'BTC',
            data: [ 300, 600, 500, 400, 600,200, 100, 700, 200, 400,100,],
            borderColor:'red',
          },
          {
            label: '???',
            data: [ 300, 600, 500, 400, 700 , 500, 400 , 400, 700 ,300, 600,],
            borderColor:'green',
          },
        ],
      },
      options: {
          legend: {
            display: false,
          }

      },
    })
  }
}

</script>
<style lang="scss">
nav {
  display: none;
}
*{
  padding: 0;
  margin:0;
  box-sizing: border-box;
  overflow-x: hidden;
}
.UserBurger{
  img{
    display: none;

  }
  @media (max-width: 1135px) {
    img {
      display: flex;
      width: 40px;
    }
  }
}

body{
  display: flex;
}
.menuBar{
  background-color: black;
  color: white;
  width: 21rem;
  height: auto;
  position: sticky;
  display: flex;
  flex-direction: column;
  padding-left: 3rem;
  padding-top: 1rem;
  @media (max-width: 890px) {
    display: none;
  }

  li{
    color: white;
    text-decoration:none;
    cursor:pointer;

  }
  .menuTitle{
    padding-bottom: 5.5rem;
    font-family: Poppins;
    font-weight: 800;
    font-weight: bolder;
    font-size: 30px;
    line-height: 57px;
    @media (max-width: 890px) {

    }
  }
  .menuNav{
    padding-top: 1.5rem;
    padding-bottom: 5rem;
    padding-left: 1rem;
  }
  @media (max-width: 890px) {
  }
  .dashboard {
    width: 32vh;
    height: 57px;
    gap: 17px;
    padding-left: 2rem;
    border-radius: 17px;
    background: linear-gradient(266.37deg, #FAFF00 -5.82%, #FAFF00 15.95%, #1970D6 41.2%, #6C1182 72.88%);

  }
  .dashboard1{
    margin-left: 1rem;
  }
  .logout{
    padding-left: 1.5rem;
    padding-bottom: 1rem;
    height: auto;
  }

}
.mainbar{
  background-color: #141414;
  color: white;
  width: 50rem;
  height: auto;
  display: flex;
  flex-direction: column;
  padding-left: 0.7rem;
  padding-right: 0.7rem;
  padding-top: 1em;

  .mainHeader{
    display: flex;
    justify-content: space-between;
    padding-right: 3.5rem;
    padding-top: 0.75em;

    .mainHeaderTitle{
      font-size: 27px;
      font-family: Poppins;
      font-weight: 500;
    }
    .mainHeaderSearchBar{
      .mainHeaderInput{
        width: 300px;
        height: 40px;
        padding-left: 40px;
        font-size: 18px;
        border-radius: 12px;
        background-image: url("../src/assets/Search.svg");
        background-repeat: no-repeat;
        background-size: 20px;
        background-position: 10px;
      }

    }
  }
  .mainMenu{
    display: flex;
  }
  .mainBalance{
    width: 35%;
    .mainBalanceSection{
      padding-left: 1rem;
      .mainBalanceMoney{
        opacity: 70%;
        font-family: Poppins;
        font-weight: 600;
        font-size: 14px;

      }
      .mainBalanceValue{
        display: flex;
        p{
          height: 42px;
          padding-right: 1rem;
          left: 20px;
          top: 65px;
          font-family: Poppins;
          font-size: 21px;
          font-weight: 700;
          line-height: 44px;
          letter-spacing: 0em;
          text-align: left;
        }
        img{
          padding-left: 0;
        }
      }
    }
  }
  .mainTabs{
    width: 65%;
    height: 100%;
    .mainTabBox{
      background-color: #292727;
      width: 390px;
      height: 50px;
      left: 343px;
      top: 44px;
      border-radius: 17px;
      display: flex;
      justify-content: center;
      padding-top: 0.5rem;
      margin-top: 1.5rem;
      input {
        display: none;
      }
      input + label{
        display: flex;
        justify-content: center;
        width: 90px;
        height: 33px;
        font-family: 'Poppins';
        font-style: normal;
        font-weight: 400;
        font-size: 14px;
        line-height: 33px;
      }
      input:checked + label{
        width: 95px;
        height: 34px;
        background: #0D0C0C;
        border-radius: 13px;
        display: flex;
        justify-content: center;

      }
    }
  }
  .mainGraph{
    padding-top: 2rem;
    background-color: #303541AB;
    border-radius: 30px;
    .mainGraphFrame{

    }
  }
  .mainTransactions{
    .mainTransactionsHead{
      display: flex;
      justify-content: space-between;
      a{
        padding-top: 2rem;
        padding-bottom: 0.75rem;
        padding-right: 1.5rem;

        text-decoration: none;
        font-family: 'Poppins';
        font-style: normal;
        font-weight: 700;
        font-size: 14px;
        line-height: 33px;
        text-align: center;

        color: rgba(255, 255, 255, 0.7);

      }
    }
  }




}

.sidebar{
  padding-top: 1em;
  background-color: black;
  color: white;
  width: 23.95rem;
  height: auto;
  display: flex;
  flex-direction: column;
  margin-right: 0px;
  @media (max-width: 1135px) {
display: none;
  }
  .sideIcons{
    display: flex;
    justify-content: space-between;
    padding: 1rem 1rem 2rem 2rem;
  }
}


</style>
