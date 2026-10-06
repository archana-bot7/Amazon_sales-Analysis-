# DAX Measures Used

The following measures are transcribed from the supplied report.

## Net Revenue

```DAX
Net Revenue =
SUM(Amazon[TotalAmount])
- SUM(Amazon[Tax])
- SUM(Amazon[Discount])
- SUM(Amazon[ShippingCost])
```

## Profit Margin %

```DAX
Profit Margin % =
DIVIDE(
    [Total Profit],
    [Net Revenue],
    0
)
```

## Brand Rank

```DAX
Brand Rank =
RANKX(
    ALL(Amazon[Brand]),
    [Total Revenue]
)
```

## Top Brand Market Share

```DAX
Top Brand Market Share =
MAXX(
    VALUES(Amazon[Brand]),
    [Brand Market Share]
)
```

## Total Customers

```DAX
Total Customers =
DISTINCTCOUNT(Amazon[CustomerID])
```

## Total Orders

```DAX
Total Orders =
DISTINCTCOUNT('Amazon'[OrderID])
```

## Total Tax Paid

```DAX
Total Tax Paid = SUM(Amazon[Tax])
```

## Average Order Value

```DAX
Average Order Value =
DIVIDE(
    [Total Revenue],
    [Total Orders]
)
```
