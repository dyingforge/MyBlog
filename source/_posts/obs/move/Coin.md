```move
module coin::dog;

  

use std::option::{Option, none, some};

use sui::coin::create_currency;

use sui::transfer;

use sui::url::{Self, Url};

  

public struct DOG has drop {}

  

fun init(dog: DOG, ctx: &mut TxContext) {

    let no: Option<Url> = none<Url>();

    let url = url::new_unsafe_from_bytes(b"");

    let yes: Option<Url> = some<Url>(url);

    let (treasury, coinmeta) = create_currency(dog, 8, b"dog", b"dog", b"a happy dog", no, ctx);

    transfer::public_freeze_object(coinmeta);

    transfer::public_transfer(treasury, ctx.sender())

}
```