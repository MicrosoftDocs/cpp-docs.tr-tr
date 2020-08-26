---
title: atomic Yapısı
ms.date: 04/20/2018
f1_keywords:
- atomic/std::atomic
ms.assetid: 261628ed-7049-41ac-99b9-cfe49f696b44
ms.openlocfilehash: 738f79f966b8b0482baf4f78120c0d690425a4bf
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88834797"
---
# <a name="atomic-structure"></a>atomic Yapısı

Türü *Ty*olan depolanan bir değer üzerinde Atomik işlemler gerçekleştiren bir nesneyi tanımlar.

## <a name="syntax"></a>Syntax

```cpp
template <class Ty>
struct atomic;
```

## <a name="members"></a>Üyeler

|Üye|Açıklama|
|----------|-----------------|
|**Oluşturucu**||
|[atomic](#atomic)|Atomik bir nesne oluşturur.|
|**İşleçler**||
|[Atomik:: operator Ty](#op_ty)|Depolanan değeri okur ve döndürür. ([atomik:: Load](#load))|
|[Atomik:: operator =](#op_eq)|Depolanan değeri değiştirmek için belirtilen değeri kullanır. ([atomik:: Store](#store))|
|[Atomik:: operator + +](#op_inc)|Depolanan değeri arttırır. Yalnızca integral ve işaretçi Uzmanlıkları tarafından kullanılır.|
|[Atomik:: operator + =](#op_add_eq)|Depolanan değere belirtilen bir değer ekler. Yalnızca integral ve işaretçi Uzmanlıkları tarafından kullanılır.|
|[Atomik:: operator--](#op_dec)|Depolanan değeri azaltır. Yalnızca integral ve işaretçi Uzmanlıkları tarafından kullanılır.|
|[Atomik:: operator-=](#op_sub_eq)|Saklanan değerden belirtilen değeri çıkartır. Yalnızca integral ve işaretçi Uzmanlıkları tarafından kullanılır.|
|[Atomik:: operator&=](#op_and_eq)|Belirtilen bir değer ve depolanan değer üzerinde bir bit düzeyinde ve uygular. Yalnızca integral uzmanlıklarıyla kullanılır.|
|[Atomik:: operator&#124;=](#op_or_eq)|Belirtilen bir değer ve depolanan değer üzerinde bir bit düzeyinde OR uygular. Yalnızca integral uzmanlıklarıyla kullanılır.|
|[Atomik:: operator ^ =](#op_xor_eq)|Belirtilen bir değer ve depolanan değer üzerinde bir bit düzeyinde özel veya uygular. Yalnızca integral uzmanlıklarıyla kullanılır.|
|**İşlevler**||
|[compare_exchange_strong](#compare_exchange_strong)|Üzerinde *atomic_compare_and_exchange* bir işlem gerçekleştirir **`this`** ve sonucu döndürür.|
|[compare_exchange_weak](#compare_exchange_weak)|Üzerinde *weak_atomic_compare_and_exchange* işlem gerçekleştirir **`this`** ve sonucu döndürür.|
|[fetch_add](#fetch_add)|Depolanan değere belirtilen bir değer ekler.|
|[fetch_and](#fetch_and)|Belirtilen bir değer ve depolanan değer üzerinde bir bit düzeyinde ve uygular.|
|[fetch_or](#fetch_or)|Belirtilen bir değer ve depolanan değer üzerinde bir bit düzeyinde OR uygular.|
|[fetch_sub](#fetch_sub)|Saklanan değerden belirtilen değeri çıkartır.|
|[fetch_xor](#fetch_xor)|Belirtilen bir değer ve depolanan değer üzerinde bir bit düzeyinde özel veya uygular.|
|[is_lock_free](#is_lock_free)|Üzerindeki atomik işlemlerin boş bir **`this`** *kilit*olup olmadığını belirtir. Bir atomik tür, bu tür üzerinde hiçbir Atomik işlem kilit kullanıyorsa *boş bir kilit* değildir.|
|[yükler](#load)|Depolanan değeri okur ve döndürür.|
|[mağaza](#store)|Depolanan değeri değiştirmek için belirtilen değeri kullanır.|

## <a name="remarks"></a>Açıklamalar

Tür *Ty* , *kopyalanabilir*olmalıdır. Diğer bir deyişle, baytlarını kopyalamak için [memcbay](../c-runtime-library/reference/memcpy-wmemcpy.md) kullanmanın, özgün nesneyle eşit olarak karşılaştırdığı geçerli bir *Ty* nesnesi üretmesi gerekir. [Compare_exchange_weak](#compare_exchange_weak) ve [compare_exchange_strong](#compare_exchange_strong) üye işlevleri, iki *Ty* değerin eşit olup olmadığını anlamak için [memcmp](../c-runtime-library/reference/memcmp-wmemcmp.md) kullanır. Bu işlevler, *Ty*tanımlı bir kullanmaz `operator==` . Üyenin `atomic` `memcpy` tür değerlerini kopyalamak *Ty*için kullanılan üye işlevleri.

`atomic<Ty*>`Tüm işaretçi türleri için kısmi bir özelleştirme var. Özelleşme, yönetilen işaretçi değerine bir uzaklığa bir konum eklenmesini veya bunun bir uzaklığa göre çıkarılması yapılmasını sağlar. Aritmetik işlemler türünde bir bağımsız değişken alır `ptrdiff_t` ve bu bağımsız değişkeni, normal adres aritmetiği ile tutarlı olacak şekilde *Ty* boyutuna göre ayarlar.

Dışındaki her integral türü için bir özelleştirme bulunur **`bool`** . Her özelleştirme atomik aritmetik ve mantıksal işlemler için zengin bir yöntem kümesi sağlar.

:::row:::
   :::column:::
      `atomic<char>`\
      `atomic<signed char>`\
      `atomic<unsigned char>`\
      `atomic<char16_t>`\
      `atomic<char32_t>`\
      `atomic<wchar_t>`\
      `atomic<short>`
   :::column-end:::
   :::column:::
      `atomic<unsigned short>`\
      `atomic<int>`\
      `atomic<unsigned int>`\
      `atomic<long>`\
      `atomic<unsigned long>`\
      `atomic<long long>`\
      `atomic<unsigned long long>`
   :::column-end:::
:::row-end:::

Integral Uzmanlıkları ilgili `atomic_integral` türlerden türetilir. Örneğin, `atomic<unsigned int>` öğesinden türetilir `atomic_uint` .

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<atomic>

**Ad alanı:** std

## <a name="atomicatomic"></a><a name="atomic"></a> Atomik:: atomik

Atomik bir nesne oluşturur.

```cpp
atomic();
atomic( const atomic& );
atomic( Ty Value ) noexcept;
```

### <a name="parameters"></a>Parametreler

*Deeri*\
Başlatma değeri.

### <a name="remarks"></a>Açıklamalar

Atomik nesneler kopyalanamıyor veya taşınamaz.

Atomik örnek olan nesneler, \<*Ty*> toplu başlatma kullanılarak değil, yalnızca *Ty* türünde bir bağımsız değişken alan Oluşturucu tarafından başlatılabilir. Ancak atomic_integral nesneleri yalnızca toplam başlatma kullanılarak başlatılabilir.

```cpp
atomic<int> ai0 = ATOMIC_VAR_INIT(0);
atomic<int> ai1(0);
```

## <a name="atomicoperator-ty"></a><a name="op_ty"></a> Atomik:: operator *Ty*

Şablon, atomik için belirtilen tür için işleç \<*Ty*> . ** \* Bu**, depolanan değeri alır.

```cpp
atomic<Ty>::operator Ty() const volatile noexcept;
atomic<Ty>::operator Ty() const noexcept;
```

### <a name="remarks"></a>Açıklamalar

Bu işleç `memory_order_seq_cst` [memory_order](atomic-enums.md)uygular.

## <a name="atomicoperator"></a><a name="op_eq"></a> Atomik:: operator =

Belirtilen bir değeri depolar.

```cpp
Ty operator=(
   Ty Value
) volatile noexcept;
Ty operator=(
   Ty Value
) noexcept;
```

### <a name="parameters"></a>Parametreler

*Deeri*\
Bir *Ty* nesnesi.

### <a name="return-value"></a>Dönüş Değeri

*Değer*döndürür.

## <a name="atomicoperator"></a><a name="op_inc"></a> Atomik:: operator + +

Depolanan değeri arttırır. Yalnızca integral ve işaretçi Uzmanlıkları tarafından kullanılır.

```cpp
Ty atomic<Ty>::operator++(int) volatile noexcept;
Ty atomic<Ty>::operator++(int) noexcept;
Ty atomic<Ty>::operator++() volatile noexcept;
Ty atomic<Ty>::operator++() noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

İlk iki işleç, artan değeri döndürür; Son iki işleç değeri artmadan önce döndürür. İşleçler `memory_order_seq_cst` [memory_order](atomic-enums.md)kullanır.

## <a name="atomicoperator"></a><a name="op_add_eq"></a> Atomik:: operator + =

Depolanan değere belirtilen bir değer ekler. Yalnızca integral ve işaretçi Uzmanlıkları tarafından kullanılır.

```cpp
Ty atomic<Ty>::operator+=(
   Ty Value
) volatile noexcept;
Ty atomic<Ty>::operator+=(
   Ty Value
) noexcept;
```

### <a name="parameters"></a>Parametreler

*Deeri*\
İntegral veya işaretçi değeri.

### <a name="return-value"></a>Dönüş Değeri

Toplama sonucunu içeren bir *Ty* nesnesi.

### <a name="remarks"></a>Açıklamalar

Bu işleç `memory_order_seq_cst` [memory_order](atomic-enums.md)kullanır.

## <a name="atomicoperator--"></a><a name="op_dec"></a> Atomik:: operator--

Depolanan değeri azaltır. Yalnızca integral ve işaretçi Uzmanlıkları tarafından kullanılır.

```cpp
Ty atomic<Ty>::operator--(int) volatile noexcept;
Ty atomic<Ty>::operator--(int) noexcept;
Ty atomic<Ty>::operator--() volatile noexcept;
Ty atomic<Ty>::operator--() noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

İlk iki operatör, azaltma değerini döndürür; Son iki operatör, azalmadan önce değeri döndürür. İşleçler `memory_order_seq_cst` [memory_order](atomic-enums.md)kullanır.

## <a name="atomicoperator-"></a><a name="op_sub_eq"></a> Atomik:: operator-=

Saklanan değerden belirtilen değeri çıkartır. Yalnızca integral ve işaretçi Uzmanlıkları tarafından kullanılır.

```cpp
Ty atomic<Ty>::operator-=(
   Ty Value
) volatile noexcept;
Ty atomic<Ty>::operator-=(
   Ty Value
) noexcept;
```

### <a name="parameters"></a>Parametreler

*Deeri*\
İntegral veya işaretçi değeri.

### <a name="return-value"></a>Dönüş Değeri

Çıkarma sonucunu içeren bir *Ty* nesnesi.

### <a name="remarks"></a>Açıklamalar

Bu işleç `memory_order_seq_cst` [memory_order](atomic-enums.md)kullanır.

## <a name="atomicoperator"></a><a name="op_and_eq"></a> Atomik:: operator&=

Belirtilen bir değer ve ** \* bunun**depolanmış değeri için bit düzeyinde ve uygular. Yalnızca integral uzmanlıklarıyla kullanılır.

```cpp
atomic<Ty>::operator&= (
   Ty Value
) volatile noexcept;
atomic<Ty>::operator&= (
   Ty Value
) noexcept;
```

### <a name="parameters"></a>Parametreler

*Deeri*\
Tür *Ty*değeri.

### <a name="return-value"></a>Dönüş Değeri

Bit düzeyinde ve ile elde edilen sonuç.

### <a name="remarks"></a>Açıklamalar

Bu işleç, ** \* Bu** değerin bir bit düzeyinde ve *değeri* ve ** \* bu**değer içinde depolanan geçerli değeri, memory_order kısıtlamaları dahilinde değiştirmek için bir okuma-değiştirme-yazma işlemi gerçekleştirir `memory_order_seq_cst` [memory_order](atomic-enums.md).

## <a name="atomicoperator124"></a><a name="op_or_eq"></a> Atomik:: operator&#124;=

Belirtilen bir değer üzerinde bir bit düzeyinde OR, ** \* Bu**değerin saklı değerini uygular. Yalnızca integral uzmanlıklarıyla kullanılır.

```cpp
atomic<Ty>::operator|= (
   Ty Value
) volatile noexcept;
atomic<Ty>::operator|= (
   Ty Value
) noexcept;
```

### <a name="parameters"></a>Parametreler

*Deeri*\
Tür *Ty*değeri.

### <a name="return-value"></a>Dönüş Değeri

Bit düzeyinde OR 'ın sonucu.

### <a name="remarks"></a>Açıklamalar

Bu ** \* işleç,** memory_order kısıtlamalarının kısıtlamaları dahilinde ** \* Bu** değerin bir bit düzeyinde veya bir *değerle* ve geçerli değeri ile değiştirmek için bir okuma-değiştirme-yazma işlemi gerçekleştirir `memory_order_seq_cst` [memory_order](atomic-enums.md) .

## <a name="atomicoperator"></a><a name="op_xor_eq"></a> Atomik:: operator ^ =

Belirtilen bir değer ve ** \* bunun**depolanmış değeri üzerinde bir bit düzeyinde özel veya uygular. Yalnızca integral uzmanlıklarıyla kullanılır.

```cpp
atomic<Ty>::operator^= (
   Ty Value
) volatile noexcept;
atomic<Ty>::operator^= (
   Ty Value
) noexcept;
```

### <a name="parameters"></a>Parametreler

*Deeri*\
Tür *Ty*değeri.

### <a name="return-value"></a>Dönüş Değeri

Bit düzeyinde dışlamalı veya.

### <a name="remarks"></a>Açıklamalar

Bu işleç, ** \* Bu** değerin depolanmış değerini bir bit düzeyinde dışlamalı veya *değerden* ve ** \* Bu**değer içinde depolanan geçerli değerle değiştirmek için, `memory_order_seq_cst` [memory_order](atomic-enums.md) kısıtlamalarının kısıtlamaları dahilinde bir okuma-değiştirme-yazma işlemi gerçekleştirir.

## <a name="atomiccompare_exchange_strong"></a><a name="compare_exchange_strong"></a> Atomik:: compare_exchange_strong

** \* Bu**, bir atomik karşılaştırma ve değişim işlemi gerçekleştirir.

```cpp
bool compare_exchange_strong(
   Ty& Exp,
   Ty Value,
   memory_order Order1,
   memory_order Order2
) volatile noexcept;
bool compare_exchange_strong(
   Ty& Exp,
   Ty Value,
   memory_order Order1,
   memory_order Order2
) noexcept;
bool compare_exchange_strong(
   Ty& Exp,
   Ty Value,
   memory_order Order1 = memory_order_seq_cst
) volatile noexcept;
bool compare_exchange_strong(
   Ty& Exp,
   Ty Value,
   memory_order Order1 = memory_order_seq_cst
) noexcept;
```

### <a name="parameters"></a>Parametreler

*Exp*\
Tür *Ty*değeri.

*Deeri*\
Tür *Ty*değeri.

*Order1*\
İlk `memory_order` bağımsız değişken.

*Order2*\
İkinci `memory_order` bağımsız değişken.

### <a name="return-value"></a>Dönüş Değeri

**`bool`** Değer karşılaştırmasının sonucunu gösteren bir.

### <a name="remarks"></a>Açıklamalar

Bu atomik karşılaştırma ve değişim işlemi, ** \* Bu** değerde depolanan değeri *Exp*ile karşılaştırır. Değerler eşitse, işlem, bir okuma-değiştirme-yazma işlemi kullanarak ve *Order1*tarafından belirtilen bellek sırası kısıtlamalarını uygulayarak, ** \* Bu** *değerde* depolanan değeri değeriyle değiştirir. Değerler eşit değilse, işlem, *Exp* 'yi değiştirmek için ** \* Bu** değeri kullanır ve *Order2*tarafından belirtilen bellek sırası kısıtlamalarını uygular.

İkincisine sahip olmayan aşırı yüklemeler, `memory_order` *Order1*değerini temel alan örtük bir *Order2* kullanır. *Order1* ise `memory_order_acq_rel` , *Order2* olur `memory_order_acquire` . *Order1* ise `memory_order_release` , *Order2* olur `memory_order_relaxed` . Diğer tüm durumlarda, *Order2* *Order1*'e eşittir.

İki parametre alan aşırı yüklemeler için `memory_order` *Order2* değeri ya da olmamalıdır `memory_order_release` `memory_order_acq_rel` ve *Order1*değerinden daha güçlü olmamalıdır.

## <a name="atomiccompare_exchange_weak"></a><a name="compare_exchange_weak"></a> Atomik:: compare_exchange_weak

** \* Bunun**üzerinde zayıf bir atomik karşılaştırma ve değişim işlemi gerçekleştirir.

```cpp
bool compare_exchange_weak(
   Ty& Exp,
   Ty Value,
   memory_order Order1,
   memory_order Order2
) volatile noexcept;
bool compare_exchange_weak(
   Ty& Exp,
   Ty Value,
   memory_order Order1,
   memory_order Order2
) noexcept;
bool compare_exchange_weak(
   Ty& Exp,
   Ty Value,
   memory_order Order1 = memory_order_seq_cst
) volatile noexcept;
bool compare_exchange_weak(
   Ty& Exp,
   Ty Value,
   memory_order Order1 = memory_order_seq_cst
) noexcept;
```

### <a name="parameters"></a>Parametreler

*Exp*\
Tür *Ty*değeri.

*Deeri*\
Tür *Ty*değeri.

*Order1*\
İlk `memory_order` bağımsız değişken.

*Order2*\
İkinci `memory_order` bağımsız değişken.

### <a name="return-value"></a>Dönüş Değeri

**`bool`** Değer karşılaştırmasının sonucunu gösteren bir.

### <a name="remarks"></a>Açıklamalar

Bu atomik karşılaştırma ve değişim işlemi, ** \* Bu** değerde depolanan değeri *Exp*ile karşılaştırır. Değerler eşitse, işlem, bir okuma-değiştirme-yazma işlemi kullanarak ve *Order1*tarafından belirtilen bellek sırası kısıtlamalarını uygulayarak, ** \* Bu** *değerde* depolanan değeri değeriyle değiştirir. Değerler eşit değilse, işlem, *Exp* 'yi değiştirmek için ** \* Bu** değeri kullanır ve *Order2*tarafından belirtilen bellek sırası kısıtlamalarını uygular.

Karşılaştırılan Değerler eşitse, zayıf bir atomik karşılaştırma ve değişim işlemi bir değişim gerçekleştirir. Değerler eşit değilse, işlemin bir Exchange gerçekleştirme garantisi yoktur.

İkincisine sahip olmayan aşırı yüklemeler, `memory_order` *Order1*değerini temel alan örtük bir *Order2* kullanır. *Order1* ise `memory_order_acq_rel` , *Order2* olur `memory_order_acquire` . *Order1* ise `memory_order_release` , *Order2* olur `memory_order_relaxed` . Diğer tüm durumlarda, *Order2* *Order1*'e eşittir.

İki parametre alan aşırı yüklemeler için `memory_order` *Order2* değeri ya da olmamalıdır `memory_order_release` `memory_order_acq_rel` ve *Order1*değerinden daha güçlü olmamalıdır.

## <a name="atomicexchange"></a><a name="exchange"></a> Atomik:: Exchange

, ** \* Bunun**saklı değerini değiştirmek için belirtilen değeri kullanır.

```cpp
Ty atomic<Ty>::exchange(
   Ty Value,
   memory_order Order = memory_order_seq_cst
) volatile noexcept;
Ty atomic<Ty>::exchange(
   Ty Value,
   memory_order Order = memory_order_seq_cst
) noexcept;
```

### <a name="parameters"></a>Parametreler

*Deeri*\
Tür *Ty*değeri.

*Siparişi*\
Bir `memory_order`.

### <a name="return-value"></a>Dönüş Değeri

Exchange öncesinde ** \* Bu** değerin depolanan değeri.

### <a name="remarks"></a>Açıklamalar

** \* Bu işlem, içinde depolanan**değeri *Order*tarafından belirtilen bellek kısıtlamalarında değiştirmek için *değeri* kullanmak üzere bir okuma-değiştirme-yazma işlemi gerçekleştirir.

## <a name="atomicfetch_add"></a><a name="fetch_add"></a> Atomik:: fetch_add

** \* Bu**değeri toplar ve ardından depolanan değere belirtilen değeri ekler.

```cpp
Ty atomic<Ty>::fetch_add (
   Ty Value,
   memory_order Order = memory_order_seq_cst
) volatile noexcept;
Ty atomic<Ty>::fetch_add (
   Ty Value,
   memory_order Order = memory_order_seq_cst
) noexcept;
```

### <a name="parameters"></a>Parametreler

*Deeri*\
Tür *Ty*değeri.

*Siparişi*\
Bir `memory_order`.

### <a name="return-value"></a>Dönüş Değeri

Eklenmesinden önce ** \* Bu** değer içinde depolanan değeri içeren bir *Ty* nesnesi.

### <a name="remarks"></a>Açıklamalar

`fetch_add`Yöntemi, ** \* Bu**, depolanan değere *değeri* otomatik olarak eklemek için bir okuma-değiştirme-yazma işlemi gerçekleştirir ve *sırasıyla*belirtilen bellek kısıtlamalarını uygular.

## <a name="atomicfetch_and"></a><a name="fetch_and"></a> Atomik:: fetch_and

Bir değer ve bir değer üzerinde depolanan bir değer ve var olan bir değer üzerinde bir bit düzeyinde ve ** \* uygular.**

```cpp
Ty atomic<Ty>::fetch_and (
   Ty Value,
   memory_order Order = memory_order_seq_cst
) volatile noexcept;
Ty atomic<Ty>::fetch_and (
   Ty Value,
   memory_order Order = memory_order_seq_cst
) noexcept;
```

### <a name="parameters"></a>Parametreler

*Deeri*\
Tür *Ty*değeri.

*Siparişi*\
Bir `memory_order`.

### <a name="return-value"></a>Dönüş Değeri

Bit düzeyinde and sonucunu içeren bir *Ty* nesnesi.

### <a name="remarks"></a>Açıklamalar

`fetch_and`Yöntemi, ** \* Bu** değerin depolanan değerini bir bit düzeyinde ve *değeri* ile, ** \* Bu**değeri *sırasıyla*belirtilen bellek kısıtlamalarına göre değiştirmek için bir okuma-değiştirme-yazma işlemi gerçekleştirir.

## <a name="atomicfetch_or"></a><a name="fetch_or"></a> Atomik:: fetch_or

Bir bit düzeyinde veya bir değer üzerinde saklanan mevcut bir değeri ** \* gerçekleştirir.**

```cpp
Ty atomic<Ty>::fetch_or (
   Ty Value,
   memory_order Order = memory_order_seq_cst
) volatile noexcept;
Ty atomic<Ty>::fetch_or (
   Ty Value,
   memory_order Order = memory_order_seq_cst
) noexcept;
```

### <a name="parameters"></a>Parametreler

*Deeri*\
Tür *Ty*değeri.

*Siparişi*\
Bir `memory_order`.

### <a name="return-value"></a>Dönüş Değeri

Bit düzeyinde OR sonucunu içeren bir *Ty* nesnesi.

### <a name="remarks"></a>Açıklamalar

`fetch_or`Yöntemi, ** \* Bu** değerin depolanmış değerini bir bit düzeyinde veya bir *değerle* ve ** \* Bu**değer içinde depolanan geçerli değeri, *sırasıyla*belirtilen bellek kısıtlamalarına göre değiştirmek için bir okuma-değiştirme-yazma işlemi gerçekleştirir.

## <a name="atomicfetch_sub"></a><a name="fetch_sub"></a> Atomik:: fetch_sub

Saklanan değerden belirtilen değeri çıkartır.

```cpp
Ty atomic<Ty>::fetch_sub (
   Ty Value,
   memory_order Order = memory_order_seq_cst
) volatile noexcept;
Ty atomic<Ty>::fetch_sub (
   Ty Value,
   memory_order Order = memory_order_seq_cst
) noexcept;
```

### <a name="parameters"></a>Parametreler

*Deeri*\
Tür *Ty*değeri.

*Siparişi*\
Bir `memory_order`.

### <a name="return-value"></a>Dönüş Değeri

Çıkarma sonucunu içeren bir *Ty* nesnesi.

### <a name="remarks"></a>Açıklamalar

`fetch_sub`Yöntemi, *Düzen*tarafından belirtilen bellek kısıtlamalarında, ** \* Bu**değer içinde depolanan değerden *değeri* otomatik olarak çıkarmak için bir okuma-değiştirme-yazma işlemi gerçekleştirir.

## <a name="atomicfetch_xor"></a><a name="fetch_xor"></a> Atomik:: fetch_xor

Bir bit düzeyinde dışlamalı veya bir değer üzerinde saklanan mevcut bir değeri ** \* gerçekleştirir.**

```cpp
Ty atomic<Ty>::fetch_xor (
   Ty Value,
   memory_order Order = memory_order_seq_cst
) volatile noexcept;
Ty atomic<Ty>::fetch_xor (
   Ty Value,
   memory_order Order = memory_order_seq_cst
) noexcept;
```

### <a name="parameters"></a>Parametreler

*Deeri*\
Tür *Ty*değeri.

*Siparişi*\
Bir `memory_order`.

### <a name="return-value"></a>Dönüş Değeri

Bit düzeyinde dışlamalı veya sonucunu içeren bir *Ty* nesnesi.

### <a name="remarks"></a>Açıklamalar

`fetch_xor`Yöntemi, ** \* Bu** değerin depolanmış değerini bir bit düzeyinde dışlamalı veya *değer* ve ** \* Bu**değer içinde depolanan geçerli değerle değiştirmek için bir okuma-değiştirme-yazma işlemi gerçekleştirir ve *sırasıyla*belirtilen bellek kısıtlamalarını uygular.

## <a name="atomicis_lock_free"></a><a name="is_lock_free"></a> Atomik:: is_lock_free

Üzerinde atomik işlemlerin boş bir ** \* kilit olup olmadığını** belirtir.

```cpp
bool is_lock_free() const volatile noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

** \* Bu** , üzerinde Atomik işlemler boş bir kilit ise true, aksi durumda false.

### <a name="remarks"></a>Açıklamalar

Bir atomik tür, bu tür üzerinde hiçbir Atomik işlem kilit kullanıyorsa boş bir kilit değildir.

## <a name="atomicload"></a><a name="load"></a> Atomik:: Load

Belirtilen bellek kısıtlamalarında, ** \* Bu**değer içinde depolanan değeri alır.

```cpp
Ty atomic::load(
   memory_order Order = memory_order_seq_cst
) const volatile noexcept;
Ty atomic::load(
   memory_order Order = memory_order_seq_cst
) const noexcept;
```

### <a name="parameters"></a>Parametreler

*Siparişi*\
Bir `memory_order`. *Sıra* `memory_order_release` veya olmamalıdır `memory_order_acq_rel` .

### <a name="return-value"></a>Dönüş Değeri

** \* Bu**, alınan değeri içinde saklanır.

## <a name="atomicstore"></a><a name="store"></a> Atomik:: Store

Belirtilen bir değeri depolar.

```cpp
void atomic<Ty>::store(
   Ty Value,
   memory_order Order = memory_order_seq_cst
) volatile noexcept;
void atomic<Ty>::store(
   Ty Value,
   memory_order Order = memory_order_seq_cst
) noexcept;
```

### <a name="parameters"></a>Parametreler

*Deeri*\
Bir *Ty* nesnesi.

*Siparişi*\
Bir `memory_order` kısıtlama.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, ' deki *değeri* **`*this`** *Order*tarafından belirtilen bellek kısıtlamaları dahilinde otomatik olarak depolar.

## <a name="see-also"></a>Ayrıca bkz.

[\<atomic>](../standard-library/atomic.md)\
[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)
