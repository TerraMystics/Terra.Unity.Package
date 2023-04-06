<br/>
<p align="center">
    <a href="https://github.com/TerraMystics"><img src="./CIcon.jpg" align="center" width=350/></a>
</p>

<p align="center">
A lightweight payment management library for the terra ecosystem for the Unity GameEngine

</p>
<br/>

<p align="center">
  <a href="https://terradocs.money/"><strong>Explore the Docs »</strong></a>
  <br />
</p>

Internally manages gas estimation required by the burn tax for successful transactions on the blockchain. Makes it easier for devs to get started with payments on the LUNC/LUNA Blockchains.

## Features

- **Written in C#**, with type definitions
- Makes it easier to manage payments for anyone deploying to the Apple or Google app stores

## Installation & Configuration

Please make sure to import the following [package](https://github.com/TerraMystics/Terra.Unity.Package/blob/main/terra.payments.unitypackage) into your project as an asset.

Please also make sure to install the following [dependency](https://docs.unity3d.com/Packages/com.unity.nuget.newtonsoft-json@3.0/manual/index.html) package into your project too.

## Usage

This package can be used for Mobile & Web Developers working with Unity, or SDK Developers looking to extend the Terra Platform

### Manage Payments

Please note: **PaymentsManager** must be registered as a Singleton to prevent issues with the Connection Pool.

```cs
void ProcessPaymentForTerra() {
     // Wallet where customer payments will be transferred to
     string businessWallet = "terra17lmam6zguazs5q5u6z5mmx76uj63gldnse2pdp";
     string customerWallet = "terra1x46rqay4d3cssq8gxxvqz8xt6nwlz4td20k38v";

     // Recovery Words of the Customer wallet that will be making the payment
     string customerRecoveryWords = "notice oak worry limit wrap speak medal online prefer cluster roof addict wrist behave treat actual wasp year salad speed social layer crew genius";

     // Configure your PaymentManager
     // Set Blockchain to target (in this case Classic)
     var paymentsManager = new PaymentsManager(TerraEnvironment.Classic)
                               .ConfigureBusinessWallet(businessWallet) // Configure your Business Wallet
                               .ConfigureCustomerWallet(customerRecoveryWords, customerWallet); // Configure the Customer Wallet

     // Charge customer with LUNC
     var receipt = await paymentsManager.ChargeCustomer(100);
}
```

## License

This software is licensed under the MIT license. See [LICENSE](./LICENSE) for full disclosure.

© 2022 TerraMystics.
