## ProPayChain - payment portal

ProPayChain is a web platform that revolutionizes the process of sourcing Fintech professionals and paying them securely with Ethereum. Leveraging a private Ethereum blockchain technology, Ganache, the platform offers a seamless interface for robust and secure financial transactions.

The ProPayChain consists of two primary Python scripts:

* `fintech_finder.py` - This is the user side of the application, designed with Streamlit, providing an intuitive and easy to use web interface for clients to engage Fintech professionals.

* `crypto_wallet.py` - Underlying the platform, this script manages Ethereum transactions, ensuring secure and swift transfers of funds from client to professional.

ProPayChain, through its integration of financial and blockchain technologies, underscores a new era of Fintech solutions, making the hiring and payment processes more efficient, secure, and transparent.

### Table of Contents
- [Technologies](#technologies)
- [Installation](#installation)
- [Instructions](#instructions)
- [Contributors](#contributors)
- [License](#license)

### Technologies

This application is built with the following technologies:

* [Python 3.7.13](https://www.python.org/downloads/release/python-385/): The primary programming language used for backend integration.

* [Streamlit](https://streamlit.io/):A Python library used to create the web interface of the application. It allows Python developers to craft user-friendly web applications without the need for front-end web languages.

* [Ganache](https://trufflesuite.com/ganache/): A personal blockchain used for Ethereum development you can use to deploy contracts, develop applications, and run tests.

* [Ethereum](https://ethereum.org/en/): An open-source blockchain platform with smart contract functionality. This application uses Ethereum to execute transactions.

* [dotenv](https://pypi.org/project/python-dotenv/): A Python library to separate sensitive credentials (like your Ganache mnemonic seed phrase) from scripts, keeping secret data safe.


### Installation

Please follow the steps outlined below to set up ProPayChain on your local machine:

1. Clone the Repository: Clone this repository onto your local machine.

2. Navigate to the Project Folder: Use your terminal to navigate to the cloned repository's location on your computer.

3. Install Python (if necessary): Make sure you have Python installed on your system. You can check this by typing `python --version` into your terminal . If Python isn't already installed, download it from the official [Python](https://www.python.org/downloads/release/python-385/) website.

4. Install Streamlit: Streamlit is the open-source app framework on which our web interface is built. To install it, use the following pip command in your terminal:
```
pip install streamlit
```
5. Install the Necessary Python Packages: ProPayChain requires several Python packages to work correctly. Install these by running the following command in your terminal:
```
pip install -r requirements.txt
```
6. Add Your Ganache Mnemonic Seed Phrase: You'll need a Ganache account to interact with your personal Ethereum blockchain. Input your Ganache mnemonic seed phrase into the .env file. If you don't have a Ganache account yet, download and install Ganache[here](https://trufflesuite.com/ganache/).

7. Launch the Application: Start the Streamlit application with the following command in your terminal:
```
streamlit run fintech_finder.py
```
### Instructions

Navigating the ProPayChain payment portal is a straightforward process. Here's a comprehensive breakdown of the steps:

1. Import Ethereum Transaction Functions: The heart of our application is the Ethereum transaction functions that allow seamless financial transactions. Upon launching the ProPayChain interface, it integrates a set of functions from the `crypto_wallet.py` script. This integration facilitates automation of crucial tasks such as generating a digital wallet, accessing Ethereum account balances, and signing and sending transactions via Ganache, a personal Ethereum blockchain. For demonstration purposes, we have assigned an account (the one with Index 0) to the user of the application, who will be sending the payments. The accounts with Indexes 1, 2, 3, and 4 have been assigned to the fintech professionals, who will be receiving payments.

* Example: Let's say you, the user, are using the account with Index 0, and you choose a fintech professional assigned to Index 1. The application will facilitate a transaction from your account (Index 0) to the professional's account (Index 1).

![Transaction Functions](gif/transaction_functions.gif)


2. Initiate and Execute a Payment Transaction: This is where you get to interact directly with the application. Once you've chosen a fintech professional from our database and entered the number of hours for which you require their service, the application calculates the total wage in Ethereum. This calculation is based on the professional's hourly rate multiplied by the number of hours you input. After the wage is calculated, you can authorise the payment transaction with a click of the "Send Transaction" button. This action triggers the `send_transaction` function, which in turn executes the transaction on the Ethereum blockchain.

* Example: Suppose you choose a professional whose hourly rate is 0.05 Ether and you need their service for 10 hours. The application will calculate the total wage as 0.5 Ether (0.05 * 10). Upon clicking the "Send Transaction" button, 0.5 Ether will be deducted from your account (Index 0) and credited to the professional's account (e.g., Index 1).

![Payment Transactions](gif/payment_transactions.gif)

3. Review Transaction on Ganache: After initiating the transaction, you can review the details. Once the transaction is executed, you'll receive a transaction hash code. Navigate to the Transactions section of Ganache with this hash to view the transaction details. You can validate the transaction's success by checking the Ganache records. After the transaction, the balances of your account and the professional's account will be updated on Ganache, reflecting the payment transaction. Additionally, the transaction details will be added to the blockchain.

* Example: Following the transaction in the previous example, you will see that 0.5 Ether has been deducted from your account balance (Index 0) and added to the professional's account balance (Index 1). In Ganache's Transactions section, you will see the transaction details including the From address (Index 0), the To address (Index 1), and the Amount (0.5 Ether).
![Review Transaction](gif/review_transactions.gif)

### Contributors

Alexander Likhachev

### License
MIT
