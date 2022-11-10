<!-- Generated by documentation.js. Update this documentation by updating the source code. -->

### Table of Contents

*   [createOrderUiStake][1]
    *   [Parameters][2]
    *   [Examples][3]
*   [createOrder][4]
    *   [Parameters][5]
    *   [Examples][6]

## createOrderUiStake

Create an order account on the Monaco protocol using a UI stake value, the client calculates the actual stake value based on mintInfo.data.decimals using uiStakeToInteger()

### Parameters

*   `program` **Program** {program} anchor program initialized by the consuming client
*   `marketPk` **PublicKey** {PublicKey} publicKey of the market to create the order for
*   `marketOutcomeIndex` **[number][7]** {number} index of the chosen outcome
*   `forOutcome` **[boolean][8]** {boolean} whether the order is for or against the outcome
*   `price` **[number][7]** {number} price at which the order should be created, the price should be present on the outcome pool for the market
*   `stake` **[number][7]** {number} UI value of the stake, the function will determine the raw value based on the market token type

### Examples

```javascript
const marketPk = new PublicKey('7o1PXyYZtBBDFZf9cEhHopn2C9R4G6GaPwFAxaNWM33D')
const marketOutcomeIndex = 0
const forOutcome = true
const price = 1.5
const stake = 20
const order = await createOrderUiStake(program, marketPk, marketOutcomeIndex, forOutcome, price, 20)
```

Returns **CreateOrderResponse** derived order publicKey and transactionID for the request, this ID should be used to confirm the success of the transaction

## createOrder

Create an order account on the Monaco protocol using the raw token value for the order stake

### Parameters

*   `program` **Program** {program} anchor program initialized by the consuming client
*   `marketPk` **PublicKey** {PublicKey} publicKey of the market to create the order for
*   `marketOutcomeIndex` **[number][7]** {number} index of the chosen outcome
*   `forOutcome` **[boolean][8]** {boolean} whether the order is for or against the outcome
*   `price` **[number][7]** {number} price at which the order should be created, the price should be present on the outcome pool for the market
*   `stake` **BN** {number} raw token value of the order taking into account the decimal amount of the token associated with the market

### Examples

```javascript
const marketPk = new PublicKey('7o1PXyYZtBBDFZf9cEhHopn2C9R4G6GaPwFAxaNWM33D')
const marketOutcomeIndex = 0
const forOutcome = true
const price = 1.5
const stake = 20,000,000,000
const order = await createOrder(program, marketPk, marketOutcomeIndex, forOutcome, price, stake)
```

Returns **CreateOrderResponse** derived order publicKey and transactionID for the request, this ID should be used to confirm the success of the transaction

[1]: #createorderuistake

[2]: #parameters

[3]: #examples

[4]: #createorder

[5]: #parameters-1

[6]: #examples-1

[7]: https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Number

[8]: https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean