---
title: '&lt;Atomik&gt; işlevler'
ms.date: 07/11/2018
f1_keywords:
- atomic/std::atomic_compare_exchange_strong
- atomic/std::atomic_compare_exchange_strong_explicit
- atomic/std::atomic_compare_exchange_weak
- atomic/std::atomic_compare_exchange_weak_explicit
- atomic/std::atomic_exchange
- atomic/std::atomic_exchange_explicit
- atomic/std::atomic_fetch_add
- atomic/std::atomic_fetch_add_explicit
- atomic/std::atomic_fetch_and
- atomic/std::atomic_fetch_and_explicit
- atomic/std::atomic_fetch_or
- atomic/std::atomic_fetch_or_explicit
- atomic/std::atomic_fetch_sub
- atomic/std::atomic_fetch_sub_explicit
- atomic/std::atomic_fetch_xor
- atomic/std::atomic_fetch_xor_explicit
- atomic/std::atomic_flag_clear
- atomic/std::atomic_flag_clear_explicit
- atomic/std::atomic_flag_test_and_set
- atomic/std::atomic_flag_test_and_set_explicit
- atomic/std::atomic_init
- atomic/std::atomic_is_lock_free
- atomic/std::atomic_load
- atomic/std::atomic_load_explicit
- atomic/std::atomic_signal_fence
- atomic/std::atomic_store
- atomic/std::atomic_store_explicit
- atomic/std::atomic_thread_fence
- atomic/std::kill_dependency
ms.assetid: 5c53b4f8-6ff5-47d7-beb2-2d6ee3c6ea89
helpviewer_keywords:
- std::atomic_compare_exchange_strong [C++]
- std::atomic_compare_exchange_strong_explicit [C++]
- std::atomic_compare_exchange_weak [C++]
- std::atomic_compare_exchange_weak_explicit [C++]
- std::atomic_exchange [C++]
- std::atomic_exchange_explicit [C++]
- std::atomic_fetch_add [C++]
- std::atomic_fetch_add_explicit [C++]
- std::atomic_fetch_and [C++]
- std::atomic_fetch_and_explicit [C++]
- std::atomic_fetch_or [C++]
- std::atomic_fetch_or_explicit [C++]
- std::atomic_fetch_sub [C++]
- std::atomic_fetch_sub_explicit [C++]
- std::atomic_fetch_xor [C++]
- std::atomic_fetch_xor_explicit [C++]
- std::atomic_flag_clear [C++]
- std::atomic_flag_clear_explicit [C++]
- std::atomic_flag_test_and_set [C++]
- std::atomic_flag_test_and_set_explicit [C++]
- std::atomic_init [C++]
- std::atomic_is_lock_free [C++]
- std::atomic_load [C++]
- std::atomic_load_explicit [C++]
- std::atomic_signal_fence [C++]
- std::atomic_store [C++]
- std::atomic_store_explicit [C++]
- std::atomic_thread_fence [C++]
- std::kill_dependency [C++]
ms.openlocfilehash: 5314db43bed913e801846341309513c239216887
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68459604"
---
# <a name="ltatomicgt-functions"></a>&lt;Atomik&gt; işlevler

||||
|-|-|-|
|[atomic_compare_exchange_strong](#atomic_compare_exchange_strong)|[atomic_compare_exchange_strong_explicit](#atomic_compare_exchange_strong_explicit)|[atomic_compare_exchange_weak](#atomic_compare_exchange_weak)|
|[atomic_compare_exchange_weak_explicit](#atomic_compare_exchange_weak_explicit)|[atomic_exchange](#atomic_exchange)|[atomic_exchange_explicit](#atomic_exchange_explicit)|
|[atomic_fetch_add](#atomic_fetch_add)|[atomic_fetch_add_explicit](#atomic_fetch_add_explicit)|[atomic_fetch_and](#atomic_fetch_and)|
|[atomic_fetch_and_explicit](#atomic_fetch_and_explicit)|[atomic_fetch_or](#atomic_fetch_or)|[atomic_fetch_or_explicit](#atomic_fetch_or_explicit)|
|[atomic_fetch_sub](#atomic_fetch_sub)|[atomic_fetch_sub_explicit](#atomic_fetch_sub_explicit)|[atomic_fetch_xor](#atomic_fetch_xor)|
|[atomic_fetch_xor_explicit](#atomic_fetch_xor_explicit)|[atomic_flag_clear](#atomic_flag_clear)|[atomic_flag_clear_explicit](#atomic_flag_clear_explicit)|
|[atomic_flag_test_and_set](#atomic_flag_test_and_set)|[atomic_flag_test_and_set_explicit](#atomic_flag_test_and_set_explicit)|[atomic_init](#atomic_init)|
|[atomic_is_lock_free](#atomic_is_lock_free)|[atomic_load](#atomic_load)|[atomic_load_explicit](#atomic_load_explicit)|
|[atomic_signal_fence](#atomic_signal_fence)|[atomic_store](#atomic_store)|[atomic_store_explicit](#atomic_store_explicit)|
|[atomic_thread_fence](#atomic_thread_fence)|[kill_dependency](#kill_dependency)|

## <a name="atomic_compare_exchange_strong"></a>atomic_compare_exchange_strong

Atomik karşılaştırma ve değişim işlemi gerçekleştirir.

```cpp
template <class Ty>
inline bool atomic_compare_exchange_strong(
    volatile atomic<Ty>* Atom,
    Ty* Exp,
    Value) noexcept;

template <class Ty>
inline bool atomic_compare_exchange_strong(
    atomic<Ty>* Atom,
    Ty* Exp,
    Ty Value) noexcept;
```

### <a name="parameters"></a>Parametreler

*Atom*\
Türünde`Ty`bir değer depolayan *atomik* nesne için bir işaretçi.

*Exp*\
Türünde `Ty`bir değer işaretçisi.

*Deeri*\
Türünde `Ty`bir değer.

### <a name="return-value"></a>Dönüş Değeri

Değerler eşitse **true** , aksi takdirde **false**.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, örtük `memory_order_seq_cst` [memory_order](../standard-library/atomic-enums.md#memory_order_enum) bağımsız değişkenleri kullanarak bir atomik karşılaştırma ve değişim işlemi gerçekleştirir. Daha fazla bilgi için bkz. [atomic_compare_exchange_strong_explicit](../standard-library/atomic-functions.md#atomic_compare_exchange_strong_explicit).

## <a name="atomic_compare_exchange_strong_explicit"></a>atomic_compare_exchange_strong_explicit

*Atomik karşılaştırma ve değişim* işlemi gerçekleştirir.

```cpp
template <class T>
inline bool atomic_compare_exchange_strong_explicit(
    volatile atomic<Ty>* Atom,
    Ty* Exp,
    Ty Value,
    memory_order Order1,
    memory_order Order2) noexcept;

template <class Ty>
inline bool atomic_compare_exchange_strong_explicit(
    atomic<Ty>* Atom,
    Ty* Exp,
    Ty Value,
    memory_order Order1,
    memory_order Order2) noexcept;
```

### <a name="parameters"></a>Parametreler

*Atom*\
`atomic` Türünde`Ty`bir değer depolayan nesne için bir işaretçi.

*Exp*\
Türünde `Ty`bir değer işaretçisi.

*Deeri*\
Türünde `Ty`bir değer.

*Order1*\
İlk [memory_order](../standard-library/atomic-enums.md#memory_order_enum) bağımsız değişkeni.

*Order2*\
İkinci `memory_order` bağımsız değişken. *Order2* `memory_order_release` değeri veya`memory_order_acq_rel`olamaz, *Order1*değerinden daha güçlü olamaz.

### <a name="return-value"></a>Dönüş Değeri

Değerler eşitse **true** , aksi takdirde **false**.

### <a name="remarks"></a>Açıklamalar

*Atomik karşılaştırma ve değişim işlemi* , *atom* tarafından işaret edilen nesnede depolanan değeri, *Exp*tarafından işaret edilen değere göre karşılaştırır. Değerler eşitse, *atom* tarafından işaret edilen nesnede depolanan değer, bir `read-modify-write` işlem kullanılarak ve *Order1*tarafından belirtilen bellek sırası kısıtlamaları uygulanarak *değeri* ile değiştirilmiştir. Değerler eşit değilse, işlem, *Exp* tarafından işaret edilen değeri, *atom* tarafından işaret edilen nesnede depolanan değerle değiştirir ve *Order2*tarafından belirtilen bellek sırası kısıtlamalarını uygular.

## <a name="atomic_compare_exchange_weak"></a>atomic_compare_exchange_weak

*Zayıf atomik karşılaştırma ve değişim* işlemi gerçekleştirir.

```cpp
template <class Ty>
inline bool atomic_compare_exchange_strong(
    volatile atomic<Ty>* Atom,
    Ty* Exp,
    Ty Value) noexcept;

template <class Ty>
inline bool atomic_compare_exchange_strong(
    atomic<Ty>* Atom,
    Ty* Exp,
    Ty Value) noexcept;
```

### <a name="parameters"></a>Parametreler

*Atom*\
`atomic` Türünde`Ty`bir değer depolayan nesne için bir işaretçi.

*Exp*\
Türünde `Ty`bir değer işaretçisi.

*Deeri*\
Türünde `Ty`bir değer.

### <a name="return-value"></a>Dönüş Değeri

Değerler eşitse **true** , aksi takdirde **false**.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, örtük `memory_order_seq_cst` [memory_order](../standard-library/atomic-enums.md#memory_order_enum) bağımsız değişkenlerine sahip *zayıf bir atomik karşılaştırma ve değişim işlemi* gerçekleştirir. Daha fazla bilgi için bkz. [atomic_compare_exchange_weak_explicit](../standard-library/atomic-functions.md#atomic_compare_exchange_weak_explicit).

## <a name="atomic_compare_exchange_weak_explicit"></a>atomic_compare_exchange_weak_explicit

*Zayıf atomik karşılaştırma ve değişim* işlemi gerçekleştirir.

```cpp
template <class Ty>
inline bool atomic_compare_exchange_weak_explicit(
    volatile atomic<Ty>* Atom,
    Ty* Exp,
    Ty Value,
    memory_order Order1,
    memory_order Order2) noexcept;

template <class Ty>
inline bool atomic_compare_exchange_weak_explicit(
    atomic<Ty>* Atom,
    Ty* Exp,
    Ty Value,
    memory_order Order1,
    memory_order Order2) noexcept;
```

### <a name="parameters"></a>Parametreler

*Atom*\
`atomic` Türünde`Ty`bir değer depolayan nesne için bir işaretçi.

*Exp*\
Türünde `Ty`bir değer işaretçisi.

*Deeri*\
Türünde `Ty`bir değer.

*Order1*\
İlk [memory_order](../standard-library/atomic-enums.md#memory_order_enum) bağımsız değişkeni.

*Order2*\
İkinci `memory_order` bağımsız değişken. *Order2* `memory_order_release` değeri veya`memory_order_acq_rel`, *Order1*değerinden daha güçlü olamaz.

### <a name="return-value"></a>Dönüş Değeri

Değerler eşitse **true** , aksi takdirde **false**.

### <a name="remarks"></a>Açıklamalar

Hem bir *atomik karşılaştırma hem de değişim işleminin* güçlü ve zayıf özellikleri, beklenen ve geçerli değerler eşit değilse yeni değeri depolamadıklarından emin olurlar. Güçlü özellik, beklenen ve geçerli değerler eşitse yeni değeri depolayacaktır. Zayıf Flavor bazen **yanlış** döndürebilir ve geçerli ve beklenen değerler eşitse bile yeni değeri depolamaz. Diğer bir deyişle, işlev **yanlış**döndürür, ancak beklenen değerin daha sonra incelendiğinde, değişmediği ortaya çıkabilir ve bu nedenle eşit olarak karşılaştırılmalıdır.

## <a name="atomic_exchange"></a>atomic_exchange

, *Atom*değerini saklı değerini *değiştirmek için kullanır* .

```cpp
template <class T>
inline Ty atomic_exchange(volatile atomic<Ty>* _Atom, Ty Value) noexcept;

template <class Ty>
inline T atomic_exchange(atomic<Ty>* Atom, Ty Value) noexcept;
```

### <a name="parameters"></a>Parametreler

*Atom*\
`atomic` Türünde`Ty`bir değer depolayan nesne için bir işaretçi.

*Deeri*\
Türünde `Ty`bir değer.

### <a name="return-value"></a>Dönüş Değeri

Exchange 'den önce, *atom* 'un depolanan değeri.

### <a name="remarks"></a>Açıklamalar

`read-modify-write` *İşlevi,* [memory_order](../standard-library/atomic-enums.md#memory_order_enum) kullanılarak atom`memory_order_seq_cst`' de depolanan değeri değiş tokuş etmek için bir işlem gerçekleştirir. `atomic_exchange`

## <a name="atomic_exchange_explicit"></a>atomic_exchange_explicit

*Atom* 'un depolanan değerini *değeriyle*değiştirir.

```cpp
template <class Ty>
inline Ty atomic_exchange_explicit(
    volatile atomic<Ty>* Atom,
    Ty Value,
    memory_order Order) noexcept;

template <class Ty>
inline Ty atomic_exchange_explicit(
    atomic<Ty>* Atom,
    Ty Value,
    memory_order Order) noexcept;
```

### <a name="parameters"></a>Parametreler

*Atom*\
`atomic` Türünde`Ty`bir değer depolayan nesne için bir işaretçi.

*Deeri*\
Türünde `Ty`bir değer.

*Siparişi*\
Bir [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

### <a name="return-value"></a>Dönüş Değeri

Exchange 'den önce, *atom* 'un depolanan değeri.

### <a name="remarks"></a>Açıklamalar

`read-modify-write`İşlevi, Order tarafından belirtilen bellek kısıtlamalarında değeri ile atom ' de depolanan değeri değiş tokuş etmek için bir işlem gerçekleştirir. `atomic_exchange_explicit`

## <a name="atomic_fetch_add"></a>atomic_fetch_add

Bir `atomic` nesnede depolanan varolan bir değere bir değer ekler.

```cpp
template <class T>
T* atomic_fetch_add(volatile atomic<T*>* Atom, ptrdiff_t Value) noexcept;
template <class T>
T* atomic_fetch_add(atomic<T*>* Atom, ptrdiff_t Value) noexcept;
```

### <a name="parameters"></a>Parametreler

*Atom*\
`atomic` Türe`T`işaretçi depolayan bir nesne işaretçisi.

*Deeri*\
Türünde `ptrdiff_t`bir değer.

### <a name="return-value"></a>Dönüş Değeri

İşlem gerçekleştirilmeden hemen önce atomik nesnenin içerdiği işaretçinin değeri.

### <a name="remarks"></a>Açıklamalar

`read-modify-write` `memory_order_seq_cst` [](../standard-library/atomic-enums.md#memory_order_enum) İşlevi, memory_order kısıtlamasını kullanarak, atom ' de depolanan değere değer eklemek için bir işlem gerçekleştirir. `atomic_fetch_add`

Atomik tür `atomic_address`olduğunda, *değer* türündedir `ptrdiff_t` ve işlem saklı işaretçiye bir `char *`olarak davranır.

Bu işlem, tam sayı türleri için de aşırı yüklendi:

```cpp
integral atomic_fetch_add(volatile atomic-integral* Atom, integral Value) noexcept;

integral atomic_fetch_add(atomic-integral* Atom, integral Value) noexcept;
```

## <a name="atomic_fetch_add_explicit"></a>atomic_fetch_add_explicit

Bir `atomic` nesnede depolanan varolan bir değere bir değer ekler.

```cpp
template <class T>
T* atomic_fetch_add_explicit(
    volatile atomic<T*>* Atom,
    ptrdiff_t Value,
    memory_order Order) noexcept;

template <class T>
T* atomic_fetch_add_explicit(
    atomic<T*>* Atom,
    ptrdiff_t Value,
    memory_order Order) noexcept;
```

### <a name="parameters"></a>Parametreler

*Atom*\
`atomic` Türe`T`işaretçi depolayan bir nesne işaretçisi.

*Deeri*\
Türünde `ptrdiff_t`bir değer.

### <a name="return-value"></a>Dönüş Değeri

İşlem gerçekleştirilmeden hemen önce atomik nesnenin içerdiği işaretçinin değeri.

### <a name="remarks"></a>Açıklamalar

`read-modify-write` İşlevi,`Order`tarafından belirtilen [memory_order](../standard-library/atomic-enums.md#memory_order_enum) kısıtlamaları dahilinde, *atom*' de depolanan değere değer eklemek için bir işlem gerçekleştirir. `atomic_fetch_add_explicit`

Atomik tür `atomic_address`olduğunda, `Value` türü `ptrdiff_t` vardır ve işlem saklı işaretçiye bir `char *`olarak davranır.

Bu işlem, tam sayı türleri için de aşırı yüklendi:

```cpp
integral atomic_fetch_add_explicit(
    volatile atomic-integral* Atom,
    integral Value,
    memory_order Order) noexcept;

integral atomic_fetch_add_explicit(
    atomic-integral* Atom,
    integral Value,
    memory_order Order) noexcept;
```

## <a name="atomic_fetch_and"></a>atomic_fetch_and

Bir değer üzerinde `and` bir bit düzeyinde ve bir `atomic` nesnesinde depolanan varolan değeri gerçekleştirir.

```cpp
template <class T>
inline T atomic_fetch_and(volatile atomic<T>* Atom, T Value) noexcept;
template <class T>
inline T atomic_fetch_and(volatile atomic<T>* Atom, T Value) noexcept;
```

### <a name="parameters"></a>Parametreler

*Atom*\
`atomic` Türünde`T`bir değer depolayan nesne için bir işaretçi.

*Deeri*\
Türünde `T`bir değer.

### <a name="return-value"></a>Dönüş Değeri

İşlem gerçekleştirilmeden hemen önce atomik nesne tarafından içerilen değer.

### <a name="remarks"></a>Açıklamalar

`and` `memory_order_seq_cst`İşlevi bir `read-modify-write` işlem gerçekleştirerek, atom değerini bir bit düzeyinde değer ve atom ' de depolanan geçerli değeri memory_order kullanarak değiştirin. `atomic_fetch_and` [ ](../standard-library/atomic-enums.md#memory_order_enum)kısıtlama.

## <a name="atomic_fetch_and_explicit"></a>atomic_fetch_and_explicit

Bir değerin bit `and` düzeyinde ve bir `atomic` nesnesinde depolanan varolan değeri gerçekleştirir.

```cpp
template <class T>
inline T atomic_fetch_and_explicit(
    volatile atomic<T>* Atom,
    T Value,
    memory_order Order) noexcept;

template <class T>
inline T atomic_fetch_and_explicit(
    volatile atomic<T>* Atom,
    T Value,
    memory_order Order) noexcept;
```

### <a name="parameters"></a>Parametreler

*Atom*\
`atomic` Türünde`T`bir değer depolayan nesne için bir işaretçi.

*Deeri*\
Türünde `T`bir değer.

*Siparişi*\
Bir [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

### <a name="return-value"></a>Dönüş Değeri

İşlem gerçekleştirilmeden hemen önce atomik nesne tarafından içerilen değer.

### <a name="remarks"></a>Açıklamalar

`and` `read-modify-write`İşlevi, belirtilen atom değerini bir bit düzeyinde değer ve atom ' de depolanan geçerli değeri, belirtilen bellek kısıtlamaları içinde değiştirmek için bir işlem gerçekleştirir `atomic_fetch_and_explicit` *sıraya*göre.

## <a name="atomic_fetch_or"></a>atomic_fetch_or

Bir değer üzerinde `or` bir bit düzeyinde ve bir `atomic` nesnesinde depolanan varolan değeri gerçekleştirir.

```cpp
template <class T>
inline T atomic_fetch_or (volatile atomic<T>* Atom, T Value) noexcept;
template <class T>
inline T atomic_fetch_or (volatile atomic<T>* Atom, T Value) noexcept;
```

### <a name="parameters"></a>Parametreler

*Atom*\
`atomic` Türünde`T`bir değer depolayan nesne için bir işaretçi.

*Deeri*\
Türünde `T`bir değer.

### <a name="return-value"></a>Dönüş Değeri

İşlem gerçekleştirilmeden hemen önce atomik nesne tarafından içerilen değer.

### <a name="remarks"></a>Açıklamalar

`or` `memory_order_seq_cst`İşlevi bir `read-modify-write` işlem gerçekleştirerek, atom değerini bir bit düzeyinde değer ve atom ' de depolanan geçerli değeri memory_order kullanarak değiştirin. `atomic_fetch_or` [ ](../standard-library/atomic-enums.md#memory_order_enum).

## <a name="atomic_fetch_or_explicit"></a>atomic_fetch_or_explicit

Bir değer üzerinde `or` bir bit düzeyinde ve bir `atomic` nesnesinde depolanan varolan değeri gerçekleştirir.

```cpp
template <class T>
inline T atomic_fetch_or_explicit(
    volatile atomic<T>* Atom,
    T Value,
    memory_order Order) noexcept;

template <class T>
inline T atomic_fetch_or_explicit(
    volatile atomic<T>* Atom,
    T Value,
    memory_order Order) noexcept;
```

### <a name="parameters"></a>Parametreler

*Atom*\
`atomic` Türünde`T`bir değer depolayan nesne için bir işaretçi.

*Deeri*\
Türünde `T`bir değer.

*Siparişi*\
Bir [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

### <a name="return-value"></a>Dönüş Değeri

İşlem gerçekleştirilmeden hemen önce atomik nesne tarafından içerilen değer.

### <a name="remarks"></a>Açıklamalar

`or` `read-modify-write` [](../standard-library/atomic-enums.md#memory_order_enum) İşlevi, memory_order kısıtlamalarında, atom değerini bir bit düzeyinde değer ve atom ' de depolanan geçerli değer ile değiştirmek için bir işlem gerçekleştirir `atomic_fetch_or_explicit` *sıraya*göre belirtilen.

## <a name="atomic_fetch_sub"></a>atomic_fetch_sub

Bir `atomic` nesne içinde depolanan varolan bir değerden değeri çıkartır.

```cpp
template <class T>
T* atomic_fetch_sub(
    volatile atomic<T*>* Atom,
    ptrdiff_t Value) noexcept;

template <class T>
T* atomic_fetch_sub(
    atomic<T*>* Atom,
    ptrdiff_t Value) noexcept;
```

### <a name="parameters"></a>Parametreler

*Atom*\
`atomic` Türe`T`işaretçi depolayan bir nesne işaretçisi.

*Deeri*\
Türünde `ptrdiff_t`bir değer.

### <a name="return-value"></a>Dönüş Değeri

İşlem gerçekleştirilmeden hemen önce atomik nesnenin içerdiği işaretçinin değeri.

### <a name="remarks"></a>Açıklamalar

`read-modify-write` `memory_order_seq_cst` [](../standard-library/atomic-enums.md#memory_order_enum) İşlevi, memory_order kısıtlamasını kullanarak, atom 'daki depolanan değerden değeri otomatik olarak çıkarmak için bir işlem gerçekleştirir. `atomic_fetch_sub`

Atomik tür `atomic_address`olduğunda, *değer* türündedir `ptrdiff_t` ve işlem saklı işaretçiye bir `char *`olarak davranır.

Bu işlem, tam sayı türleri için de aşırı yüklendi:

```cpp
integral atomic_fetch_sub(volatile atomic-integral* Atom, integral Value) noexcept;
integral atomic_fetch_sub(atomic-integral* Atom, integral Value) noexcept;
```

## <a name="atomic_fetch_sub_explicit"></a>atomic_fetch_sub_explicit

Bir `atomic` nesne içinde depolanan varolan bir değerden değeri çıkartır.

```cpp
template <class T>
T* atomic_fetch_sub_explicit(
    volatile atomic<T*>* Atom,
    ptrdiff_t Value,
    memory_order Order) noexcept;

template <class T>
T* atomic_fetch_sub_explicit(
    atomic<T*>* Atom,
    ptrdiff_t Value, memory_order Order) noexcept;
```

### <a name="parameters"></a>Parametreler

*Atom*\
`atomic` Türe`T`işaretçi depolayan bir nesne işaretçisi.

*Deeri*\
Türünde `ptrdiff_t`bir değer.

### <a name="return-value"></a>Dönüş Değeri

İşlem gerçekleştirilmeden hemen önce atomik nesnenin içerdiği işaretçinin değeri.

### <a name="remarks"></a>Açıklamalar

`read-modify-write` İşlevi,`Order`tarafından belirtilen [memory_order](../standard-library/atomic-enums.md#memory_order_enum) kısıtlamaları dahilinde, *atom*'daki depolanan değerden değeri atomicınsel olarak çıkarmak için bir işlem gerçekleştirir. `atomic_fetch_sub_explicit`

Atomik tür `atomic_address`olduğunda, *değer* türündedir `ptrdiff_t` ve işlem saklı işaretçiye bir `char *`olarak davranır.

Bu işlem, tam sayı türleri için de aşırı yüklendi:

```cpp
integral atomic_fetch_sub_explicit(
    volatile atomic-integral* Atom,
    integral Value,
    memory_order Order) noexcept;

integral atomic_fetch_sub_explicit(
    atomic-integral* Atom,
    integral Value,
    memory_order Order) noexcept;
```

## <a name="atomic_fetch_xor"></a>atomic_fetch_xor

Bir değer üzerinde `exclusive or` bir bit düzeyinde ve bir `atomic` nesnesinde depolanan varolan değeri gerçekleştirir.

```cpp
template <class T>
inline T atomic_fetch_xor(volatile atomic<T>* Atom, T Value) noexcept;

template <class T>
inline T atomic_fetch_xor(volatile atomic<T>* Atom, T Value) noexcept;
```

### <a name="parameters"></a>Parametreler

*Atom*\
`atomic` Türünde`T`bir değer depolayan nesne için bir işaretçi.

*Deeri*\
Türünde `T`bir değer.

### <a name="return-value"></a>Dönüş Değeri

İşlem gerçekleştirilmeden hemen önce atomik nesne tarafından içerilen değer.

### <a name="remarks"></a>Açıklamalar

`exclusive or` `memory_order_seq_cst`İşlevi bir `read-modify-write` işlem gerçekleştirerek, atom değerini bir bit düzeyinde değer ve atom ' de depolanan geçerli değeri memory_order kullanarak değiştirin. `atomic_fetch_xor` [ ](../standard-library/atomic-enums.md#memory_order_enum).

## <a name="atomic_fetch_xor_explicit"></a>atomic_fetch_xor_explicit

Bir değer üzerinde `exclusive or` bir bit düzeyinde ve bir `atomic` nesnesinde depolanan varolan değeri gerçekleştirir.

```cpp
template <class T>
inline T atomic_fetch_xor_explicit(
    volatile atomic<T>* Atom,
    T Value,
    memory_order Order) noexcept;

template <class T>
inline T atomic_fetch_xor_explicit(
    volatile atomic<T>* Atom,
    T Value,
    memory_order Order) noexcept;
```

### <a name="parameters"></a>Parametreler

*Atom*\
`atomic` Türünde`T`bir değer depolayan nesne için bir işaretçi.

*Deeri*\
Türünde `T`bir değer.

*Siparişi*\
Bir [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

### <a name="return-value"></a>Dönüş Değeri

İşlem gerçekleştirilmeden hemen önce atomik nesne tarafından içerilen değer.

### <a name="remarks"></a>Açıklamalar

`exclusive or` `read-modify-write` [](../standard-library/atomic-enums.md#memory_order_enum) İşlevi, memory_order kısıtlamalarında, atom değerini bir bit düzeyinde değer ve atom ' de depolanan geçerli değer ile değiştirmek için bir işlem gerçekleştirir `atomic_fetch_xor_explicit` Bu, *sırasıyla*belirtilen.

## <a name="atomic_flag_clear"></a>atomic_flag_clear

[Atomic_flag](../standard-library/atomic-flag-structure.md) nesnesindeki **bool** bayrağını [memory_order](../standard-library/atomic-enums.md#memory_order_enum)içinde `memory_order_seq_cst` **false**olarak ayarlar.

```cpp
inline void atomic_flag_clear(volatile atomic_flag* Flag) noexcept;
inline void atomic_flag_clear(atomic_flag* Flag) noexcept;
```

### <a name="parameters"></a>Parametreler

*Bayrağıyla*\
Bir `atomic_flag` nesne işaretçisi.

## <a name="atomic_flag_clear_explicit"></a>  atomic_flag_clear_explicit

[Atomic_flag](../standard-library/atomic-flag-structure.md) nesnesindeki **bool** bayrağını, belirtilen [memory_order](../standard-library/atomic-enums.md#memory_order_enum) kısıtlamaları içinde **false**olarak ayarlar.

```cpp
inline void atomic_flag_clear_explicit(volatile atomic_flag* Flag, memory_order Order) noexcept;
inline void atomic_flag_clear_explicit(atomic_flag* Flag, memory_order Order) noexcept;
```

### <a name="parameters"></a>Parametreler

*Bayrağıyla*\
Bir `atomic_flag` nesne işaretçisi.

*Siparişi*\
Bir [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

## <a name="atomic_flag_test_and_set"></a>atomic_flag_test_and_set

[Memory_order](../standard-library/atomic-enums.md#memory_order_enum)kısıtlamaları [](../standard-library/atomic-flag-structure.md) içinde`memory_order_seq_cst`, bir atomic_flag nesnesindeki bool bayrağını True olarak ayarlar.

```cpp
inline bool atomic_flag_test_and_set(volatile atomic_flag* Flag,) noexcept;
inline bool atomic_flag_test_and_set(atomic_flag* Flag,) noexcept;
```

### <a name="parameters"></a>Parametreler

*Bayrağıyla*\
Bir `atomic_flag` nesne işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

*Bayrağın*başlangıç değeri.

## <a name="atomic_flag_test_and_set_explicit"></a>  atomic_flag_test_and_set_explicit

[Atomic_flag](../standard-library/atomic-flag-structure.md) nesnesindeki **bool** bayrağını, belirtilen [memory_order](../standard-library/atomic-enums.md#memory_order_enum) kısıtlamaları içinde **true**olarak ayarlar.

```cpp
inline bool atomic_flag_test_and_set_explicit(volatile atomic_flag* Flag, memory_order Order) noexcept;
inline bool atomic_flag_test_and_set_explicit(atomic_flag* Flag, memory_order Order) noexcept;
```

### <a name="parameters"></a>Parametreler

*Bayrağıyla*\
Bir `atomic_flag` nesne işaretçisi.

*Siparişi*\
Bir [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

### <a name="return-value"></a>Dönüş Değeri

*Bayrağın*başlangıç değeri.

## <a name="atomic_init"></a>atomic_init

Bir `atomic` nesne içindeki saklı değeri ayarlar.

```cpp
template <class Ty>
inline void atomic_init(volatile atomic<Ty>* Atom, Ty Value) noexcept;
template <class Ty>
inline void atomic_init(atomic<Ty>* Atom, Ty Value) noexcept;
```

### <a name="parameters"></a>Parametreler

*Atom*\
`atomic` Türünde`Ty`bir değer depolayan nesne için bir işaretçi.

*Deeri*\
Türünde `Ty`bir değer.

### <a name="remarks"></a>Açıklamalar

`atomic_init`Atomik bir işlem değil. İş parçacığı açısından güvenli değildir.

## <a name="atomic_is_lock_free"></a>atomic_is_lock_free

Bir `atomic` nesne üzerindeki atomik işlemlerin *kilitli*olup olmadığını belirtir.

```cpp
template <class T>
inline bool atomic_is_lock_free(const volatile atomic<T>* Atom) noexcept;
template <class T>
inline bool atomic_is_lock_free(const atomic<T>* Atom) noexcept;
```

### <a name="parameters"></a>Parametreler

*Atom*\
`atomic` Türünde`T`bir değer depolayan nesne için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

*atom* üzerinde Atomik işlemler kilitsiz ise **doğru** ; Aksi takdirde, **false**.

### <a name="remarks"></a>Açıklamalar

Bir atomik tür, bu tür üzerinde hiçbir Atomik işlem kilit kullanıyorsa kilit ücretsizdir. Bu işlev true değerini döndürürse, tür sinyal işleyicilerde kullanılmak üzere güvenlidir.

## <a name="atomic_load"></a>atomic_load

Bir `atomic` nesnesinde depolanan değeri alır.

```cpp
template <class Ty>
inline Ty atomic_load(const volatile atomic<Ty>* Atom) noexcept;
template <class Ty>
inline Ty atomic_load(const atomic<Ty>* Atom) noexcept;
```

### <a name="parameters"></a>Parametreler

*Atom*\
`atomic` Türünde`Ty`bir değer içeren bir nesne işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

*Atom*içinde depolanan alınan değer.

### <a name="remarks"></a>Açıklamalar

`atomic_load`örtük olarak `memory_order_seq_cst` [memory_order](../standard-library/atomic-enums.md#memory_order_enum)kullanır.

## <a name="atomic_load_explicit"></a>atomic_load_explicit

Belirtilen bir memory_order içinde depolanan değeri `atomic` bir nesne içinde alır. [](../standard-library/atomic-enums.md#memory_order_enum)

```cpp
template <class Ty>
inline Ty atomic_load_explicit(const volatile atomic<Ty>* Atom, memory_order Order) noexcept;
template <class Ty>
inline Ty atomic_load_explicit(const atomic<Ty>* Atom, memory_order Order) noexcept;
```

### <a name="parameters"></a>Parametreler

*Atom*\
`atomic` Türünde`Ty`bir değer içeren bir nesne işaretçisi.

*Siparişi*\
Bir [memory_order](../standard-library/atomic-enums.md#memory_order_enum). `memory_order_release` Veya`memory_order_acq_rel`kullanmayın.

### <a name="return-value"></a>Dönüş Değeri

*Atom*içinde depolanan alınan değer.

## <a name="atomic_signal_fence"></a>atomic_signal_fence

Aynı iş parçacığındayürütülen sinyal işleyicilerine sahip bir çağıran iş parçacığındaki diğer balıklarla, yükleme/depolama işlemleri arasında sıralamayı zorlayan bir sınır gibi davranır.

```cpp
inline void atomic_signal_fence(memory_order Order) noexcept;
```

### <a name="parameters"></a>Parametreler

*Siparişi*\
Çit türünü belirleyen bir bellek sıralama kısıtlaması.

### <a name="remarks"></a>Açıklamalar

*Order* bağımsız değişkeni sınır türünü belirler.

|||
|-|-|
|`memory_order_relaxed`|Çit etkisizdir.|
|`memory_order_consume`|Çit, bir edinme dilimtir.|
|`memory_order_acquire`|Çit, bir edinme dilimtir.|
|`memory_order_release`|Sınır, bir yayın dilimi.|
|`memory_order_acq_rel`|Sınır hem bir alma dilimi hem de serbest bırakma dilimi.|
|`memory_order_seq_cst`|Sınır hem bir alma dilimi hem de serbest bırakma dilimi ve sıralı olarak tutarlıdır.|

## <a name="atomic_store"></a>atomic_store

Atomik bir nesnede bir değeri atomicbir şekilde depolar.

```cpp
template <class Ty>
inline Ty atomic_store_explicit(const volatile atomic<Ty>* Atom, Ty Value) noexcept;
template <class Ty>
inline Ty atomic_store_explicit(const atomic<Ty>* Atom, T Value) noexcept;
```

### <a name="parameters"></a>Parametreler

*Atom*\
Türünde `Ty`bir değer içeren atomik nesne için bir işaretçi.

*Deeri*\
Türünde `Ty`bir değer.

### <a name="remarks"></a>Açıklamalar

`atomic_store`*değeri* , [memory_order](../standard-library/atomic-enums.md#memory_order_enum) kısıtlaması içinde `memory_order_seq_cst` *atom*tarafından işaret edilen nesnede depolar.

## <a name="atomic_store_explicit"></a>atomic_store_explicit

Atomik bir nesnede bir değeri atomicbir şekilde depolar.

```cpp
template <class Ty>
inline Ty atomic_store_explicit(
    const volatile atomic<Ty>* Atom,
    Ty Value,
    memory_order Order) noexcept;

template <class Ty>
inline Ty atomic_store_explicit(
    const atomic<Ty>* Atom,
    T Value,
    memory_order Order) noexcept;
```

### <a name="parameters"></a>Parametreler

*Atom*\
`atomic` Türünde`Ty`bir değer içeren bir nesne işaretçisi.

*Deeri*\
Türünde `Ty`bir değer.

*Siparişi*\
Bir [memory_order](../standard-library/atomic-enums.md#memory_order_enum). , `memory_order_consume` `memory_order_acquire`Veya kullanmayın.`memory_order_acq_rel`

### <a name="remarks"></a>Açıklamalar

`atomic_store`*değerini* , *sıralamayla*belirtilen içindeki `memory_order` , *atom*tarafından işaret edilen nesnede depolar.

## <a name="atomic_thread_fence"></a>atomic_thread_fence

İlişkili bir atomik işlem olmadan, yük/depolama işlemleri arasında sıralamayı zorlayan bir bellek eşitleme temel alanı olan bir *çit*gibi davranır.

```cpp
inline void atomic_thread_fence(memory_order Order) noexcept;
```

### <a name="parameters"></a>Parametreler

*Siparişi*\
Çit türünü belirleyen bir bellek sıralama kısıtlaması.

### <a name="remarks"></a>Açıklamalar

*Order* bağımsız değişkeni sınır türünü belirler.

|||
|-|-|
|`memory_order_relaxed`|Çit etkisizdir.|
|`memory_order_consume`|Çit, bir edinme dilimtir.|
|`memory_order_acquire`|Çit, bir edinme dilimtir.|
|`memory_order_release`|Sınır, bir yayın dilimi.|
|`memory_order_acq_rel`|Sınır hem bir alma dilimi hem de serbest bırakma dilimi.|
|`memory_order_seq_cst`|Sınır hem bir alma dilimi hem de serbest bırakma dilimi ve sıralı olarak tutarlıdır.|

## <a name="kill_dependency"></a>kill_dependency

Bir bağımlılığı kaldırır.

```cpp
template <class Ty>
Ty kill_dependency(Ty Arg) noexcept;
```

### <a name="parameters"></a>Parametreler

*Değişkeni*\
Türünde `Ty`bir değer.

### <a name="return-value"></a>Dönüş Değeri

Dönüş değeri *bağımsız değişken*. *Bağımsız değişken* değerlendirmesi, işlev çağrısına bir bağımlılık taşımaz. Olası bir bağımlılık zincirini bozarak, işlev derleyicinin daha verimli kod oluşturmasına izin verebilir.

## <a name="see-also"></a>Ayrıca bkz.

[\<Atomik >](../standard-library/atomic.md)
