---
{"dg-publish":true,"permalink":"/programming/web-development/backend/php/01-procedural/04-control-structures/03-switch/","tags":["programming","php","webdevelopment","backend"],"created":"2024-11-09T11:30:30.264+08:00"}
---


--- 
```php
$paymentStatus = 'paid';

switch($paymentStatus) {
	case 'paid':
		echo 'Paid';
		break;

	// FALL THROUGH
	// 'declined' or 'rejected'
	case 'declined':
	case 'rejected':
		echo 'Payment declined';
		break;

	case 'pending':
		echo 'Pending Payment';
		break;

	default:
		echo 'Unknown Payment Status';
}
```

```php
$paymentStatuses = [1, 3, 0];

foreach($paymentStatuses as $paymentStatus) {
	switch ($paymentStatus ){
		case 1:
			echo 'Paid';
			break 2; // Break of both the loops
			continue 2; // OUTPUT: PaidPayment Declined (<br />) Pending Payment
		
		case 2:
		case 3:
			echo 'Payment Declined';
			break;
			
		case 0:
			echo 'Pending Payment';
			break;
			
		default: 
			echo 'Unknown Payment Status';
	}
	
	echo '<br />';
}

// 'Paid'
// 'Payment Declined'
// 'Pending Payment'
```