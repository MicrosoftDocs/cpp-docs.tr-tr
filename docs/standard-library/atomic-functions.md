---
title: '&lt;atomik&gt; işlevleri'
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
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79421998"
---
# <a name="ltatomicgt-functions"></a>&lt;atomik&gt; işlevleri

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
`Ty`türünde bir değer depolayan *atomik* nesneye yönelik bir işaretçi.

*Exp*\
`Ty`türünde bir değer işaretçisi.

*Değer*\
`Ty`türünde bir değer.

### <a name="return-value"></a>Dönüş Değeri

Değerler eşitse **true** , aksi takdirde **false**.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, örtük `memory_order_seq_cst`[memory_order](../standard-library/atomic-enums.md#memory_order_enum) bağımsız değişkenlerini kullanarak atomik bir karşılaştırma ve değişim işlemi gerçekleştirir. Daha fazla bilgi için bkz. [atomic_compare_exchange_strong_explicit](../standard-library/atomic-functions.md#atomic_compare_exchange_strong_explicit).

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
`Ty`türünde bir değer depolayan `atomic` nesnesine yönelik bir işaretçi.

*Exp*\
`Ty`türünde bir değer işaretçisi.

*Değer*\
`Ty`türünde bir değer.

*Order1*\
İlk [memory_order](../standard-library/atomic-enums.md#memory_order_enum) bağımsız değişkeni.

*Order2*\
İkinci `memory_order` bağımsız değişkeni. *Order2* değeri `memory_order_release` veya `memory_order_acq_rel`olamaz, *Order1*değerinden daha güçlü olamaz.

### <a name="return-value"></a>Dönüş Değeri

Değerler eşitse **true** , aksi takdirde **false**.

### <a name="remarks"></a>Açıklamalar

*Atomik karşılaştırma ve değişim işlemi* , *atom* tarafından işaret edilen nesnede depolanan değeri, *Exp*tarafından işaret edilen değere göre karşılaştırır. Değerler eşitse, *atom* tarafından işaret edilen nesnede depolanan değer, `read-modify-write` bir işlem kullanarak ve *Order1*tarafından belirtilen bellek sırası kısıtlamalarını uygulayarak *değeri* ile değiştirilmiştir. Değerler eşit değilse, işlem, *Exp* tarafından işaret edilen değeri, *atom* tarafından işaret edilen nesnede depolanan değerle değiştirir ve *Order2*tarafından belirtilen bellek sırası kısıtlamalarını uygular.

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
`Ty`türünde bir değer depolayan `atomic` nesnesine yönelik bir işaretçi.

*Exp*\
`Ty`türünde bir değer işaretçisi.

*Değer*\
`Ty`türünde bir değer.

### <a name="return-value"></a>Dönüş Değeri

Değerler eşitse **true** , aksi takdirde **false**.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, örtük `memory_order_seq_cst`[memory_order](../standard-library/atomic-enums.md#memory_order_enum) bağımsız değişkenlerine sahip *zayıf bir atomik karşılaştırma ve değişim işlemi* gerçekleştirir. Daha fazla bilgi için bkz. [atomic_compare_exchange_weak_explicit](../standard-library/atomic-functions.md#atomic_compare_exchange_weak_explicit).

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
`Ty`türünde bir değer depolayan `atomic` nesnesine yönelik bir işaretçi.

*Exp*\
`Ty`türünde bir değer işaretçisi.

*Değer*\
`Ty`türünde bir değer.

*Order1*\
İlk [memory_order](../standard-library/atomic-enums.md#memory_order_enum) bağımsız değişkeni.

*Order2*\
İkinci `memory_order` bağımsız değişkeni. *Order2* değeri `memory_order_release` veya `memory_order_acq_rel`olamaz, ya da *Order1*değerinden daha güçlü olabilir.

### <a name="return-value"></a>Dönüş Değeri

Değerler eşitse **true** , aksi takdirde **false**.

### <a name="remarks"></a>Açıklamalar

Hem bir *atomik karşılaştırma hem de değişim işleminin* güçlü ve zayıf özellikleri, beklenen ve geçerli değerler eşit değilse yeni değeri depolamadıklarından emin olurlar. Güçlü özellik, beklenen ve geçerli değerler eşitse yeni değeri depolayacaktır. Zayıf Flavor bazen **yanlış** döndürebilir ve geçerli ve beklenen değerler eşitse bile yeni değeri depolamaz. Diğer bir deyişle, işlev **yanlış**döndürür, ancak beklenen değerin daha sonra incelendiğinde, değişmediği ortaya çıkabilir ve bu nedenle eşit olarak karşılaştırılmalıdır.

## <a name="atomic_exchange"></a>atomic_exchange

, *Atom* *değerini saklı değerini değiştirmek için kullanır* .

```cpp
template <class T>
inline Ty atomic_exchange(volatile atomic<Ty>* _Atom, Ty Value) noexcept;

template <class Ty>
inline T atomic_exchange(atomic<Ty>* Atom, Ty Value) noexcept;
```

### <a name="parameters"></a>Parametreler

*Atom*\
`Ty`türünde bir değer depolayan `atomic` nesnesine yönelik bir işaretçi.

*Değer*\
`Ty`türünde bir değer.

### <a name="return-value"></a>Dönüş Değeri

Exchange 'den önce, *atom* 'un depolanan değeri.

### <a name="remarks"></a>Açıklamalar

`atomic_exchange` *işlevi, `memory_order_seq_cst`* [memory_order](../standard-library/atomic-enums.md#memory_order_enum)kullanılarak *atom* ' de depolanan değeri değiş tokuş etmek için bir `read-modify-write` işlemi gerçekleştirir.

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
`Ty`türünde bir değer depolayan `atomic` nesnesine yönelik bir işaretçi.

*Değer*\
`Ty`türünde bir değer.

*Sipariş*\
Bir [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

### <a name="return-value"></a>Dönüş Değeri

Exchange 'den önce, *atom* 'un depolanan değeri.

### <a name="remarks"></a>Açıklamalar

`atomic_exchange_explicit` işlevi, *Order*tarafından belirtilen bellek kısıtlamalarında *değer*ile *atom* içinde depolanan değeri değiştirmek için bir `read-modify-write` işlemi gerçekleştirir.

## <a name="atomic_fetch_add"></a>atomic_fetch_add

`atomic` nesnesinde depolanan mevcut bir değere bir değer ekler.

```cpp
template <class T>
T* atomic_fetch_add(volatile atomic<T*>* Atom, ptrdiff_t Value) noexcept;
template <class T>
T* atomic_fetch_add(atomic<T*>* Atom, ptrdiff_t Value) noexcept;
```

### <a name="parameters"></a>Parametreler

*Atom*\
`T`yazmak için bir işaretçi depolayan `atomic` nesnesine yönelik bir işaretçi.

*Değer*\
`ptrdiff_t`türünde bir değer.

### <a name="return-value"></a>Dönüş Değeri

İşlem gerçekleştirilmeden hemen önce atomik nesnenin içerdiği işaretçinin değeri.

### <a name="remarks"></a>Açıklamalar

`atomic_fetch_add` işlevi, `memory_order_seq_cst`[memory_order](../standard-library/atomic-enums.md#memory_order_enum) kısıtlamasını kullanarak, *atom*' de depolanan değere *değeri* otomatik olarak eklemek için bir `read-modify-write` işlemi gerçekleştirir.

Atomik tür `atomic_address`olduğunda, *değer* `ptrdiff_t` tür olur ve işlem, saklı işaretçiyi bir `char *`olarak değerlendirir.

Bu işlem, tam sayı türleri için de aşırı yüklendi:

```cpp
integral atomic_fetch_add(volatile atomic-integral* Atom, integral Value) noexcept;

integral atomic_fetch_add(atomic-integral* Atom, integral Value) noexcept;
```

## <a name="atomic_fetch_add_explicit"></a>atomic_fetch_add_explicit

`atomic` nesnesinde depolanan mevcut bir değere bir değer ekler.

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
`T`yazmak için bir işaretçi depolayan `atomic` nesnesine yönelik bir işaretçi.

*Değer*\
`ptrdiff_t`türünde bir değer.

### <a name="return-value"></a>Dönüş Değeri

İşlem gerçekleştirilmeden hemen önce atomik nesnenin içerdiği işaretçinin değeri.

### <a name="remarks"></a>Açıklamalar

`atomic_fetch_add_explicit` işlevi, `Order`tarafından belirtilen [memory_order](../standard-library/atomic-enums.md#memory_order_enum) kısıtlamalarında, *atom*içindeki depolanan değere *değeri* otomatik olarak eklemek için bir `read-modify-write` işlemi gerçekleştirir.

Atomik tür `atomic_address`olduğunda, `Value` tür `ptrdiff_t` sahiptir ve işlem, saklı işaretçiyi bir `char *`olarak değerlendirir.

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

Değer üzerinde bir bit düzeyinde `and` ve `atomic` nesnesinde depolanan varolan değeri gerçekleştirir.

```cpp
template <class T>
inline T atomic_fetch_and(volatile atomic<T>* Atom, T Value) noexcept;
template <class T>
inline T atomic_fetch_and(volatile atomic<T>* Atom, T Value) noexcept;
```

### <a name="parameters"></a>Parametreler

*Atom*\
`T`türünde bir değer depolayan `atomic` nesnesine yönelik bir işaretçi.

*Değer*\
`T`türünde bir değer.

### <a name="return-value"></a>Dönüş Değeri

İşlem gerçekleştirilmeden hemen önce atomik nesne tarafından içerilen değer.

### <a name="remarks"></a>Açıklamalar

`atomic_fetch_and` işlevi, *atom* değerini, `memory_order_seq_cst`[memory_order](../standard-library/atomic-enums.md#memory_order_enum) kısıtlamasını kullanarak bir *değer* bit düzeyi `and` ve *atom*' de depolanan geçerli değeri ile değiştirmek için `read-modify-write` bir işlem gerçekleştirir.

## <a name="atomic_fetch_and_explicit"></a>atomic_fetch_and_explicit

Bir değerin bit düzeyinde `and` ve `atomic` nesnesinde depolanan mevcut bir değeri gerçekleştirir.

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
`T`türünde bir değer depolayan `atomic` nesnesine yönelik bir işaretçi.

*Değer*\
`T`türünde bir değer.

*Sipariş*\
Bir [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

### <a name="return-value"></a>Dönüş Değeri

İşlem gerçekleştirilmeden hemen önce atomik nesne tarafından içerilen değer.

### <a name="remarks"></a>Açıklamalar

`atomic_fetch_and_explicit` işlevi, *atom* değerini bir *değerin* bit düzeyinde bir `and` ve *atom*' de depolanan geçerli değeri *Order*tarafından belirtilen bellek kısıtlamalarında değiştirmek için `read-modify-write` bir işlemi gerçekleştirir.

## <a name="atomic_fetch_or"></a>atomic_fetch_or

Değer üzerinde bir bit düzeyinde `or` ve `atomic` nesnesinde depolanan varolan değeri gerçekleştirir.

```cpp
template <class T>
inline T atomic_fetch_or (volatile atomic<T>* Atom, T Value) noexcept;
template <class T>
inline T atomic_fetch_or (volatile atomic<T>* Atom, T Value) noexcept;
```

### <a name="parameters"></a>Parametreler

*Atom*\
`T`türünde bir değer depolayan `atomic` nesnesine yönelik bir işaretçi.

*Değer*\
`T`türünde bir değer.

### <a name="return-value"></a>Dönüş Değeri

İşlem gerçekleştirilmeden hemen önce atomik nesne tarafından içerilen değer.

### <a name="remarks"></a>Açıklamalar

`atomic_fetch_or` işlevi, *atom* değerini bir *değeri* bit düzeyinde `or` ve *atom*içinde depolanan geçerli değeri `memory_order_seq_cst`[memory_order](../standard-library/atomic-enums.md#memory_order_enum)kullanarak değiştirmek için `read-modify-write` bir işlemi gerçekleştirir.

## <a name="atomic_fetch_or_explicit"></a>atomic_fetch_or_explicit

Değer üzerinde bir bit düzeyinde `or` ve `atomic` nesnesinde depolanan varolan değeri gerçekleştirir.

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
`T`türünde bir değer depolayan `atomic` nesnesine yönelik bir işaretçi.

*Değer*\
`T`türünde bir değer.

*Sipariş*\
Bir [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

### <a name="return-value"></a>Dönüş Değeri

İşlem gerçekleştirilmeden hemen önce atomik nesne tarafından içerilen değer.

### <a name="remarks"></a>Açıklamalar

`atomic_fetch_or_explicit` işlevi, *atom* değerini bir *değerin* bit düzeyinde bir `or` ve *atom*' de depolanan geçerli değeri *Order*tarafından belirtilen [memory_order](../standard-library/atomic-enums.md#memory_order_enum) kısıtlamalarına göre değiştirmek için `read-modify-write` bir işlemi gerçekleştirir.

## <a name="atomic_fetch_sub"></a>atomic_fetch_sub

`atomic` nesnesinde depolanan mevcut bir değerden bir değeri çıkartır.

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
`T`yazmak için bir işaretçi depolayan `atomic` nesnesine yönelik bir işaretçi.

*Değer*\
`ptrdiff_t`türünde bir değer.

### <a name="return-value"></a>Dönüş Değeri

İşlem gerçekleştirilmeden hemen önce atomik nesnenin içerdiği işaretçinin değeri.

### <a name="remarks"></a>Açıklamalar

`atomic_fetch_sub` işlevi, `memory_order_seq_cst`[memory_order](../standard-library/atomic-enums.md#memory_order_enum) kısıtlamasını kullanarak, *atom*'daki depolanan değerden *değeri* otomatik olarak çıkarmak için bir `read-modify-write` işlemi gerçekleştirir.

Atomik tür `atomic_address`olduğunda, *değer* `ptrdiff_t` tür olur ve işlem, saklı işaretçiyi bir `char *`olarak değerlendirir.

Bu işlem, tam sayı türleri için de aşırı yüklendi:

```cpp
integral atomic_fetch_sub(volatile atomic-integral* Atom, integral Value) noexcept;
integral atomic_fetch_sub(atomic-integral* Atom, integral Value) noexcept;
```

## <a name="atomic_fetch_sub_explicit"></a>atomic_fetch_sub_explicit

`atomic` nesnesinde depolanan mevcut bir değerden bir değeri çıkartır.

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
`T`yazmak için bir işaretçi depolayan `atomic` nesnesine yönelik bir işaretçi.

*Değer*\
`ptrdiff_t`türünde bir değer.

### <a name="return-value"></a>Dönüş Değeri

İşlem gerçekleştirilmeden hemen önce atomik nesnenin içerdiği işaretçinin değeri.

### <a name="remarks"></a>Açıklamalar

`atomic_fetch_sub_explicit` işlevi, `Order`tarafından belirtilen [memory_order](../standard-library/atomic-enums.md#memory_order_enum) kısıtlamalarında, *atom*'daki depolanan değerden *değeri* otomatik olarak çıkarmak için bir `read-modify-write` işlemi gerçekleştirir.

Atomik tür `atomic_address`olduğunda, *değer* `ptrdiff_t` tür olur ve işlem, saklı işaretçiyi bir `char *`olarak değerlendirir.

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

Değer üzerinde bir bit düzeyinde `exclusive or` ve `atomic` nesnesinde depolanan varolan değeri gerçekleştirir.

```cpp
template <class T>
inline T atomic_fetch_xor(volatile atomic<T>* Atom, T Value) noexcept;

template <class T>
inline T atomic_fetch_xor(volatile atomic<T>* Atom, T Value) noexcept;
```

### <a name="parameters"></a>Parametreler

*Atom*\
`T`türünde bir değer depolayan `atomic` nesnesine yönelik bir işaretçi.

*Değer*\
`T`türünde bir değer.

### <a name="return-value"></a>Dönüş Değeri

İşlem gerçekleştirilmeden hemen önce atomik nesne tarafından içerilen değer.

### <a name="remarks"></a>Açıklamalar

`atomic_fetch_xor` işlevi, *atom* değerini bir *değeri* bit düzeyinde `exclusive or` ve *atom*içinde depolanan geçerli değeri `memory_order_seq_cst`[memory_order](../standard-library/atomic-enums.md#memory_order_enum)kullanarak değiştirmek için `read-modify-write` bir işlemi gerçekleştirir.

## <a name="atomic_fetch_xor_explicit"></a>atomic_fetch_xor_explicit

Değer üzerinde bir bit düzeyinde `exclusive or` ve `atomic` nesnesinde depolanan varolan değeri gerçekleştirir.

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
`T`türünde bir değer depolayan `atomic` nesnesine yönelik bir işaretçi.

*Değer*\
`T`türünde bir değer.

*Sipariş*\
Bir [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

### <a name="return-value"></a>Dönüş Değeri

İşlem gerçekleştirilmeden hemen önce atomik nesne tarafından içerilen değer.

### <a name="remarks"></a>Açıklamalar

`atomic_fetch_xor_explicit` işlevi, *atom* değerini bir *değerin* bit düzeyinde bir `exclusive or` ve *atom*' de depolanan geçerli değeri *Order*tarafından belirtilen [memory_order](../standard-library/atomic-enums.md#memory_order_enum) kısıtlamalarında değiştirmek için `read-modify-write` bir işlemi gerçekleştirir.

## <a name="atomic_flag_clear"></a>atomic_flag_clear

[Atomic_flag](../standard-library/atomic-flag-structure.md) nesnesindeki **bool** bayrağını `memory_order_seq_cst`[memory_order](../standard-library/atomic-enums.md#memory_order_enum)içinde **false**olarak ayarlar.

```cpp
inline void atomic_flag_clear(volatile atomic_flag* Flag) noexcept;
inline void atomic_flag_clear(atomic_flag* Flag) noexcept;
```

### <a name="parameters"></a>Parametreler

*Bayrak*\
`atomic_flag` nesnesine yönelik bir işaretçi.

## <a name="atomic_flag_clear_explicit"></a>atomic_flag_clear_explicit

[Atomic_flag](../standard-library/atomic-flag-structure.md) nesnesindeki **bool** bayrağını, belirtilen [memory_order](../standard-library/atomic-enums.md#memory_order_enum) kısıtlamalarında **false**olarak ayarlar.

```cpp
inline void atomic_flag_clear_explicit(volatile atomic_flag* Flag, memory_order Order) noexcept;
inline void atomic_flag_clear_explicit(atomic_flag* Flag, memory_order Order) noexcept;
```

### <a name="parameters"></a>Parametreler

*Bayrak*\
`atomic_flag` nesnesine yönelik bir işaretçi.

*Sipariş*\
Bir [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

## <a name="atomic_flag_test_and_set"></a>atomic_flag_test_and_set

Bir [atomic_flag](../standard-library/atomic-flag-structure.md) nesnesindeki **bool** bayrağını, `memory_order_seq_cst`[memory_order](../standard-library/atomic-enums.md#memory_order_enum)kısıtlamaları içinde **true**olarak ayarlar.

```cpp
inline bool atomic_flag_test_and_set(volatile atomic_flag* Flag,) noexcept;
inline bool atomic_flag_test_and_set(atomic_flag* Flag,) noexcept;
```

### <a name="parameters"></a>Parametreler

*Bayrak*\
`atomic_flag` nesnesine yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

*Bayrağın*başlangıç değeri.

## <a name="atomic_flag_test_and_set_explicit"></a>atomic_flag_test_and_set_explicit

[Atomic_flag](../standard-library/atomic-flag-structure.md) nesnesindeki **bool** bayrağını, belirtilen [memory_order](../standard-library/atomic-enums.md#memory_order_enum) kısıtlamalarında **true**olarak ayarlar.

```cpp
inline bool atomic_flag_test_and_set_explicit(volatile atomic_flag* Flag, memory_order Order) noexcept;
inline bool atomic_flag_test_and_set_explicit(atomic_flag* Flag, memory_order Order) noexcept;
```

### <a name="parameters"></a>Parametreler

*Bayrak*\
`atomic_flag` nesnesine yönelik bir işaretçi.

*Sipariş*\
Bir [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

### <a name="return-value"></a>Dönüş Değeri

*Bayrağın*başlangıç değeri.

## <a name="atomic_init"></a>atomic_init

`atomic` nesnesindeki depolanan değeri ayarlar.

```cpp
template <class Ty>
inline void atomic_init(volatile atomic<Ty>* Atom, Ty Value) noexcept;
template <class Ty>
inline void atomic_init(atomic<Ty>* Atom, Ty Value) noexcept;
```

### <a name="parameters"></a>Parametreler

*Atom*\
`Ty`türünde bir değer depolayan `atomic` nesnesine yönelik bir işaretçi.

*Değer*\
`Ty`türünde bir değer.

### <a name="remarks"></a>Açıklamalar

`atomic_init` atomik bir işlem değil. İş parçacığı açısından güvenli değildir.

## <a name="atomic_is_lock_free"></a>atomic_is_lock_free

`atomic` nesne üzerindeki atomik işlemlerin *kilitli*olup olmadığını belirtir.

```cpp
template <class T>
inline bool atomic_is_lock_free(const volatile atomic<T>* Atom) noexcept;
template <class T>
inline bool atomic_is_lock_free(const atomic<T>* Atom) noexcept;
```

### <a name="parameters"></a>Parametreler

*Atom*\
`T`türünde bir değer depolayan `atomic` nesnesine yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

*atom* üzerinde Atomik işlemler kilitsiz ise **doğru** ; Aksi takdirde, **false**.

### <a name="remarks"></a>Açıklamalar

Bir atomik tür, bu tür üzerinde hiçbir Atomik işlem kilit kullanıyorsa kilit ücretsizdir. Bu işlev true değerini döndürürse, tür sinyal işleyicilerde kullanılmak üzere güvenlidir.

## <a name="atomic_load"></a>atomic_load

`atomic` nesnesinde depolanan değeri alır.

```cpp
template <class Ty>
inline Ty atomic_load(const volatile atomic<Ty>* Atom) noexcept;
template <class Ty>
inline Ty atomic_load(const atomic<Ty>* Atom) noexcept;
```

### <a name="parameters"></a>Parametreler

*Atom*\
`Ty`türünde bir değer içeren `atomic` nesnesine yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

*Atom*içinde depolanan alınan değer.

### <a name="remarks"></a>Açıklamalar

`atomic_load`, `memory_order_seq_cst`[memory_order](../standard-library/atomic-enums.md#memory_order_enum)örtülü olarak kullanır.

## <a name="atomic_load_explicit"></a>atomic_load_explicit

Belirtilen bir [memory_order](../standard-library/atomic-enums.md#memory_order_enum)içindeki bir `atomic` nesnesinde depolanan değeri alır.

```cpp
template <class Ty>
inline Ty atomic_load_explicit(const volatile atomic<Ty>* Atom, memory_order Order) noexcept;
template <class Ty>
inline Ty atomic_load_explicit(const atomic<Ty>* Atom, memory_order Order) noexcept;
```

### <a name="parameters"></a>Parametreler

*Atom*\
`Ty`türünde bir değer içeren `atomic` nesnesine yönelik bir işaretçi.

*Sipariş*\
Bir [memory_order](../standard-library/atomic-enums.md#memory_order_enum). `memory_order_release` veya `memory_order_acq_rel`kullanmayın.

### <a name="return-value"></a>Dönüş Değeri

*Atom*içinde depolanan alınan değer.

## <a name="atomic_signal_fence"></a>atomic_signal_fence

Aynı iş parçacığında yürütülen sinyal işleyicilerine sahip bir çağıran iş parçacığındaki diğer balıklarla, yükleme/depolama işlemleri arasında sıralamayı *zorlayan bir sınır*gibi davranır.

```cpp
inline void atomic_signal_fence(memory_order Order) noexcept;
```

### <a name="parameters"></a>Parametreler

*Sipariş*\
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
`Ty`türünde bir değer içeren atomik nesne işaretçisi.

*Değer*\
`Ty`türünde bir değer.

### <a name="remarks"></a>Açıklamalar

`atomic_store`, `memory_order_seq_cst`[memory_order](../standard-library/atomic-enums.md#memory_order_enum) kısıtlaması içinde *atom*tarafından işaret edilen nesnedeki *değeri* depolar.

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
`Ty`türünde bir değer içeren `atomic` nesnesine yönelik bir işaretçi.

*Değer*\
`Ty`türünde bir değer.

*Sipariş*\
Bir [memory_order](../standard-library/atomic-enums.md#memory_order_enum). `memory_order_consume`, `memory_order_acquire`veya `memory_order_acq_rel`kullanmayın.

### <a name="remarks"></a>Açıklamalar

`atomic_store` *değeri* , *sıralamada*belirtilen `memory_order` içinde *atom*tarafından işaret edilen nesnede depolar.

## <a name="atomic_thread_fence"></a>atomic_thread_fence

İlişkili bir atomik işlem olmadan, yük/depolama işlemleri arasında sıralamayı zorlayan bir bellek eşitleme temel alanı olan bir *çit*gibi davranır.

```cpp
inline void atomic_thread_fence(memory_order Order) noexcept;
```

### <a name="parameters"></a>Parametreler

*Sipariş*\
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

*Bağımsız değişken*\
`Ty`türünde bir değer.

### <a name="return-value"></a>Dönüş Değeri

Dönüş değeri *bağımsız değişken*. *Bağımsız değişken* değerlendirmesi, işlev çağrısına bir bağımlılık taşımaz. Olası bir bağımlılık zincirini bozarak, işlev derleyicinin daha verimli kod oluşturmasına izin verebilir.

## <a name="see-also"></a>Ayrıca bkz.

[\<atomik >](../standard-library/atomic.md)
