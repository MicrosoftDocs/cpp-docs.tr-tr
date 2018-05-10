---
title: atomic yapısı | Microsoft Docs
ms.custom: ''
ms.date: 04/20/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- atomic/std::atomic
dev_langs:
- C++
ms.assetid: 261628ed-7049-41ac-99b9-cfe49f696b44
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 298fe2751cf25355e2075a2870c34bf17cedc222
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="atomic-structure"></a>atomic Yapısı

Türünde bir saklı değeri atomik işlemler gerçekleştiren bir nesneyi tanımlayan *Ty*.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
struct atomic;
```

## <a name="members"></a>Üyeler

|Üye|Açıklama|
|----------|-----------------|
|**Oluşturucusu**||
|[atomic](#atomic)|Atomik bir nesne oluşturur.|
|**İşleçler**||
|[atomic::operator Ty](#op_ty)|Okur ve saklanan değeri döndürür. ([atomic::load](#load))|
|[atomic::operator =](#op_eq)|Saklanan değeri değiştirmek için belirtilen değeri kullanır. ([atomic::store](#store))|
|[atomic::operator ++](#op_inc)|Depolanan değer artırır. Yalnızca integral ve işaretçi özelleştirmeleri tarafından kullanılır.|
|[atomic::operator +=](#op_add_eq)|Belirtilen bir değeri saklı değerine ekler. Yalnızca integral ve işaretçi özelleştirmeleri tarafından kullanılır.|
|[atomic::operator--](#op_dec)|Azaltır depolanan değer. Yalnızca integral ve işaretçi özelleştirmeleri tarafından kullanılır.|
|[atomic::operator-=](#op_sub_eq)|Saklanan değeri belirtilen değeri çıkarır. Yalnızca integral ve işaretçi özelleştirmeleri tarafından kullanılır.|
|[atomic::operator & =](#op_and_eq)|Bit tabanlı gerçekleştirir ve belirtilen bir değeri ile depolanan değer. Yalnızca tam sayı özelleştirmeleri tarafından kullanılır.|
|[atomic::operator&#124;=](#op_or_eq)|Bit tabanlı gerçekleştirir veya belirtilen değere ve depolanan değer. Yalnızca tam sayı özelleştirmeleri tarafından kullanılır.|
|[atomic::operator ^ =](#op_xor_eq)|Bit düzeyinde özel gerçekleştirir veya belirtilen değere ve depolanan değer. Yalnızca tam sayı özelleştirmeleri tarafından kullanılır.|
|**İşlevler**||
|[compare_exchange_strong](#compare_exchange_strong)|Gerçekleştiren bir *atomic_compare_and_exchange* işlemi **bu** ve sonucu döndürür.|
|[compare_exchange_weak](#compare_exchange_weak)|Gerçekleştiren bir *weak_atomic_compare_and_exchange* işlemi **bu** ve sonucu döndürür.|
|[fetch_add](#fetch_add)|Belirtilen bir değeri saklı değerine ekler.|
|[fetch_and](#fetch_and)|Bit tabanlı gerçekleştirir ve belirtilen bir değeri ile depolanan değer.|
|[fetch_or](#fetch_or)|Bit tabanlı gerçekleştirir veya belirtilen değere ve depolanan değer.|
|[fetch_sub](#fetch_sub)|Saklanan değeri belirtilen değeri çıkarır.|
|[fetch_xor](#fetch_xor)|Bit düzeyinde özel gerçekleştirir veya belirtilen değere ve depolanan değer.|
|[is_lock_free](#is_lock_free)|Belirtir olup olmadığını atomik işlemleri **bu** olan *kilidi serbest*. Atomik bir tür olduğundan *kilidi serbest* ilgili türdeki atomik bir işlem kilitleri kullanıyorsanız.|
|[Yükleme](#load)|Okur ve saklanan değeri döndürür.|
|[Depolama](#store)|Saklanan değeri değiştirmek için belirtilen değeri kullanır.|

## <a name="remarks"></a>Açıklamalar

Türü *Ty* olmalıdır *trivially copyable*. Diğer bir deyişle, kullanarak [memcpy](../c-runtime-library/reference/memcpy-wmemcpy.md) kendi bayt kopyalamak için geçerli bir üretmek gerekir *Ty* özgün nesne eşit karşılaştırır nesnesi. [Compare_exchange_weak](#compare_exchange_weak) ve [compare_exchange_strong](#compare_exchange_strong) üye işlevlerini kullanmak [memcmp](../c-runtime-library/reference/memcmp-wmemcmp.md) iki olup olmadığını belirlemek için *Ty* değerleri eşit olduğu. Bu işlevler kullanmaz bir *Ty*-tanımlı **işleç ==**. Üye işlevlerini **atomik** kullanmak **memcpy** türü değerleri kopyalamak için *Ty*.

Kısmi uzmanlığı ** atomik\<Ty * > **, tüm işaretçi türleri için bulunmaktadır. Yönetilen işaretçi değeri bir uzaklık eklenmesi veya bir uzaklığı çıkarma uzmanlık etkinleştirir. Aritmetik işlemler türünde bir bağımsız değişken Al **ptrdiff_t** ve boyutuna göre bu bağımsız değişken Ayarla *Ty* aritmetik sıradan adresi ile tutarlı olacak şekilde.

Dışında tam sayı her türü için bir uzmanlık var. **bool**. Her uzmanlık zengin bir atomik aritmetik ve mantıksal işlemleri için yöntemleri sağlar.

||||
|-|-|-|
|**atomik\<char >**|**atomik\<char imzalı >**|**atomik\<imzasız char >**|
|**atomik\<char16_t >**|**atomik\<char32_t >**|**atomik\<wchar_t >**|
|**atomik\<kısa >**|**atomik\<kısa imzasız >**|**atomik\<int >**|
|**atomik\<imzasız int >**|**atomik\<uzun >**|**atomik\<uzun imzasız >**|
|**atomik\<uzun uzun >**|**atomik\<uzun uzun imzasız >**|

Tam sayı özelleştirmeleri karşılık gelen öğesinden türetilen **atomic_integral** türleri. Örneğin, **atomik\<imzasız int >** türetildiği **atomic_uint**.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<atomik >

**Namespace:** std

## <a name="atomic"></a> atomic::atomic

Atomik bir nesne oluşturur.

```cpp
atomic();
atomic( const atomic& );
atomic( Ty Value ) noexcept;
```

### <a name="parameters"></a>Parametreler

*Değer*<br/>
Başlatma değeri.

### <a name="remarks"></a>Açıklamalar

Atomik nesneleri kopyalanamaz veya taşınamaz.

Atomik işlemlerinden olan nesneler\<*Ty*> yalnızca türünde bir bağımsız değişken alan Oluşturucu tarafından başlatılan *Ty* ve toplu başlatma kullanarak değil. Ancak, atomic_integral nesneleri yalnızca toplu başlatma kullanılarak başlatılabilir.

```cpp
atomic<int> ai0 = ATOMIC_VAR_INIT(0);
atomic<int> ai1(0);
```

## <a name="op_ty"></a> atomic::operator *Ty*

Şablon, atomik belirtilen tür için işleci\<*Ty*>. Saklı değerinde alır  **\*bu**.

```cpp
atomic<Ty>::operator Ty() const volatile noexcept;
atomic<Ty>::operator Ty() const noexcept;
```

### <a name="remarks"></a>Açıklamalar

Bu işleç geçerli **memory_order_seq_cst** [memory_order](atomic-enums.md).

## <a name="op_eq"></a> atomic::operator =

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

*Değer*<br/>
A *Ty* nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Döndürür *değeri*.

## <a name="op_inc"></a> atomic::operator ++

Depolanan değer artırır. Yalnızca integral ve işaretçi özelleştirmeleri tarafından kullanılır.

```cpp
Ty atomic<Ty>::operator++(int) volatile noexcept;
Ty atomic<Ty>::operator++(int) noexcept;
Ty atomic<Ty>::operator++() volatile noexcept;
Ty atomic<Ty>::operator++() noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

İlk iki işleç artırılır değerini döndürür; Son iki işleç artışı önce değerini döndürür. İşleçler kullanan **memory_order_seq_cst** [memory_order](atomic-enums.md).

## <a name="op_add_eq"></a> atomic::operator +=

Belirtilen bir değeri saklı değerine ekler. Yalnızca integral ve işaretçi özelleştirmeleri tarafından kullanılır.

```cpp
Ty atomic<Ty>::operator+=(
   Ty Value
) volatile noexcept;
Ty atomic<Ty>::operator+=(
   Ty Value
) noexcept;
```

### <a name="parameters"></a>Parametreler

*Değer*<br/>
Bir tamsayı veya işaretçi değeri.

### <a name="return-value"></a>Dönüş Değeri

A *Ty* eklenmesi sonucunu içeren nesne.

### <a name="remarks"></a>Açıklamalar

Bu işleç kullanan **memory_order_seq_cst** [memory_order](atomic-enums.md).

## <a name="op_dec"></a> atomic::operator--

Azaltır depolanan değer. Yalnızca integral ve işaretçi özelleştirmeleri tarafından kullanılır.

```cpp
Ty atomic<Ty>::operator--(int) volatile noexcept;
Ty atomic<Ty>::operator--(int) noexcept;
Ty atomic<Ty>::operator--() volatile noexcept;
Ty atomic<Ty>::operator--() noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

İlk iki işleç indirildiği değerini döndürür; Son iki işleç azaltma önce değerini döndürür. İşleçler kullanan **memory_order_seq_cst** [memory_order](atomic-enums.md).

## <a name="op_sub_eq"></a> atomic::operator-=

Saklanan değeri belirtilen değeri çıkarır. Yalnızca integral ve işaretçi özelleştirmeleri tarafından kullanılır.

```cpp
Ty atomic<Ty>::operator-=(
   Ty Value
) volatile noexcept;
Ty atomic<Ty>::operator-=(
   Ty Value
) noexcept;
```

### <a name="parameters"></a>Parametreler

*Değer*<br/>
Bir tamsayı veya işaretçi değeri.

### <a name="return-value"></a>Dönüş Değeri

A *Ty* çıkarma sonucunu içeren nesne.

### <a name="remarks"></a>Açıklamalar

Bu işleç kullanan **memory_order_seq_cst** [memory_order](atomic-enums.md).

## <a name="op_and_eq"></a> atomic::operator & =

Bit tabanlı gerçekleştirir ve belirtilen bir değeri ve üzerinde depolanan değeri  **\*bu**. Yalnızca tam sayı özelleştirmeleri tarafından kullanılır.

```cpp
atomic<Ty>::operator&= (
   Ty Value
) volatile noexcept;
atomic<Ty>::operator&= (
   Ty Value
) noexcept;
```

### <a name="parameters"></a>Parametreler

*Değer*<br/>
Türünde bir değer *Ty*.

### <a name="return-value"></a>Dönüş Değeri

Bit düzeyinde sonucunu ve.

### <a name="remarks"></a>Açıklamalar

Bu işleç saklı değerini değiştirmek için okuma-değiştirme-yazma işlemi gerçekleştirir  **\*bu** bit ile *değeri* ve içinde depolanan geçerli değeri  **\*bu**, kısıtlamaları dahilinde **memory_order_seq_cst** [memory_order](atomic-enums.md).

## <a name="op_or_eq"></a> atomic::operator&#124;=

Bit tabanlı gerçekleştirir veya belirtilen değere ve üzerinde depolanan değeri  **\*bu**. Yalnızca tam sayı özelleştirmeleri tarafından kullanılır.

```cpp
atomic<Ty>::operator|= (
   Ty Value
) volatile noexcept;
atomic<Ty>::operator|= (
   Ty Value
) noexcept;
```

### <a name="parameters"></a>Parametreler

*Değer*<br/>
Türünde bir değer *Ty*.

### <a name="return-value"></a>Dönüş Değeri

Bit düzeyinde sonucu veya.

### <a name="remarks"></a>Açıklamalar

Bu işleç saklı değerini değiştirmek için okuma-değiştirme-yazma işlemi gerçekleştirir  **\*bu** bit veya, *değeri* ve içinde depolanan geçerli değeri  **\*bu**, kısıtlamaları dahilinde **memory_order_seq_cst** [memory_order](atomic-enums.md) kısıtlamaları.

## <a name="op_xor_eq"></a> atomic::operator ^ =

Bit düzeyinde özel gerçekleştirir veya belirtilen değere ve üzerinde depolanan değeri  **\*bu**. Yalnızca tam sayı özelleştirmeleri tarafından kullanılır.

```cpp
atomic<Ty>::operator^= (
   Ty Value
) volatile noexcept;
atomic<Ty>::operator^= (
   Ty Value
) noexcept;
```

### <a name="parameters"></a>Parametreler

*Değer*<br/>
Türünde bir değer *Ty*.

### <a name="return-value"></a>Dönüş Değeri

Bit düzeyinde özel sonucunu veya.

### <a name="remarks"></a>Açıklamalar

Bu işleç saklı değerini değiştirmek için okuma-değiştirme-yazma işlemi gerçekleştirir  **\*bu** bit düzeyinde özel veya, *değeri* ve içinde depolanan geçerli değeri  **\*bu**, kısıtlamaları dahilinde **memory_order_seq_cst** [memory_order](atomic-enums.md) kısıtlamaları.

## <a name="compare_exchange_strong"></a> atomic::compare_exchange_strong

Atomik Karşılaştır ve exchange işlemi gerçekleştirir.  **\*bu**.

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

*exp*<br/>
Türünde bir değer *Ty*.

*Değer*<br/>
Türünde bir değer *Ty*.

*Order1*<br/>
İlk **memory_order** bağımsız değişkeni.

*Order2*<br/>
İkinci **memory_order** bağımsız değişkeni.

### <a name="return-value"></a>Dönüş Değeri

A **bool** değer karşılaştırması sonucunu gösterir.

### <a name="remarks"></a>Açıklamalar

Bu atomik Karşılaştır ve exchange işlem içinde saklanan değerle karşılaştırır  **\*bu** ile *Exp*. Değerlerin eşit olup olmadığını işlemi depolanan değeri değiştirir  **\*bu** ile *değeri* okuma-değiştirme-yazma işlemini kullanarak ve olan bellek sipariş kısıtlamalarını uygulama tarafından belirtilen *Order1*. Değerler eşit değilse, işlem depolanan değeri kullanan  **\*bu** değiştirmek için *Exp* ve tarafından belirtilen bellek sipariş kısıtlamaları geçerlidir *Order2* .

İkinci bir olmayan aşırı **memory_order** örtülü kullanmak *Order2* değeri temel alarak *Order1*. Varsa *Order1* olan **memory_order_acq_rel**, *Order2* olan **memory_order_acquire**. Varsa *Order1* olan **memory_order_release**, *Order2* olan **memory_order_relaxed**. Diğer durumlarda *Order2* eşittir *Order1*.

İki ele aşırı yüklemeleri için **memory_order** parametreleri, değeri *Order2* olmamalıdır **memory_order_release** veya **memory_order_acq_rel**, değerinden daha güçlü olamaz *Order1*.

## <a name="compare_exchange_weak"></a> atomic::compare_exchange_weak

Zayıf bir atomik Karşılaştır ve exchange işlemi gerçekleştirir.  **\*bu**.

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

*exp*<br/>
Türünde bir değer *Ty*.

*Değer*<br/>
Türünde bir değer *Ty*.

*Order1*<br/>
İlk **memory_order** bağımsız değişkeni.

*Order2*<br/>
İkinci **memory_order** bağımsız değişkeni.

### <a name="return-value"></a>Dönüş Değeri

A **bool** değer karşılaştırması sonucunu gösterir.

### <a name="remarks"></a>Açıklamalar

Bu atomik Karşılaştır ve exchange işlem içinde saklanan değerle karşılaştırır  **\*bu** ile *Exp*. Değerlerin eşit olup olmadığını işlemi depolanan değeri değiştirir  **\*bu** ile*değeri* okuma-değiştirme-yazma işlemini kullanarak ve olan bellek sipariş kısıtlamalarını uygulama tarafından belirtilen *Order1*. Değerler eşit değilse, işlem depolanan değeri kullanan  **\*bu** değiştirmek için *Exp* ve tarafından belirtilen bellek sipariş kısıtlamaları geçerlidir *Order2* .

Atomik bir zayıf karşılaştırın ve Karşılaştırılan değer eşitse, bir exchange exchange işlemi gerçekleştirir. Değerlerin eşit değilse, işlemi bir exchange gerçekleştirmek için kesin değildir.

İkinci bir olmayan aşırı **memory_order** örtülü kullanmak *Order2* değeri temel alarak *Order1*. Varsa *Order1* olan **memory_order_acq_rel**, *Order2* olan **memory_order_acquire**. Varsa *Order1* olan **memory_order_release**, *Order2* olan **memory_order_relaxed**. Diğer durumlarda *Order2* eşittir *Order1*.

İki ele aşırı yüklemeleri için **memory_order** parametreleri, değeri *Order2* olmamalıdır **memory_order_release** veya **memory_order_acq_rel**, değerinden daha güçlü olamaz *Order1*.

## <a name="exchange"></a> atomic::Exchange

Saklı değerini değiştirmek için belirtilen değer kullanan  **\*bu**.

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

*Değer*<br/>
Türünde bir değer *Ty*.

*Sırası*<br/>
A **memory_order**.

### <a name="return-value"></a>Dönüş Değeri

Saklı değeri  **\*bu** exchange önce.

### <a name="remarks"></a>Açıklamalar

Bu işlemi kullanmak için okuma-değiştirme-yazma işlemi gerçekleştirir *değeri* depolanan değeri değiştirmek için  **\*bu**, tarafından belirtilen bellek kısıtlamaları içinde  *Sipariş*.

## <a name="fetch_add"></a> atomic::fetch_add

İçinde depolanan değeri getirir  **\*bu**ve ardından belirli bir değeri saklı değerine ekler.

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

*Değer*<br/>
Türünde bir değer *Ty*.

*Sırası*<br/>
A **memory_order**.

### <a name="return-value"></a>Dönüş Değeri

A *Ty* depolanan değeri içeren nesne  **\*bu** eklenmesi önce.

### <a name="remarks"></a>Açıklamalar

**Fetch_add** yöntemi otomatik olarak eklemek için okuma-değiştirme-yazma işlemi gerçekleştirir *değeri* saklı değerine  **\*bu**ve bellek uygular tarafından belirlenen kısıtlamalar *sipariş*.

## <a name="fetch_and"></a> atomic::fetch_and

Bit tabanlı gerçekleştirir ve üzerinde bir ve depolanan mevcut değeri  **\*bu**.

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

*Değer*<br/>
Türünde bir değer *Ty*.

*Sırası*<br/>
A **memory_order**.

### <a name="return-value"></a>Dönüş Değeri

A *Ty* bitwise sonucunu içeren nesne ve.

### <a name="remarks"></a>Açıklamalar

**Fetch_and** yöntemi saklı değerini değiştirmek için okuma-değiştirme-yazma işlemi gerçekleştirir  **\*bu** bit ile *değeri* ve geçerli depolanan değer  **\*bu**, tarafından belirtilen bellek kısıtlamaları içinde *sipariş*.

## <a name="fetch_or"></a> atomic::fetch_or

Bit tabanlı gerçekleştirir veya üzerinde bir ve depolanan mevcut değeri  **\*bu**.

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

*Değer*<br/>
Türünde bir değer *Ty*.

*Sırası*<br/>
A **memory_order**.

### <a name="return-value"></a>Dönüş Değeri

A *Ty* bitwise sonucunu içeren nesne veya.

### <a name="remarks"></a>Açıklamalar

**Fetch_or** yöntemi saklı değerini değiştirmek için okuma-değiştirme-yazma işlemi gerçekleştirir  **\*bu** bit veya, *değeri* geçerli değeri içinde depolanan  **\*bu**, tarafından belirtilen bellek kısıtlamaları içinde *sipariş*.

## <a name="fetch_sub"></a> atomic::fetch_sub

Saklanan değeri belirtilen değeri çıkarır.

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

*Değer*<br/>
Türünde bir değer *Ty*.

*Sırası*<br/>
A **memory_order**.

### <a name="return-value"></a>Dönüş Değeri

A *Ty* çıkarma sonucunu içeren nesne.

### <a name="remarks"></a>Açıklamalar

**Fetch_sub** yöntemi otomatik olarak çıkarmak için okuma-değiştirme-yazma işlemi gerçekleştirir *değeri* saklı değerinden  **\*bu**, bellek içinde tarafından belirlenen kısıtlamalar *sipariş*.

## <a name="fetch_xor"></a> atomic::fetch_xor

Bit düzeyinde özel gerçekleştirir veya üzerinde bir ve depolanan mevcut değeri  **\*bu**.

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

*Değer*<br/>
Türünde bir değer *Ty*.

*Sırası*<br/>
A **memory_order**.

### <a name="return-value"></a>Dönüş Değeri

A *Ty* bit düzeyinde özel sonucunu içeren nesne veya.

### <a name="remarks"></a>Açıklamalar

**Fetch_xor** yöntemi saklı değerini değiştirmek için okuma-değiştirme-yazma işlemi gerçekleştirir  **\*bu** bit düzeyinde özel veya, *değeri* ve içinde depolanan geçerli değeri  **\*bu**ve tarafından belirtilen bellek kısıtlamaları geçerlidir *sipariş*.

## <a name="is_lock_free"></a> atomic::is_lock_free

Belirtir olup olmadığını atomik işlemleri  **\*bu** kilidi serbest şunlardır.

```cpp
bool is_lock_free() const volatile noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

TRUE atomik işlemleri  **\*bu** olan kilit boş, aksi takdirde false.

### <a name="remarks"></a>Açıklamalar

Bu tür hiçbir atomik işlemleri kilitleri kullanıyorsanız bir atomik kilidi serbest türüdür.

## <a name="load"></a> atomic::Load

Saklı değerinde alır  **\*bu**, belirtilen bellek kısıtlamaları içinde.

```cpp
Ty atomic::load(
   memory_order Order = memory_order_seq_cst
) const volatile noexcept;
Ty atomic::load(
   memory_order Order = memory_order_seq_cst
) const noexcept;
```

### <a name="parameters"></a>Parametreler

*Sırası*<br/>
A **memory_order**. *Sipariş* olmamalıdır **memory_order_release** veya **memory_order_acq_rel**.

### <a name="return-value"></a>Dönüş Değeri

Depolanan alınan değerin  **\*bu**.

## <a name="store"></a> atomic::store

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

*Değer*<br/>
A *Ty* nesnesi.

*Sırası*<br/>
A **memory_order** kısıtlaması.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi otomatik olarak depolar *değeri* içinde `*this`, tarafından belirtilen bellek kısıtlamaları içinde *sipariş*.

## <a name="see-also"></a>Ayrıca bkz.

[\<atomik >](../standard-library/atomic.md)<br/>
[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
