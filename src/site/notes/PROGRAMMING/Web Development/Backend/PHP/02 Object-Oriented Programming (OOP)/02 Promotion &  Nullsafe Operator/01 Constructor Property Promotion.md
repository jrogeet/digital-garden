---
ProgrammingLanguage: PHP
tags:
  - programming
  - php
  - webdevelopment
  - backend
  - OOP
dg-publish: true
Topic: OOP
---

---

> [!caution] Instead of:
>
> ```php
> declare(strict_types = 1);
>
> class Transaction
> {
> 	private float $amount;
> 	private string $description;
>
> 	public function __construct(
> 		float $amount,
> 		string $description
> 	) {
> 		$this->amount = $amount;
> 		$this->description = $description;
> 	}
>
>
> ```
>
> > [!info]- If you can't read that shit i'll format it for you:
> >
> > ```php
> > declare(strict_types = 1);
> >
> > class Transaction {
> > 	private float $amount;
> > 	private string $description;
> >
> > 	public function __construct(float $amount, string $description) {
> > 		$this->amount = $amount;
> > 		$this->description = $description;
> > 	}
> > }
> > ```

> [!done] **We can do the same with just this**:
>
> ```php
> declare(strict_types = 1);
>
> class Transaction
> {
> 	public function __construct(
> 		private float $amount,
> 		private string $description
> 	) {
>
> 	}
>
> }
> ```
>
> > [!info]- If you can't read that shit i'll format it for you:
> >
> > ```php
> > declare(strict_types = 1);
> >
> > class Transaction {
> >
> > 	public function __construct(private float $amount, private string $description) {
> > 	}
> > }
> > ```

> [!example] Some variants:
>
> - You don't need to **_promote every_** `property`
>
> ```php
> declare(strict_types = 1);
>
> class Transaction
> {
> 	private float $amount;
>
> 	public function __construct(
> 		float $amount,
> 		private string $description
> 	) {
> 		$this->amount = $amount; // Modify the value
> 	}
>
> }
> ```

> [!tip] Callable
>
> ```php
> declare(strict_types = 1);
>
> class Transaction
> {
> 	private float $amount;
> 	private string $description;
>
> 	public function __construct(
> 		float $amount,
> 		callable $description
> 	) {
> 	}
> }
> ```

> [!tip] Default Value
>
> ```php
> declare(strict_types = 1);
>
> class Transaction
> {
> 	private float $amount;
>
> 	public function __construct (
> 		float $amount,
> 		private string $description	= 'hello'
> 	) {
> 		$this->amount = $amount;
> 	}
> }
> ```
>
> `null` value
> Set the **_type_** into **Nullable type** with `?`
>
> ```php
> private ?string $description  = null
> ```
