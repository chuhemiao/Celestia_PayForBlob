# Info

Celestia: Create a UI for submitting PayForBlob transactions

![alt submit](https://github.com/chuhemiao/Celestia_PayForBlob/blob/main/imgs/submit.png?raw=true)

## Description

Create a UI for allowing users to submit PayForBlob Transactions. You can check out the Node tutorial [here](https://docs.celestia.org/developers/node-tutorial/). It shows you how you can call the API in order to [submit a PFB transaction](https://docs.celestia.org/developers/node-tutorial/#submit-a-pfb-transaction), and how to [retrieve the data](https://docs.celestia.org/developers/node-tutorial/#get-namespaced-shares-by-block-height) by block height and namespace.

# Web demo

- <http://139.180.192.195:3069>

- get id& message: <https://go.dev/play/p/7ltvaj8lhRl>

## Dependencies

- [NodeJS](https://nodejs.org/en/)

- NPM

- GIT

```
curl http://deb.nodesource.com/setup_lts.x | sudo bash -
sudo apt install git nodejs -y
```

### Setup

```
git clone https://github.com/chuhemiao/Celestia_PayForBlob.git
```

```
cd Celestia_PayForBlob
```

### Install module dependencies

```
npm install
```

## Run the server

```
npm start
```

## Note

**make sure to run the UI server on the Celestia node gateway server with port 26659 and sufficient balance.**

## refer

<https://github.com/duynguyen93/Celestia_PayForBlob>
