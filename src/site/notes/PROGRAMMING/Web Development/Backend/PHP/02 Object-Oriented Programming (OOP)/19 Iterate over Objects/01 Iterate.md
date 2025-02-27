---
{"dg-publish":true,"permalink":"/programming/web-development/backend/php/02-object-oriented-programming-oop/19-iterate-over-objects/01-iterate/","tags":["programming","php","webdevelopment","backend","OOP"],"created":"2024-11-09T11:30:32.843+08:00"}
---


---

> [!info] > `foreach` can also **iterate** over the `properties` of an `Object`
>
> ```php
> namespace App;
>
> class Invoice
> {
> 	public string $id;
>
> 	public function __construct(public float $amount)
> 	{
> 		$this->id = random_int(10000, 9999999);
> 	}
> }
> ```
>
> ```PHP
> foreach(new App\Invoice(25) as $key => $value) {
> 	echo $key . ' = ' . $value . PHP_EOL;
> }
> ```
>
> **_OUTPUT_**:
> ![Pasted image 20240330075226.png](/img/user/PROGRAMMING/Web%20Development/Backend/PHP/02%20Object-Oriented%20Programming%20(OOP)/19%20Iterate%20over%20Objects/attachments/Pasted%20image%2020240330075226.png)

> [!example]
>
> ```php
> $invoiceCollection = new InvoiceCollection([new \App\Invoice(15), new \App\Invoice(25), new \App\Invoice(50)]);
>
> foreach($invoiceCollection as $invoice) {
> 	echo $invoice->id . ' - ' . $invoice->amount . PHP_EOL;
> }
> ```
>
> - `\Iterator` Interface:
>
> ```php
> namespace App;
>
> class InvoiceCollection implements \Iterator
> {
> 	public function __construct(public array $invoices)
> 	{
>
> 	}
> }
> ```
