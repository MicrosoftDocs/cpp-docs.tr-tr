---
title: atomic Yapısı
ms.date: 04/20/2018
f1_keywords:
- atomic/std::atomic
ms.assetid: 261628ed-7049-41ac-99b9-cfe49f696b44
ms.openlocfilehash: 258812f033d34f040d96847581d6f51692a933b6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50590066"
---
# <a name="atomic-structure"></a>atomic Yapısı

Depolanan değer türünde atomik işlemleri gerçekleştiren bir nesneyi tanımlayan *Ty*.

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
|[atomic::operator Ty](#op_ty)|Okur ve depolanan değeri döndürür. ([atomic::load](#load))|
|[atomic::operator =](#op_eq)|Belirtilen bir değeri depolanan değeri değiştirmek için kullanır. ([atomic::store](#store))|
|[atomic::operator ++](#op_inc)|Depolanan değeri artırır. Yalnızca integral ve işaretçi uzmanlıklarıyla kullanılır.|
|[atomic::operator +=](#op_add_eq)|Depolanan değere belirtilen bir değer ekler. Yalnızca integral ve işaretçi uzmanlıklarıyla kullanılır.|
|[atomic::operator--](#op_dec)|Azaltır depolanan değeri. Yalnızca integral ve işaretçi uzmanlıklarıyla kullanılır.|
|[atomic::operator-=](#op_sub_eq)|Belirtilen bir değeri depolanan değerden çıkarır. Yalnızca integral ve işaretçi uzmanlıklarıyla kullanılır.|
|[atomic::operator & =](#op_and_eq)|Bit düzeyinde gerçekleştirir ve belirtilen değer ve depolanan değeri. Yalnızca integral uzmanlıklarıyla kullanılır.|
|[atomic::operator&#124;=](#op_or_eq)|Bit düzeyinde gerçekleştirir veya belirtilen değer ve depolanan değeri. Yalnızca integral uzmanlıklarıyla kullanılır.|
|[atomic::operator ^ =](#op_xor_eq)|Bit düzeyinde özel gerçekleştirir veya belirtilen değer ve depolanan değeri. Yalnızca integral uzmanlıklarıyla kullanılır.|
|**İşlevler**||
|[compare_exchange_strong](#compare_exchange_strong)|Gerçekleştiren bir *atomic_compare_and_exchange* işlemi **bu** ve sonucu döndürür.|
|[compare_exchange_weak](#compare_exchange_weak)|Gerçekleştiren bir *weak_atomic_compare_and_exchange* işlemi **bu** ve sonucu döndürür.|
|[fetch_add](#fetch_add)|Depolanan değere belirtilen bir değer ekler.|
|[fetch_and](#fetch_and)|Bit düzeyinde gerçekleştirir ve belirtilen değer ve depolanan değeri.|
|[fetch_or](#fetch_or)|Bit düzeyinde gerçekleştirir veya belirtilen değer ve depolanan değeri.|
|[fetch_sub](#fetch_sub)|Belirtilen bir değeri depolanan değerden çıkarır.|
|[fetch_xor](#fetch_xor)|Bit düzeyinde özel gerçekleştirir veya belirtilen değer ve depolanan değeri.|
|[is_lock_free](#is_lock_free)|Belirtir olup olmadığını üzerinde yapılan atomik işlemlerin **bu** olan *kilitsiz*. Atomik tür *kilitsiz* hiçbir bu türdeki atomik işlemler kilit kullanmıyorsa.|
|[Yükleme](#load)|Okur ve depolanan değeri döndürür.|
|[Store](#store)|Belirtilen bir değeri depolanan değeri değiştirmek için kullanır.|

## <a name="remarks"></a>Açıklamalar

Türü *Ty* olmalıdır *artık önemsiz olarak kopyalanabilir*. Diğer bir deyişle, kullanarak [memcpy](../c-runtime-library/reference/memcpy-wmemcpy.md) baytlarını kopyalamak için geçerli bir üretmelidir *Ty* özgün nesneye eşitse karşılaştıran bir nesne. [Compare_exchange_weak](#compare_exchange_weak) ve [compare_exchange_strong](#compare_exchange_strong) üye işlevleri kullanmak [memcmp](../c-runtime-library/reference/memcmp-wmemcmp.md) iki olup olmadığını belirlemek için *Ty* değerleri eşit olur. Bu işlevler kullanmaz bir *Ty*-tanımlanan `operator==`. Üye işlevlerinin `atomic` kullanın `memcpy` türünün değerlerini kopyalamak için *Ty*.

Kısmi özelleştirmede **atomik\<Ty \* >** , tüm işaretçi türlerine ilişkin bulunmaktadır. Uzmanlık, Yönetilen işaretçi değerine bir ofsetin eklenmesini veya ondan bir ofsetin çıkarma sağlar. Bağımsız değişken türü aritmetik işlemler ele `ptrdiff_t` ve bu bağımsız değişken boyutuna göre ayarlayın *Ty* normal adres aritmetiğiyle tutarlı olmak.

Dışında her tamsayı türü için bir özelleştirmesi var **bool**. Her özelleştirme yöntemleri atomik aritmetik ve mantıksal işlemler için zengin bir özellik kümesi sağlar.

||||
|-|-|-|
|**atomik\<char >**|**atomik\<signed char >**|**atomik\<işaretsiz karakter >**|
|**atomik\<char16_t >**|**atomik\<char32_t >**|**atomik\<wchar_t >**|
|**atomik\<kısa >**|**atomik\<işaretsiz >**|**atomik\<int >**|
|**atomik\<işaretsiz int >**|**atomik\<uzun >**|**atomik\<işaretsiz uzun >**|
|**atomik\<uzun uzun >**|**atomik\<işaretsiz long long >**|

Uzmanlıkları ilgili türetilen `atomic_integral` türleri. Örneğin, **atomik\<işaretsiz int >** türetilir `atomic_uint`.

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

Atomik nesneler kopyalanamaz veya taşınamaz.

Atomik örneklemeleri olan nesneler\<*Ty*> yalnızca türünde bir bağımsız değişken alan Oluşturucu tarafından başlatılabilir *Ty* ve toplama başlatma kullanılarak başlatılamaz. Ancak, atomic_integral nesneleri yalnızca toplama başlatma kullanılarak başlatılabilir.

```cpp
atomic<int> ai0 = ATOMIC_VAR_INIT(0);
atomic<int> ai1(0);
```

## <a name="op_ty"></a> atomic::operator *Ty*

Belirtilen şablonu, atomik tür için işleç\<*Ty*>. Depolanan değeri alır  **\*bu**.

```cpp
atomic<Ty>::operator Ty() const volatile noexcept;
atomic<Ty>::operator Ty() const noexcept;
```

### <a name="remarks"></a>Açıklamalar

Bu işleç geçerli `memory_order_seq_cst` [memory_order](atomic-enums.md).

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
A *Ty* nesne.

### <a name="return-value"></a>Dönüş Değeri

Döndürür *değer*.

## <a name="op_inc"></a> atomic::operator ++

Depolanan değeri artırır. Yalnızca integral ve işaretçi uzmanlıklarıyla kullanılır.

```cpp
Ty atomic<Ty>::operator++(int) volatile noexcept;
Ty atomic<Ty>::operator++(int) noexcept;
Ty atomic<Ty>::operator++() volatile noexcept;
Ty atomic<Ty>::operator++() noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

İlk iki işleç artan bir değer döndürür; Son iki işleçleri, artırma önce değerini döndürür. İşleçleri kullanan `memory_order_seq_cst` [memory_order](atomic-enums.md).

## <a name="op_add_eq"></a> atomic::operator +=

Depolanan değere belirtilen bir değer ekler. Yalnızca integral ve işaretçi uzmanlıklarıyla kullanılır.

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
Bir integral veya işaretçi değeri.

### <a name="return-value"></a>Dönüş Değeri

A *Ty* toplamın sonucunu içeren nesne.

### <a name="remarks"></a>Açıklamalar

Bu işleç kullanır `memory_order_seq_cst` [memory_order](atomic-enums.md).

## <a name="op_dec"></a> atomic::operator--

Azaltır depolanan değeri. Yalnızca integral ve işaretçi uzmanlıklarıyla kullanılır.

```cpp
Ty atomic<Ty>::operator--(int) volatile noexcept;
Ty atomic<Ty>::operator--(int) noexcept;
Ty atomic<Ty>::operator--() volatile noexcept;
Ty atomic<Ty>::operator--() noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

İlk iki işleç indirildiği değerini döndürür; Son iki işleç azaltma önce değerini döndürür. İşleçleri kullanan `memory_order_seq_cst` [memory_order](atomic-enums.md).

## <a name="op_sub_eq"></a> atomic::operator-=

Belirtilen bir değeri depolanan değerden çıkarır. Yalnızca integral ve işaretçi uzmanlıklarıyla kullanılır.

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
Bir integral veya işaretçi değeri.

### <a name="return-value"></a>Dönüş Değeri

A *Ty* çıkarmanın sonucunu içeren nesne.

### <a name="remarks"></a>Açıklamalar

Bu işleç kullanır `memory_order_seq_cst` [memory_order](atomic-enums.md).

## <a name="op_and_eq"></a> atomic::operator & =

Bit düzeyinde gerçekleştirir ve üzerinde belirtilen değer ve depolanan değeri  **\*bu**. Yalnızca integral uzmanlıklarıyla kullanılır.

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

Bit düzeyi sonucu ve.

### <a name="remarks"></a>Açıklamalar

Bu işleç, depolanan değeri değiştirmek için bir okuma-değiştirme-yazma işlemi gerçekleştirir  **\*bu** bit düzeyiyle ve, *değer* içinde depolanmış geçerli değerle  **\*bu**, kısıtlamaları dahilinde `memory_order_seq_cst` [memory_order](atomic-enums.md).

## <a name="op_or_eq"></a> atomic::operator&#124;=

Bit düzeyinde gerçekleştirir veya üzerinde belirtilen değer ve depolanan değeri  **\*bu**. Yalnızca integral uzmanlıklarıyla kullanılır.

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

Bit düzeyi sonucu veya.

### <a name="remarks"></a>Açıklamalar

Bu işleç, depolanan değeri değiştirmek için bir okuma-değiştirme-yazma işlemi gerçekleştirir  **\*bu** bit düzeyinde veya, *değer* içinde depolanmış geçerli değerle  **\*bu**, kısıtlamaları dahilinde `memory_order_seq_cst` [memory_order](atomic-enums.md) kısıtlamaları.

## <a name="op_xor_eq"></a> atomic::operator ^ =

Bit düzeyinde özel gerçekleştirir veya üzerinde belirtilen değer ve depolanan değeri  **\*bu**. Yalnızca integral uzmanlıklarıyla kullanılır.

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

Bu işleç, depolanan değeri değiştirmek için bir okuma-değiştirme-yazma işlemi gerçekleştirir  **\*bu** bit düzeyinde özel veya, *değer* içinde depolanmış geçerli değerle  **\*bu**, kısıtlamaları dahilinde `memory_order_seq_cst` [memory_order](atomic-enums.md) kısıtlamaları.

## <a name="compare_exchange_strong"></a> atomic::compare_exchange_strong

Atomik karşılaştırma ve değişim işlemi gerçekleştirir  **\*bu**.

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
İlk `memory_order` bağımsız değişken.

*Order2*<br/>
İkinci `memory_order` bağımsız değişken.

### <a name="return-value"></a>Dönüş Değeri

A **bool** değeri Karşılaştırmanın sonucu gösterir.

### <a name="remarks"></a>Açıklamalar

Bu atomik karşılaştırma ve değişim işlemi içinde depolanan değeri karşılaştırır  **\*bu** ile *Exp*. Değerler eşitse, işlem içinde depolanmış değerle değiştirir.  **\*bu** ile *değer* bir okuma-değiştirme-yazma işlemini kullanarak ve olan bellek sırası kısıtlamalarını uygulayarak tarafından belirtilen *Order1*. Değerler eşit değilse, işlem içinde depolanan değeri kullanır.  **\*bu** değiştirilecek *Exp* ve tarafından belirtilen bellek sırası kısıtlamalarını uygular *Order2* .

İkinci olmayan aşırı `memory_order` örtük kullanın *Order2* değerini temel alarak *Order1*. Varsa *Order1* olduğu `memory_order_acq_rel`, *Order2* olduğu `memory_order_acquire`. Varsa *Order1* olduğu `memory_order_release`, *Order2* olduğu `memory_order_relaxed`. Diğer tüm durumlarda *Order2* eşittir *Order1*.

İki alan aşırı yüklemeler için `memory_order` parametreler, değerini *Order2* olmamalıdır `memory_order_release` veya `memory_order_acq_rel`ve değerinden daha güçlü olmamalıdır *Order1*.

## <a name="compare_exchange_weak"></a> atomic::compare_exchange_weak

Bir zayıf atomik karşılaştırma ve değişim işlemi gerçekleştirir  **\*bu**.

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
İlk `memory_order` bağımsız değişken.

*Order2*<br/>
İkinci `memory_order` bağımsız değişken.

### <a name="return-value"></a>Dönüş Değeri

A **bool** değeri Karşılaştırmanın sonucu gösterir.

### <a name="remarks"></a>Açıklamalar

Bu atomik karşılaştırma ve değişim işlemi içinde depolanan değeri karşılaştırır  **\*bu** ile *Exp*. Değerler eşitse, işlem içinde depolanmış değerle değiştirir.  **\*bu** ile*değer* bir okuma-değiştirme-yazma işlemini kullanarak ve olan bellek sırası kısıtlamalarını uygulayarak tarafından belirtilen *Order1*. Değerler eşit değilse, işlem içinde depolanan değeri kullanır.  **\*bu** değiştirilecek *Exp* ve tarafından belirtilen bellek sırası kısıtlamalarını uygular *Order2* .

Bir zayıf atomik karşılaştırma ve Karşılaştırılan değerler eşitse, bir exchange değişim işlemi gerçekleştirir. Değerler eşit değilse işlem bir değiş tokuş için garanti edilmez.

İkinci olmayan aşırı `memory_order` örtük kullanın *Order2* değerini temel alarak *Order1*. Varsa *Order1* olduğu `memory_order_acq_rel`, *Order2* olduğu `memory_order_acquire`. Varsa *Order1* olduğu `memory_order_release`, *Order2* olduğu `memory_order_relaxed`. Diğer tüm durumlarda *Order2* eşittir *Order1*.

İki alan aşırı yüklemeler için `memory_order` parametreler, değerini *Order2* olmamalıdır `memory_order_release` veya `memory_order_acq_rel`ve değerinden daha güçlü olmamalıdır *Order1*.

## <a name="exchange"></a> atomic::Exchange

Belirtilen bir değeri depolanan değeri değiştirmek için kullandığı  **\*bu**.

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
A `memory_order`.

### <a name="return-value"></a>Dönüş Değeri

Depolanan değeri  **\*bu** exchange önce.

### <a name="remarks"></a>Açıklamalar

Bu işlemi kullanmak için bir okuma-değiştirme-yazma işlemi gerçekleştirir *değer* içinde depolanmış değerle değiştirmek için  **\*bu**, tarafından belirtilen bellek kısıtlamaları dahilinde  *Sipariş*.

## <a name="fetch_add"></a> atomic::fetch_add

İçinde depolanan değeri getirir  **\*bu**ve ardından depolanan değere belirtilen bir değer ekler.

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
A `memory_order`.

### <a name="return-value"></a>Dönüş Değeri

A *Ty* içinde depolanan değeri içeren nesne  **\*bu** eklenmesi önce.

### <a name="remarks"></a>Açıklamalar

`fetch_add` Yöntemi otomatik olarak eklemek için okuma-değiştirme-yazma işlemi gerçekleştirir *değer* içinde depolanmış değere  **\*bu**ve tarafından belirtilen bellek kısıtlamaları geçerlidir *Sipariş*.

## <a name="fetch_and"></a> atomic::fetch_and

Bit düzeyinde gerçekleştirir ve üzerinde bir değer ve depolanan varolan değeri  **\*bu**.

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
A `memory_order`.

### <a name="return-value"></a>Dönüş Değeri

A *Ty* bit düzeyi sonucu içeren nesne ve.

### <a name="remarks"></a>Açıklamalar

`fetch_and` Yöntemi depolanan değeri değiştirmek için okuma-değiştirme-yazma işlemi gerçekleştirir  **\*bu** bit düzeyiyle ve, *değer* içindedepolanmışgeçerlideğerle **\*bu**, tarafından belirtilen bellek kısıtlamaları dahilinde *sipariş*.

## <a name="fetch_or"></a> atomic::fetch_or

Bit düzeyinde gerçekleştirir veya üzerinde bir değer ve depolanan varolan değeri  **\*bu**.

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
A `memory_order`.

### <a name="return-value"></a>Dönüş Değeri

A *Ty* bit düzeyi sonucu içeren nesne veya.

### <a name="remarks"></a>Açıklamalar

`fetch_or` Yöntemi depolanan değeri değiştirmek için okuma-değiştirme-yazma işlemi gerçekleştirir  **\*bu** bit düzeyinde veya, *değer* içindedepolanmışgeçerlideğerle **\*bu**, tarafından belirtilen bellek kısıtlamaları dahilinde *sipariş*.

## <a name="fetch_sub"></a> atomic::fetch_sub

Belirtilen bir değeri depolanan değerden çıkarır.

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
A `memory_order`.

### <a name="return-value"></a>Dönüş Değeri

A *Ty* çıkarmanın sonucunu içeren nesne.

### <a name="remarks"></a>Açıklamalar

`fetch_sub` Yöntemi atomik çıkartmak üzere bir okuma-değiştirme-yazma işlemi gerçekleştiren *değer* içinde depolanmış değerden  **\*bu**, tarafından belirtilen bellek kısıtlamaları dahilinde *Sipariş*.

## <a name="fetch_xor"></a> atomic::fetch_xor

Bit düzeyinde özel gerçekleştirir veya üzerinde bir değer ve depolanan varolan değeri  **\*bu**.

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
A `memory_order`.

### <a name="return-value"></a>Dönüş Değeri

A *Ty* bit düzeyinde özel sonucunu içeren bir nesne veya.

### <a name="remarks"></a>Açıklamalar

`fetch_xor` Yöntemi depolanan değeri değiştirmek için okuma-değiştirme-yazma işlemi gerçekleştirir  **\*bu** bit düzeyinde özel veya, *değer* içinde depolanmış geçerli değerle  **\*bu**ve tarafından belirtilen bellek kısıtlamaları geçerlidir *sipariş*.

## <a name="is_lock_free"></a> atomic::is_lock_free

Belirtir olup olmadığını üzerinde yapılan atomik işlemlerin  **\*bu** kilitsiz olan.

```cpp
bool is_lock_free() const volatile noexcept;
```

### <a name="return-value"></a>Dönüş Değeri

TRUE atomik işlemler  **\*bu** olan kilidi serbest; Aksi takdirde false.

### <a name="remarks"></a>Açıklamalar

Hiçbir bu türdeki atomik işlemler kilit kullanmıyorsa atomik kilitsiz türüdür.

## <a name="load"></a> atomic::Load

Depolanan değeri alır  **\*bu**, belirtilen bellek kısıtlamaları dahilinde.

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
A `memory_order`. *Sipariş* olmamalıdır `memory_order_release` veya `memory_order_acq_rel`.

### <a name="return-value"></a>Dönüş Değeri

Depolanan alınan değeri  **\*bu**.

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
A *Ty* nesne.

*Sırası*<br/>
A `memory_order` kısıtlaması.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi atomik olarak depolar *değer* içinde `*this`, tarafından belirtilen bellek kısıtlamaları dahilinde *sipariş*.

## <a name="see-also"></a>Ayrıca bkz.

[\<atomik >](../standard-library/atomic.md)<br/>
[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
