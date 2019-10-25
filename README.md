# Google Tag Manager Enhanced eCommerce Tag
This tag utilizes Google Tag Manager’s `dataLayer` to populate a formatted Partnerize purchase event tracking tag.
## dataLayer Format
The [Enhanced Ecommerce Developer Guide](https://developers.google.com/tag-manager/enhanced-ecommerce) lists the required formatted for the `dataLayer` as it relates to this tag. You can view the specific requirements under the [Measuring Purchases](https://developers.google.com/tag-manager/enhanced-ecommerce#purchases) header.
### Example
```<script>
// Send transaction data with a pageview if available
// when the page loads. Otherwise, use an event when the transaction
// data becomes available.
dataLayer.push({
  ‘ecommerce’: {
    ‘purchase’: {
      ‘actionField’: {
        ‘id’: ‘T12345’,                         // Transaction ID. Required for purchases and refunds.
        ‘affiliation’: ‘Online Store’,
        ‘revenue’: ’35.43’,                     // Total transaction value (incl. tax and shipping)
        ‘tax’:’4.90’,
        ‘shipping’: ‘5.99’,
        ‘coupon’: ‘SUMMER_SALE’
      },
      ‘products’: [{                            // List of productFieldObjects.
        ‘name’: ‘Triblend Android T-Shirt’,     // Name or ID is required.
        ‘id’: ‘12345’,
        ‘price’: ’15.25’,
        ‘brand’: ‘Google’,
        ‘category’: ‘Apparel’,
        ‘variant’: ‘Gray’,
        ‘quantity’: 1,
        ‘coupon’: ‘’                            // Optional fields may be omitted or set to empty string.
       },
       {
        ‘name’: ‘Donut Friday Scented T-Shirt’,
        ‘id’: ‘67890’,
        ‘price’: ’33.75’,
        ‘brand’: ‘Google’,
        ‘category’: ‘Apparel’,
        ‘variant’: ‘Black’,
        ‘quantity’: 1
       }]
    }
  }
});
</script>```
