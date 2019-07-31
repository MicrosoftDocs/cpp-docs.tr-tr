---
title: atomic Yapısı
ms.date: 04/20/2018
f1_keywords:
- atomic/std::atomic
ms.assetid: 261628ed-7049-41ac-99b9-cfe49f696b44
ms.openlocfilehash: 1b3b60d71fcdf68fdf215820535c3bfb3d4dfb2b
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68456742"
---
# <a name="atomic-structure"></a>atomic Yapısı

Türü *Ty*olan depolanan bir değer üzerinde Atomik işlemler gerçekleştiren bir nesneyi tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
struct atomic;
```

## <a name="members"></a>Üyeler

|Üye|Açıklama|
|----------|-----------------|
|**Constructor**||
|[atomic](#atomic)|Atomik bir nesne oluşturur.|
|**İşleçler**||
|[Atomik:: operator Ty](#op_ty)|Depolanan değeri okur ve döndürür. ([atomik:: Load](#load))|
|[Atomik:: operator =](#op_eq)|Depolanan değeri değiştirmek için belirtilen değeri kullanır. ([atomik:: Store](#store))|
|[Atomik:: operator + +](#op_inc)|Depolanan değeri arttırır. Yalnızca integral ve işaretçi Uzmanlıkları tarafından kullanılır.|
|[Atomik:: operator + =](#op_add_eq)|Depolanan değere belirtilen bir değer ekler. Yalnızca integral ve işaretçi Uzmanlıkları tarafından kullanılır.|
|[Atomik:: operator--](#op_dec)|Depolanan değeri azaltır. Yalnızca integral ve işaretçi Uzmanlıkları tarafından kullanılır.|
|[Atomik:: operator-=](#op_sub_eq)|Saklanan değerden belirtilen değeri çıkartır. Yalnızca integral ve işaretçi Uzmanlıkları tarafından kullanılır.|
|[Atomik:: operator & =](#op_and_eq)|Belirtilen bir değer ve depolanan değer üzerinde bir bit düzeyinde ve uygular. Yalnızca integral uzmanlıklarıyla kullanılır.|
|[Atomik:: operator&#124;=](#op_or_eq)|Belirtilen bir değer ve depolanan değer üzerinde bir bit düzeyinde OR uygular. Yalnızca integral uzmanlıklarıyla kullanılır.|
|[Atomik:: operator ^ =](#op_xor_eq)|Belirtilen bir değer ve depolanan değer üzerinde bir bit düzeyinde özel veya uygular. Yalnızca integral uzmanlıklarıyla kullanılır.|
|**İşlevler**||
|[compare_exchange_strong](#compare_exchange_strong)|**Bunun** üzerinde bir *atomic_compare_and_exchange* işlemi gerçekleştirir ve sonucu döndürür.|
|[compare_exchange_weak](#compare_exchange_weak)|**Bunun** üzerinde bir *weak_atomic_compare_and_exchange* işlemi gerçekleştirir ve sonucu döndürür.|
|[fetch_add](#fetch_add)|Depolanan değere belirtilen bir değer ekler.|
|[fetch_and](#fetch_and)|Belirtilen bir değer ve depolanan değer üzerinde bir bit düzeyinde ve uygular.|
|[fetch_or](#fetch_or)|Belirtilen bir değer ve depolanan değer üzerinde bir bit düzeyinde OR uygular.|
|[fetch_sub](#fetch_sub)|Saklanan değerden belirtilen değeri çıkartır.|
|[fetch_xor](#fetch_xor)|Belirtilen bir değer ve depolanan değer üzerinde bir bit düzeyinde özel veya uygular.|
|[is_lock_free](#is_lock_free)|**Üzerinde atomik** işlemlerin *boş bir kilit*olup olmadığını belirtir. Bir atomik tür, bu tür üzerinde hiçbir Atomik işlem kilit kullanıyorsa *boş bir kilit* değildir.|
|[yükler](#load)|Depolanan değeri okur ve döndürür.|
|[saklayabilir](#store)|Depolanan değeri değiştirmek için belirtilen değeri kullanır.|

## <a name="remarks"></a>Açıklamalar

Tür *Ty* , *kopyalanabilir*olmalıdır. Diğer bir deyişle, baytlarını kopyalamak için [memcbay](../c-runtime-library/reference/memcpy-wmemcpy.md) kullanmanın, özgün nesneyle eşit olarak karşılaştırdığı geçerli bir *Ty* nesnesi üretmesi gerekir. [Compare_exchange_weak](#compare_exchange_weak) ve [compare_exchange_strong](#compare_exchange_strong) üye işlevleri, iki *Ty* değerin eşit olup olmadığını anlamak için [memcmp](../c-runtime-library/reference/memcmp-wmemcmp.md) kullanır. Bu işlevler, *Ty*tanımlı `operator==`bir kullanmaz. Üyenin tür değerlerini kopyalamak `atomic` için `memcpy` kullanılan üye *işlevleri.*

Tüm işaretçi türleri için kısmi bir özelleştirme, **atomik\<bir özellik \* >** var. Özelleşme, yönetilen işaretçi değerine bir uzaklığa bir konum eklenmesini veya bunun bir uzaklığa göre çıkarılması yapılmasını sağlar. Aritmetik işlemler türünde `ptrdiff_t` bir bağımsız değişken alır ve bu bağımsız değişkeni, normal adres aritmetiği ile tutarlı olacak şekilde *Ty* boyutuna göre ayarlar.

**Bool**hariç her integral türü için bir özelleştirme var. Her özelleştirme atomik aritmetik ve mantıksal işlemler için zengin bir yöntem kümesi sağlar.

||||
|-|-|-|
|**Atomik\<char >**|**Atomik\<işaretli char >**|**Atomik\<işaretsiz char >**|
|**Atomik\<char16_t >**|**Atomik\<char32_t >**|**Atomik\<wchar_t >**|
|**Atomik\<kısa >**|**Atomik\<işaretsiz kısa >**|**Atomik\<tamsayı >**|
|**Atomik\<işaretsiz int >**|**Atomik\<uzun >**|**Atomik\<işaretsiz uzun >**|
|**Atomik\<uzun uzun >**|**Atomik\<işaretsiz uzun uzun >**|

Integral Uzmanlıkları ilgili `atomic_integral` türlerden türetilir. Örneğin **atomik\<işaretsiz int >** , öğesinden `atomic_uint`türetilir.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<atomik >

**Ad alanı:** std

## <a name="atomic"></a>Atomik:: atomik

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

Atomik\<*değer* > örneklendirmiş nesneler, toplu başlatma kullanılarak değil, yalnızca *Ty* türünde bir bağımsız değişken alan Oluşturucu tarafından başlatılabilir. Ancak, atomic_integral nesneleri yalnızca toplam başlatma kullanılarak başlatılabilir.

```cpp
atomic<int> ai0 = ATOMIC_VAR_INIT(0);
atomic<int> ai1(0);
```

## <a name="op_ty"></a>Atomik:: operator *Ty*

Şablon için belirtilen türün işleci\< *, atomik >* . Bu, depolanan değeri  **\*** alır.

```cpp
atomic<Ty>::operator Ty() const volatile noexcept;
atomic<Ty>::operator Ty() const noexcept;
```

### <a name="remarks"></a>Açıklamalar

Bu işleç, `memory_order_seq_cst` [memory_order](atomic-enums.md)uygular.

## <a name="op_eq"></a>Atomik:: operator =

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

## <a name="op_inc"></a>Atomik:: operator + +

Depolanan değeri arttırır. Yalnızca integral ve işaretçi Uzmanlıkları tarafından kullanılır.

```cpp
Ty atomic<Ty>::operator++(int) volatile noexcept;
Ty atomic<Ty>::operator++(int) noexcept;
Ty atomic<Ty>::operator++() volatile noexcept;
Ty atomic<Ty>::operator++() noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

İlk iki işleç, artan değeri döndürür; Son iki işleç değeri artmadan önce döndürür. İşleçler, `memory_order_seq_cst` [memory_order](atomic-enums.md)kullanır.

## <a name="op_add_eq"></a>Atomik:: operator + =

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

Bu işleç [memory_order](atomic-enums.md)kullanır `memory_order_seq_cst` .

## <a name="op_dec"></a>Atomik:: operator--

Depolanan değeri azaltır. Yalnızca integral ve işaretçi Uzmanlıkları tarafından kullanılır.

```cpp
Ty atomic<Ty>::operator--(int) volatile noexcept;
Ty atomic<Ty>::operator--(int) noexcept;
Ty atomic<Ty>::operator--() volatile noexcept;
Ty atomic<Ty>::operator--() noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

İlk iki operatör, azaltma değerini döndürür; Son iki operatör, azalmadan önce değeri döndürür. İşleçler, `memory_order_seq_cst` [memory_order](atomic-enums.md)kullanır.

## <a name="op_sub_eq"></a>Atomik:: operator-=

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

Bu işleç [memory_order](atomic-enums.md)kullanır `memory_order_seq_cst` .

## <a name="op_and_eq"></a>Atomik:: operator & =

Belirtilen bir değer ve  **\*bunun**depolanmış değeri için bit düzeyinde ve uygular. Yalnızca integral uzmanlıklarıyla kullanılır.

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

Bu işleç,  **\*bu** değerin bir bit düzeyinde ve *değeri* ve  **\*bu**değer içinde depolanan geçerli değeri ile değiştirmek için bir okuma-değiştirme-yazma işlemi gerçekleştirir. `memory_order_seq_cst` [memory_order](atomic-enums.md).

## <a name="op_or_eq"></a>Atomik:: operator&#124;=

Belirtilen bir değer üzerinde bir bit düzeyinde OR,  **\*bu**değerin saklı değerini uygular. Yalnızca integral uzmanlıklarıyla kullanılır.

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

Bu işleç,  **\*bu** değerin bir bit düzeyinde ya da bir *değere* ve  **\*bu**değer içinde depolanan geçerli değerle değiştirmek için bir okuma-değiştirme-yazma işlemi gerçekleştirir. `memory_order_seq_cst` [memory_order](atomic-enums.md) kısıtlamaları.

## <a name="op_xor_eq"></a>Atomik:: operator ^ =

Belirtilen bir değer ve  **\*bunun**depolanmış değeri üzerinde bir bit düzeyinde özel veya uygular. Yalnızca integral uzmanlıklarıyla kullanılır.

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

Bu işleç,  **\*bu** değerin saklı değerini bir bit düzeyinde dışlamalı veya *değeri* ve  **\*bu**değer içinde depolanan geçerli değeri ile değiştirmek için bir okuma-değiştirme-yazma işlemi gerçekleştirir. [memory_order kısıtlamaları](atomic-enums.md) . `memory_order_seq_cst`

## <a name="compare_exchange_strong"></a>Atomik:: compare_exchange_strong

Bu, bir atomik karşılaştırma ve değişim işlemi  **\*** gerçekleştirir.

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

Değer karşılaştırmasının sonucunu gösteren bir **bool** .

### <a name="remarks"></a>Açıklamalar

Bu atomik karşılaştırma ve değişim işlemi,  **\*bu** değerde depolanan değeri *Exp*ile karşılaştırır. Değerler eşitse, işlem, bir okuma-değiştirme-yazma işlemi kullanarak ve *Order1*tarafından belirtilen bellek sırası kısıtlamalarını uygulayarak,  **\*bu** *değerde* depolanan değeri değeriyle değiştirir. Değerler eşit değilse, işlem, *Exp* 'yi değiştirmek için  **\*bu** değeri kullanır ve *Order2*tarafından belirtilen bellek sırası kısıtlamalarını uygular.

İkincisine `memory_order` sahip olmayan aşırı yüklemeler, *Order1*değerini temel alan örtük bir *Order2* kullanır. `memory_order_acquire` *Order1* `memory_order_acq_rel`ise, *Order2* olur. `memory_order_relaxed` *Order1* `memory_order_release`ise, *Order2* olur. Diğer tüm durumlarda, *Order2* *Order1*'e eşittir.

İki `memory_order` parametre alan aşırı yüklemeler için *Order2* değeri ya `memory_order_release` `memory_order_acq_rel`da olmamalıdır ve *Order1*değerinden daha güçlü olmamalıdır.

## <a name="compare_exchange_weak"></a>Atomik:: compare_exchange_weak

**\*Bunun**üzerinde zayıf bir atomik karşılaştırma ve değişim işlemi gerçekleştirir.

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

Değer karşılaştırmasının sonucunu gösteren bir **bool** .

### <a name="remarks"></a>Açıklamalar

Bu atomik karşılaştırma ve değişim işlemi,  **\*bu** değerde depolanan değeri *Exp*ile karşılaştırır. Değerler eşitse, işlem, bir okuma-değiştirme-yazma işlemi kullanarak ve *Order1*tarafından belirtilen bellek sırası kısıtlamalarını uygulayarak,  **\*bu** *değerde* depolanan değeri değeriyle değiştirir. Değerler eşit değilse, işlem, *Exp* 'yi değiştirmek için  **\*bu** değeri kullanır ve *Order2*tarafından belirtilen bellek sırası kısıtlamalarını uygular.

Karşılaştırılan Değerler eşitse, zayıf bir atomik karşılaştırma ve değişim işlemi bir değişim gerçekleştirir. Değerler eşit değilse, işlemin bir Exchange gerçekleştirme garantisi yoktur.

İkincisine `memory_order` sahip olmayan aşırı yüklemeler, *Order1*değerini temel alan örtük bir *Order2* kullanır. `memory_order_acquire` *Order1* `memory_order_acq_rel`ise, *Order2* olur. `memory_order_relaxed` *Order1* `memory_order_release`ise, *Order2* olur. Diğer tüm durumlarda, *Order2* *Order1*'e eşittir.

İki `memory_order` parametre alan aşırı yüklemeler için *Order2* değeri ya `memory_order_release` `memory_order_acq_rel`da olmamalıdır ve *Order1*değerinden daha güçlü olmamalıdır.

## <a name="exchange"></a>Atomik:: Exchange

,  **\*Bunun**saklı değerini değiştirmek için belirtilen değeri kullanır.

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
A `memory_order`.

### <a name="return-value"></a>Dönüş Değeri

Exchange öncesinde  **\*bu** değerin depolanan değeri.

### <a name="remarks"></a>Açıklamalar

Bu işlem  **\*, içinde depolanan**değeri *Order*tarafından belirtilen bellek kısıtlamalarında değiştirmek için *değeri* kullanmak üzere bir okuma-değiştirme-yazma işlemi gerçekleştirir.

## <a name="fetch_add"></a>Atomik:: fetch_add

Bu değeri toplar ve ardından depolanan değere belirtilen değeri ekler.  **\***

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
A `memory_order`.

### <a name="return-value"></a>Dönüş Değeri

Eklenmesinden önce  **\*bu** değer içinde depolanan değeri içeren bir *Ty* nesnesi.

### <a name="remarks"></a>Açıklamalar

Yöntemi, **Bu, depolanan değere değeri otomatik olarak eklemek için bir okuma-değiştirme-yazma işlemi gerçekleştirir ve sırasıyla belirtilen \*** bellek kısıtlamalarını uygular. `fetch_add`

## <a name="fetch_and"></a>Atomik:: fetch_and

Bir değer ve bir değer üzerinde depolanan  **\*** bir değer ve var olan bir değer üzerinde bir bit düzeyinde ve uygular.

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
A `memory_order`.

### <a name="return-value"></a>Dönüş Değeri

Bit düzeyinde and sonucunu içeren bir *Ty* nesnesi.

### <a name="remarks"></a>Açıklamalar

Yöntemi,  **\***  **Bu\*** değerin depolanan değerini bir bit düzeyinde ve değerle ve bu değer içinde depolanan geçerli değeri, bellek içinde değiştirmek için bir okuma-değiştirme-yazma işlemi gerçekleştirir `fetch_and` *sırasıyla*belirtilen kısıtlamalar.

## <a name="fetch_or"></a>Atomik:: fetch_or

Bir bit düzeyinde veya bir değer üzerinde saklanan  **\*** mevcut bir değeri gerçekleştirir.

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
A `memory_order`.

### <a name="return-value"></a>Dönüş Değeri

Bit düzeyinde OR sonucunu içeren bir *Ty* nesnesi.

### <a name="remarks"></a>Açıklamalar

Yöntemi,  **\***  **Bu\*** değerin depolanan değerini bir bit düzeyinde veya değerle ve bu değer içinde depolanan geçerli değeri, bellek içinde değiştirmek için bir okuma-değiştirme-yazma işlemi gerçekleştirir `fetch_or` *sırasıyla*belirtilen kısıtlamalar.

## <a name="fetch_sub"></a>Atomik:: fetch_sub

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
A `memory_order`.

### <a name="return-value"></a>Dönüş Değeri

Çıkarma sonucunu içeren bir *Ty* nesnesi.

### <a name="remarks"></a>Açıklamalar

Yöntemi, düzen tarafından belirtilen bellek kısıtlamalarında,  **\*bu**değer içinde depolanan değerden *değeri* otomatik olarak çıkarmak için bir okuma-değiştirme-yazma işlemi gerçekleştirir. `fetch_sub`

## <a name="fetch_xor"></a>Atomik:: fetch_xor

Bir bit düzeyinde dışlamalı veya bir değer üzerinde saklanan  **\*** mevcut bir değeri gerçekleştirir.

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
A `memory_order`.

### <a name="return-value"></a>Dönüş Değeri

Bit düzeyinde dışlamalı veya sonucunu içeren bir *Ty* nesnesi.

### <a name="remarks"></a>Açıklamalar

Yöntemi,  **\***  **Bu\*** değerin depolanmış değerini bir bit düzeyinde dışlamalı veya değerden ve bu değer içinde depolanan geçerli değerle değiştirmek için bir okuma-değiştirme-yazma işlemi gerçekleştirir ve `fetch_xor` *Order*tarafından belirtilen bellek kısıtlamaları.

## <a name="is_lock_free"></a>Atomik:: is_lock_free

**Üzerinde\*atomik** işlemlerin boş bir kilit olup olmadığını belirtir.

```cpp
bool is_lock_free() const volatile noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

**\*bu** , üzerinde Atomik işlemler boş bir kilit ise true, aksi durumda false.

### <a name="remarks"></a>Açıklamalar

Bir atomik tür, bu tür üzerinde hiçbir Atomik işlem kilit kullanıyorsa boş bir kilit değildir.

## <a name="load"></a>Atomik:: Load

Belirtilen bellek kısıtlamalarında,  **\*bu**değer içinde depolanan değeri alır.

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
A `memory_order`. *Sıra* `memory_order_release` veya`memory_order_acq_rel`olmamalıdır.

### <a name="return-value"></a>Dönüş Değeri

**\*Bu**, alınan değeri içinde saklanır.

## <a name="store"></a>Atomik:: Store

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

Bu üye işlevi, ' deki *değeri* order `*this`tarafından belirtilen bellek kısıtlamaları dahilinde otomatik olarak depolar.

## <a name="see-also"></a>Ayrıca bkz.

[\<Atomik >](../standard-library/atomic.md)\
[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)
