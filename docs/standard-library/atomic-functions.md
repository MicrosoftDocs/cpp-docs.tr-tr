---
title: '&lt;atomik&gt; fonksiyonlar'
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
ms.openlocfilehash: b6d03da446e4a3bae02f662e5b106bd5de534d0a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376895"
---
# <a name="ltatomicgt-functions"></a>&lt;atomik&gt; fonksiyonlar

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

## <a name="atomic_compare_exchange_strong"></a><a name="atomic_compare_exchange_strong"></a>atomic_compare_exchange_strong

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
Bir tür `Ty`değerini depolayan *bir atomik* nesneye işaretçi.

*Exp*\
Türünde `Ty`bir değer için bir işaretçi .

*Değer*\
Türübir `Ty`değer.

### <a name="return-value"></a>Dönüş Değeri

değerler eşitse **doğru,** aksi takdirde **yanlış**.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, örtülü `memory_order_seq_cst` [memory_order](../standard-library/atomic-enums.md#memory_order_enum) bağımsız değişkenleri kullanarak bir atomik karşılaştırma ve değişim işlemi gerçekleştirir. Daha fazla bilgi için [atomic_compare_exchange_strong_explicit.](../standard-library/atomic-functions.md#atomic_compare_exchange_strong_explicit)

## <a name="atomic_compare_exchange_strong_explicit"></a><a name="atomic_compare_exchange_strong_explicit"></a>atomic_compare_exchange_strong_explicit

Atomik *karşılaştırma ve değişim* işlemi gerçekleştirir.

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
Türünde `Ty`bir `atomic` değer depolayan bir nesneye işaretçi.

*Exp*\
Türünde `Ty`bir değer için bir işaretçi .

*Değer*\
Türübir `Ty`değer.

*Sipariş1*\
İlk [memory_order](../standard-library/atomic-enums.md#memory_order_enum) tartışma.

*Sipariş2*\
İkinci `memory_order` tartışma. *Order2'nin* değeri, `memory_order_release` `memory_order_acq_rel` *Sipariş1*değerinden daha güçlü olamaz veya olamaz.

### <a name="return-value"></a>Dönüş Değeri

değerler eşitse **doğru,** aksi takdirde **yanlış**.

### <a name="remarks"></a>Açıklamalar

*Atomik karşılaştırma ve değişim işlemi,* *Atom* tarafından işaret edilen nesnede depolanan değeri *Exp'nin*işaret ettiği değerle karşılaştırır. Değerler eşitse, *atom* tarafından işaret edilen nesnede depolanan değer, bir *Value* `read-modify-write` işlem kullanılarak ve *Order1*tarafından belirtilen bellek sırası kısıtlamaları uygulanarak Değer ile değiştirilir. Değerler eşit değilse, işlem *Exp* tarafından işaret edilen değeri *Atom* tarafından işaret edilen nesnede depolanan değerle değiştirir ve *Order2*tarafından belirtilen bellek sırası kısıtlamalarını uygular.

## <a name="atomic_compare_exchange_weak"></a><a name="atomic_compare_exchange_weak"></a>atomic_compare_exchange_weak

Zayıf bir *atomik karşılaştırma ve değişim* işlemi gerçekleştirir.

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
Türünde `Ty`bir `atomic` değer depolayan bir nesneye işaretçi.

*Exp*\
Türünde `Ty`bir değer için bir işaretçi .

*Değer*\
Türübir `Ty`değer.

### <a name="return-value"></a>Dönüş Değeri

değerler eşitse **doğru,** aksi takdirde **yanlış**.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, örtülü `memory_order_seq_cst` [memory_order](../standard-library/atomic-enums.md#memory_order_enum) bağımsız değişkenleri olan zayıf bir atomik karşılaştırma ve değişim *işlemi* gerçekleştirir. Daha fazla bilgi için [atomic_compare_exchange_weak_explicit.](../standard-library/atomic-functions.md#atomic_compare_exchange_weak_explicit)

## <a name="atomic_compare_exchange_weak_explicit"></a><a name="atomic_compare_exchange_weak_explicit"></a>atomic_compare_exchange_weak_explicit

Zayıf bir *atomik karşılaştırma ve değişim* işlemi gerçekleştirir.

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
Türünde `Ty`bir `atomic` değer depolayan bir nesneye işaretçi.

*Exp*\
Türünde `Ty`bir değer için bir işaretçi .

*Değer*\
Türübir `Ty`değer.

*Sipariş1*\
İlk [memory_order](../standard-library/atomic-enums.md#memory_order_enum) tartışma.

*Sipariş2*\
İkinci `memory_order` tartışma. *Order2'nin* değeri, `memory_order_release` `memory_order_acq_rel` *Sipariş1'in*değerinden daha güçlü olamaz veya olamaz.

### <a name="return-value"></a>Dönüş Değeri

değerler eşitse **doğru,** aksi takdirde **yanlış**.

### <a name="remarks"></a>Açıklamalar

Bir atomik karşılaştırma ve *değişim işlemi* hem güçlü ve zayıf tatlar beklenen ve geçerli değerler eşit değilse yeni değeri depolamak olmadığını garanti eder. Güçlü lezzet, beklenen ve geçerli değerler eşitse yeni değeri depolayabacağını garanti eder. Zayıf tat bazen **yanlış** döndürebilir ve geçerli ve beklenen değerler eşit olsa bile yeni değeri depolamayabilir. Başka bir deyişle, işlev **yanlış**döndürecek, ancak beklenen değerin daha sonraki bir incelemesi değişmediğini ve bu nedenle eşit olarak karşılaştırılması gerektiğini ortaya çıkarabilir.

## <a name="atomic_exchange"></a><a name="atomic_exchange"></a>atomic_exchange

*Atomun*depolanan değerini değiştirmek için *Değer'i* kullanır.

```cpp
template <class T>
inline Ty atomic_exchange(volatile atomic<Ty>* _Atom, Ty Value) noexcept;

template <class Ty>
inline T atomic_exchange(atomic<Ty>* Atom, Ty Value) noexcept;
```

### <a name="parameters"></a>Parametreler

*Atom*\
Türünde `Ty`bir `atomic` değer depolayan bir nesneye işaretçi.

*Değer*\
Türübir `Ty`değer.

### <a name="return-value"></a>Dönüş Değeri

Değişimden önce *Atom'un* depolanan değeri.

### <a name="remarks"></a>Açıklamalar

`atomic_exchange` İşlev, `read-modify-write` `memory_order_seq_cst` [memory_order](../standard-library/atomic-enums.md#memory_order_enum)kullanarak *Atom'da* *Depolanan Değeri Değer*ile değiştirmek için bir işlem gerçekleştirir.

## <a name="atomic_exchange_explicit"></a><a name="atomic_exchange_explicit"></a>atomic_exchange_explicit

*Atomun* depolanan değerini *Değer*ile değiştirir.

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
Türünde `Ty`bir `atomic` değer depolayan bir nesneye işaretçi.

*Değer*\
Türübir `Ty`değer.

*Sipariş*\
Bir [memory_order.](../standard-library/atomic-enums.md#memory_order_enum)

### <a name="return-value"></a>Dönüş Değeri

Değişimden önce *Atom'un* depolanan değeri.

### <a name="remarks"></a>Açıklamalar

`atomic_exchange_explicit` İşlev, `read-modify-write` *Atom'da*Depolanan *Değeri,* *Atom* Sipariş tarafından belirtilen bellek kısıtlamaları içinde değiş tokuş etmek için bir işlem gerçekleştirir.

## <a name="atomic_fetch_add"></a><a name="atomic_fetch_add"></a>atomic_fetch_add

Bir `atomic` nesnede depolanan varolan bir değere değer ekler.

```cpp
template <class T>
T* atomic_fetch_add(volatile atomic<T*>* Atom, ptrdiff_t Value) noexcept;
template <class T>
T* atomic_fetch_add(atomic<T*>* Atom, ptrdiff_t Value) noexcept;
```

### <a name="parameters"></a>Parametreler

*Atom*\
Bir işaretçiyi yazmak `atomic` `T`için depolayan bir nesneye işaretçi.

*Değer*\
Türübir `ptrdiff_t`değer.

### <a name="return-value"></a>Dönüş Değeri

İşlem gerçekleştirilmeden hemen önce atomik nesnetarafından bulunan işaretçinin değeri.

### <a name="remarks"></a>Açıklamalar

İşlev, `atomic_fetch_add` `read-modify-write` [memory_order](../standard-library/atomic-enums.md#memory_order_enum) kısıtlamasını kullanarak `memory_order_seq_cst` *Atom'da*depolanan değere atomik olarak *Değer* eklemek için bir işlem gerçekleştirir.

Atomik tür olduğunda, `atomic_address` *Değer* `ptrdiff_t` türü vardır ve işlem depolanan `char *`işaretçiyi .

Bu işlem, integral türleri için de aşırı yüklenir:

```cpp
integral atomic_fetch_add(volatile atomic-integral* Atom, integral Value) noexcept;

integral atomic_fetch_add(atomic-integral* Atom, integral Value) noexcept;
```

## <a name="atomic_fetch_add_explicit"></a><a name="atomic_fetch_add_explicit"></a>atomic_fetch_add_explicit

Bir `atomic` nesnede depolanan varolan bir değere değer ekler.

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
Bir işaretçiyi yazmak `atomic` `T`için depolayan bir nesneye işaretçi.

*Değer*\
Türübir `ptrdiff_t`değer.

### <a name="return-value"></a>Dönüş Değeri

İşlem gerçekleştirilmeden hemen önce atomik nesnetarafından bulunan işaretçinin değeri.

### <a name="remarks"></a>Açıklamalar

İşlev, `atomic_fetch_add_explicit` `read-modify-write` *atomda*depolanan değere atomik olarak *değer* eklemek için bir işlem `Order`gerçekleştirir , tarafından belirtilen [memory_order](../standard-library/atomic-enums.md#memory_order_enum) kısıtlamaları içinde .

Atomik türü `atomic_address`olduğunda, `Value` türü `ptrdiff_t` vardır ve işlem depolanan işaretçiyi . `char *`

Bu işlem, integral türleri için de aşırı yüklenir:

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

## <a name="atomic_fetch_and"></a><a name="atomic_fetch_and"></a>atomic_fetch_and

Bir değer `and` ve bir `atomic` nesnede depolanan varolan bir değer üzerinde biraz akıllıca gerçekleştirir.

```cpp
template <class T>
inline T atomic_fetch_and(volatile atomic<T>* Atom, T Value) noexcept;
template <class T>
inline T atomic_fetch_and(volatile atomic<T>* Atom, T Value) noexcept;
```

### <a name="parameters"></a>Parametreler

*Atom*\
Türünde `T`bir `atomic` değer depolayan bir nesneye işaretçi.

*Değer*\
Türübir `T`değer.

### <a name="return-value"></a>Dönüş Değeri

İşlem gerçekleştirilmeden hemen önce atomik nesnenin içerdiği değer.

### <a name="remarks"></a>Açıklamalar

İşlev, `atomic_fetch_and` `read-modify-write` [atomun](../standard-library/atomic-enums.md#memory_order_enum) depolanan değerini, memory_order kısıtlamasını `and` kullanarak, `memory_order_seq_cst`Atom'da depolanan bir değer *ve* atomda depolanan geçerli değer *le* değiştirmek için bir işlem gerçekleştirir. *Atom*

## <a name="atomic_fetch_and_explicit"></a><a name="atomic_fetch_and_explicit"></a>atomic_fetch_and_explicit

Bir değerin `and` ve bir `atomic` nesnede depolanan varolan bir değerin bitwise gerçekleştirir.

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
Türünde `T`bir `atomic` değer depolayan bir nesneye işaretçi.

*Değer*\
Türübir `T`değer.

*Sipariş*\
Bir [memory_order.](../standard-library/atomic-enums.md#memory_order_enum)

### <a name="return-value"></a>Dönüş Değeri

İşlem gerçekleştirilmeden hemen önce atomik nesnenin içerdiği değer.

### <a name="remarks"></a>Açıklamalar

İşlev, `atomic_fetch_and_explicit` `read-modify-write` *Atom'un* depolanan değerini, *Sipariş*tarafından `and` *Value* belirtilen bellek kısıtlamaları içinde, Atom'da depolanan bir değer ve atomda depolanan geçerli değer ile değiştirmek için bir işlem gerçekleştirir. *Atom*

## <a name="atomic_fetch_or"></a><a name="atomic_fetch_or"></a>atomic_fetch_or

Bir değer `or` ve bir `atomic` nesnede depolanan varolan bir değer üzerinde biraz akıllıca gerçekleştirir.

```cpp
template <class T>
inline T atomic_fetch_or (volatile atomic<T>* Atom, T Value) noexcept;
template <class T>
inline T atomic_fetch_or (volatile atomic<T>* Atom, T Value) noexcept;
```

### <a name="parameters"></a>Parametreler

*Atom*\
Türünde `T`bir `atomic` değer depolayan bir nesneye işaretçi.

*Değer*\
Türübir `T`değer.

### <a name="return-value"></a>Dönüş Değeri

İşlem gerçekleştirilmeden hemen önce atomik nesnenin içerdiği değer.

### <a name="remarks"></a>Açıklamalar

`atomic_fetch_or` İşlev, `read-modify-write` [atomun](../standard-library/atomic-enums.md#memory_order_enum)depolanan değerini bir bitwise `or` *değeri* ve *Atom'da*depolanan geçerli değeri *ile* değiştirmek için bir işlem gerçekleştirir , memory_order kullanarak `memory_order_seq_cst`.

## <a name="atomic_fetch_or_explicit"></a><a name="atomic_fetch_or_explicit"></a>atomic_fetch_or_explicit

Bir değer `or` ve bir `atomic` nesnede depolanan varolan bir değer üzerinde biraz akıllıca gerçekleştirir.

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
Türünde `T`bir `atomic` değer depolayan bir nesneye işaretçi.

*Değer*\
Türübir `T`değer.

*Sipariş*\
Bir [memory_order.](../standard-library/atomic-enums.md#memory_order_enum)

### <a name="return-value"></a>Dönüş Değeri

İşlem gerçekleştirilmeden hemen önce atomik nesnenin içerdiği değer.

### <a name="remarks"></a>Açıklamalar

`atomic_fetch_or_explicit` İşlev, `read-modify-write` *Atom'un* depolanan değerini, *Sipariş*tarafından `or` belirtilen [memory_order](../standard-library/atomic-enums.md#memory_order_enum) kısıtlamaları içinde, Atom'da depolanan bir değer *ve* *atomda*depolanan geçerli değer ile değiştirmek için bir işlem gerçekleştirir.

## <a name="atomic_fetch_sub"></a><a name="atomic_fetch_sub"></a>atomic_fetch_sub

Bir `atomic` nesnede depolanan varolan bir değerden bir değer çıkarır.

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
Bir işaretçiyi yazmak `atomic` `T`için depolayan bir nesneye işaretçi.

*Değer*\
Türübir `ptrdiff_t`değer.

### <a name="return-value"></a>Dönüş Değeri

İşlem gerçekleştirilmeden hemen önce atomik nesnetarafından bulunan işaretçinin değeri.

### <a name="remarks"></a>Açıklamalar

İşlev, `atomic_fetch_sub` `read-modify-write` [memory_order](../standard-library/atomic-enums.md#memory_order_enum) kısıtlamasını kullanarak `memory_order_seq_cst` *Atom'da*depolanan değerden *Değeri* atomik olarak çıkarmak için bir işlem gerçekleştirir.

Atomik tür olduğunda, `atomic_address` *Değer* `ptrdiff_t` türü vardır ve işlem depolanan `char *`işaretçiyi .

Bu işlem, integral türleri için de aşırı yüklenir:

```cpp
integral atomic_fetch_sub(volatile atomic-integral* Atom, integral Value) noexcept;
integral atomic_fetch_sub(atomic-integral* Atom, integral Value) noexcept;
```

## <a name="atomic_fetch_sub_explicit"></a><a name="atomic_fetch_sub_explicit"></a>atomic_fetch_sub_explicit

Bir `atomic` nesnede depolanan varolan bir değerden bir değer çıkarır.

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
Bir işaretçiyi yazmak `atomic` `T`için depolayan bir nesneye işaretçi.

*Değer*\
Türübir `ptrdiff_t`değer.

### <a name="return-value"></a>Dönüş Değeri

İşlem gerçekleştirilmeden hemen önce atomik nesnetarafından bulunan işaretçinin değeri.

### <a name="remarks"></a>Açıklamalar

İşlev, `atomic_fetch_sub_explicit` `read-modify-write` *Atom'da*depolanan değerden *değeri* atomik olarak çıkarmak için bir işlem `Order`gerçekleştirir , tarafından belirtilen [memory_order](../standard-library/atomic-enums.md#memory_order_enum) kısıtlamaları içinde .

Atomik tür olduğunda, `atomic_address` *Değer* `ptrdiff_t` türü vardır ve işlem depolanan `char *`işaretçiyi .

Bu işlem, integral türleri için de aşırı yüklenir:

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

## <a name="atomic_fetch_xor"></a><a name="atomic_fetch_xor"></a>atomic_fetch_xor

Bir değer `exclusive or` ve bir `atomic` nesnede depolanan varolan bir değer üzerinde biraz akıllıca gerçekleştirir.

```cpp
template <class T>
inline T atomic_fetch_xor(volatile atomic<T>* Atom, T Value) noexcept;

template <class T>
inline T atomic_fetch_xor(volatile atomic<T>* Atom, T Value) noexcept;
```

### <a name="parameters"></a>Parametreler

*Atom*\
Türünde `T`bir `atomic` değer depolayan bir nesneye işaretçi.

*Değer*\
Türübir `T`değer.

### <a name="return-value"></a>Dönüş Değeri

İşlem gerçekleştirilmeden hemen önce atomik nesnenin içerdiği değer.

### <a name="remarks"></a>Açıklamalar

`atomic_fetch_xor` İşlev, `read-modify-write` [atomun](../standard-library/atomic-enums.md#memory_order_enum)depolanan değerini bir bitwise `exclusive or` *değeri* ve *Atom'da*depolanan geçerli değeri *ile* değiştirmek için bir işlem gerçekleştirir , memory_order kullanarak `memory_order_seq_cst`.

## <a name="atomic_fetch_xor_explicit"></a><a name="atomic_fetch_xor_explicit"></a>atomic_fetch_xor_explicit

Bir değer `exclusive or` ve bir `atomic` nesnede depolanan varolan bir değer üzerinde biraz akıllıca gerçekleştirir.

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
Türünde `T`bir `atomic` değer depolayan bir nesneye işaretçi.

*Değer*\
Türübir `T`değer.

*Sipariş*\
Bir [memory_order.](../standard-library/atomic-enums.md#memory_order_enum)

### <a name="return-value"></a>Dönüş Değeri

İşlem gerçekleştirilmeden hemen önce atomik nesnenin içerdiği değer.

### <a name="remarks"></a>Açıklamalar

İşlev, `atomic_fetch_xor_explicit` `read-modify-write` *Atom'un* depolanan değerini, *Düzen* tarafından `exclusive or` belirtilen [memory_order](../standard-library/atomic-enums.md#memory_order_enum) kısıtlamaları içinde, Atom'da depolanan bir değer ve *Order* *Atom'da*depolanan geçerli değer ile değiştirmek için bir işlem gerçekleştirir.

## <a name="atomic_flag_clear"></a><a name="atomic_flag_clear"></a>atomic_flag_clear

Bool bayrağını [atomic_flag](../standard-library/atomic-flag-structure.md) bir nesnedeki **bool** bayrağını [memory_order](../standard-library/atomic-enums.md#memory_order_enum)içinde `memory_order_seq_cst` **, yanlış**bir nesneye ayarlar.

```cpp
inline void atomic_flag_clear(volatile atomic_flag* Flag) noexcept;
inline void atomic_flag_clear(atomic_flag* Flag) noexcept;
```

### <a name="parameters"></a>Parametreler

*Bayrak*\
Bir `atomic_flag` nesneye işaretçi.

## <a name="atomic_flag_clear_explicit"></a><a name="atomic_flag_clear_explicit"></a>atomic_flag_clear_explicit

Bool bayrağını [atomic_flag](../standard-library/atomic-flag-structure.md) bir nesnedeki **bool** bayrağını belirtilen [memory_order](../standard-library/atomic-enums.md#memory_order_enum) kısıtlamaları içinde **false'a**ayarlar.

```cpp
inline void atomic_flag_clear_explicit(volatile atomic_flag* Flag, memory_order Order) noexcept;
inline void atomic_flag_clear_explicit(atomic_flag* Flag, memory_order Order) noexcept;
```

### <a name="parameters"></a>Parametreler

*Bayrak*\
Bir `atomic_flag` nesneye işaretçi.

*Sipariş*\
Bir [memory_order.](../standard-library/atomic-enums.md#memory_order_enum)

## <a name="atomic_flag_test_and_set"></a><a name="atomic_flag_test_and_set"></a>atomic_flag_test_and_set

bool **bool** bayrağını [atomic_flag](../standard-library/atomic-flag-structure.md) bir nesnenin [içinde, memory_order](../standard-library/atomic-enums.md#memory_order_enum) **true**kısıtlamaları `memory_order_seq_cst`içinde ayarlar.

```cpp
inline bool atomic_flag_test_and_set(volatile atomic_flag* Flag,) noexcept;
inline bool atomic_flag_test_and_set(atomic_flag* Flag,) noexcept;
```

### <a name="parameters"></a>Parametreler

*Bayrak*\
Bir `atomic_flag` nesneye işaretçi.

### <a name="return-value"></a>Dönüş Değeri

*Bayrağın*başlangıç değeri.

## <a name="atomic_flag_test_and_set_explicit"></a><a name="atomic_flag_test_and_set_explicit"></a>atomic_flag_test_and_set_explicit

Bool bayrağını [atomic_flag](../standard-library/atomic-flag-structure.md) bir nesnedeki **bool** bayrağını belirtilen [memory_order](../standard-library/atomic-enums.md#memory_order_enum) kısıtlamaları içinde **doğru**olarak ayarlar.

```cpp
inline bool atomic_flag_test_and_set_explicit(volatile atomic_flag* Flag, memory_order Order) noexcept;
inline bool atomic_flag_test_and_set_explicit(atomic_flag* Flag, memory_order Order) noexcept;
```

### <a name="parameters"></a>Parametreler

*Bayrak*\
Bir `atomic_flag` nesneye işaretçi.

*Sipariş*\
Bir [memory_order.](../standard-library/atomic-enums.md#memory_order_enum)

### <a name="return-value"></a>Dönüş Değeri

*Bayrağın*başlangıç değeri.

## <a name="atomic_init"></a><a name="atomic_init"></a>atomic_init

Depolanan değeri bir `atomic` nesnede ayarlar.

```cpp
template <class Ty>
inline void atomic_init(volatile atomic<Ty>* Atom, Ty Value) noexcept;
template <class Ty>
inline void atomic_init(atomic<Ty>* Atom, Ty Value) noexcept;
```

### <a name="parameters"></a>Parametreler

*Atom*\
Türünde `Ty`bir `atomic` değer depolayan bir nesneye işaretçi.

*Değer*\
Türübir `Ty`değer.

### <a name="remarks"></a>Açıklamalar

`atomic_init`atomik bir işlem değildir. İş parçacığı güvenli değildir.

## <a name="atomic_is_lock_free"></a><a name="atomic_is_lock_free"></a>atomic_is_lock_free

Bir `atomic` nesneüzerindeki atomik işlemlerin *kilitsiz*olup olmadığını belirtir.

```cpp
template <class T>
inline bool atomic_is_lock_free(const volatile atomic<T>* Atom) noexcept;
template <class T>
inline bool atomic_is_lock_free(const atomic<T>* Atom) noexcept;
```

### <a name="parameters"></a>Parametreler

*Atom*\
Türünde `T`bir `atomic` değer depolayan bir nesneye işaretçi.

### <a name="return-value"></a>Dönüş Değeri

*Atom'daki* atomik işlemler kilitsiz ise **doğrudur;** aksi takdirde, **yanlış**.

### <a name="remarks"></a>Açıklamalar

Atomik tür, bu tür kullanım kilitleri üzerinde atomik işlemler yoksa kilitsizdir. Bu işlev doğru döndürürse, tür sinyal işleyicilerinde kullanımı güvenlidir.

## <a name="atomic_load"></a><a name="atomic_load"></a>atomic_load

Bir `atomic` nesnede depolanan değeri alır.

```cpp
template <class Ty>
inline Ty atomic_load(const volatile atomic<Ty>* Atom) noexcept;
template <class Ty>
inline Ty atomic_load(const atomic<Ty>* Atom) noexcept;
```

### <a name="parameters"></a>Parametreler

*Atom*\
Türü `Ty`nde `atomic` değer içeren bir nesneye işaretçi.

### <a name="return-value"></a>Dönüş Değeri

*Atom'da*depolanan alınan değer.

### <a name="remarks"></a>Açıklamalar

`atomic_load`örtülü olarak `memory_order_seq_cst` [memory_order](../standard-library/atomic-enums.md#memory_order_enum)kullanır.

## <a name="atomic_load_explicit"></a><a name="atomic_load_explicit"></a>atomic_load_explicit

Depolanan değeri, belirli `atomic` bir [memory_order](../standard-library/atomic-enums.md#memory_order_enum)içinde bir nesnede alır.

```cpp
template <class Ty>
inline Ty atomic_load_explicit(const volatile atomic<Ty>* Atom, memory_order Order) noexcept;
template <class Ty>
inline Ty atomic_load_explicit(const atomic<Ty>* Atom, memory_order Order) noexcept;
```

### <a name="parameters"></a>Parametreler

*Atom*\
Türü `Ty`nde `atomic` değer içeren bir nesneye işaretçi.

*Sipariş*\
Bir [memory_order.](../standard-library/atomic-enums.md#memory_order_enum) Kullanmayın `memory_order_release` veya `memory_order_acq_rel`.

### <a name="return-value"></a>Dönüş Değeri

*Atom'da*depolanan alınan değer.

## <a name="atomic_signal_fence"></a><a name="atomic_signal_fence"></a>atomic_signal_fence

Aynı iş parçacığı içinde yürütülen sinyal işleyicileri olan bir arama iş parçacığı diğer çitler arasında yük / depo işlemleri arasında sipariş zorlar bir bellek senkronizasyon ilkel bir *çit*gibi davranır.

```cpp
inline void atomic_signal_fence(memory_order Order) noexcept;
```

### <a name="parameters"></a>Parametreler

*Sipariş*\
Çit türünü belirleyen bir bellek sıralama kısıtlaması.

### <a name="remarks"></a>Açıklamalar

*Sipariş* bağımsız değişkeni çit türünü belirler.

|||
|-|-|
|`memory_order_relaxed`|Çitin bir etkisi yok.|
|`memory_order_consume`|Çit bir edinme çitidir.|
|`memory_order_acquire`|Çit bir edinme çitidir.|
|`memory_order_release`|Çit bir serbest bırakma çiti.|
|`memory_order_acq_rel`|Çit hem bir edinme çit ve bir serbest bırakma çit.|
|`memory_order_seq_cst`|Çit hem bir edinme çit ve bir serbest bırakma çit, ve sırayla tutarlıdır.|

## <a name="atomic_store"></a><a name="atomic_store"></a>atomic_store

Atomik olarak bir değeri atomik bir nesnede depolar.

```cpp
template <class Ty>
inline Ty atomic_store_explicit(const volatile atomic<Ty>* Atom, Ty Value) noexcept;
template <class Ty>
inline Ty atomic_store_explicit(const atomic<Ty>* Atom, T Value) noexcept;
```

### <a name="parameters"></a>Parametreler

*Atom*\
Türünde `Ty`bir değer içeren bir atomik nesneye işaretçi.

*Değer*\
Türübir `Ty`değer.

### <a name="remarks"></a>Açıklamalar

`atomic_store`*Atom*tarafından işaret edilen nesnedeki `memory_order_seq_cst` [Değeri, memory_order](../standard-library/atomic-enums.md#memory_order_enum) kısıtlaması içinde depolar. *Value*

## <a name="atomic_store_explicit"></a><a name="atomic_store_explicit"></a>atomic_store_explicit

Atomik olarak bir değeri atomik bir nesnede depolar.

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
Türü `Ty`nde `atomic` değer içeren bir nesneye işaretçi.

*Değer*\
Türübir `Ty`değer.

*Sipariş*\
Bir [memory_order.](../standard-library/atomic-enums.md#memory_order_enum) Kullanmayın, `memory_order_consume` `memory_order_acquire`veya `memory_order_acq_rel`.

### <a name="remarks"></a>Açıklamalar

`atomic_store`*Atom*tarafından işaret edilen nesnedeki *Değeri,* `memory_order` *Sipariş*tarafından belirtilen nesne içinde depolar.

## <a name="atomic_thread_fence"></a><a name="atomic_thread_fence"></a>atomic_thread_fence

Bir *çit*gibi davranır -hangi bir bellek senkronizasyon ilkel yük / depo işlemleri arasında sipariş zorlar- ilişkili bir atomik işlem olmadan.

```cpp
inline void atomic_thread_fence(memory_order Order) noexcept;
```

### <a name="parameters"></a>Parametreler

*Sipariş*\
Çit türünü belirleyen bir bellek sıralama kısıtlaması.

### <a name="remarks"></a>Açıklamalar

*Sipariş* bağımsız değişkeni çit türünü belirler.

|||
|-|-|
|`memory_order_relaxed`|Çitin bir etkisi yok.|
|`memory_order_consume`|Çit bir edinme çitidir.|
|`memory_order_acquire`|Çit bir edinme çitidir.|
|`memory_order_release`|Çit bir serbest bırakma çiti.|
|`memory_order_acq_rel`|Çit hem bir edinme çit ve bir serbest bırakma çit.|
|`memory_order_seq_cst`|Çit hem bir edinme çit ve bir serbest bırakma çit, ve sırayla tutarlıdır.|

## <a name="kill_dependency"></a><a name="kill_dependency"></a>kill_dependency

Bir bağımlılığı kaldırır.

```cpp
template <class Ty>
Ty kill_dependency(Ty Arg) noexcept;
```

### <a name="parameters"></a>Parametreler

*Arg*\
Türübir `Ty`değer.

### <a name="return-value"></a>Dönüş Değeri

İade değeri *Arg'dır.* *Arg'ın* değerlendirilmesi işlev çağrısına bir bağımlılık taşımaz. Olası bir bağımlılık zincirini kırarak, işlev derleyicinin daha verimli kod oluşturmasına izin verebilir.

## <a name="see-also"></a>Ayrıca bkz.

[\<atomik>](../standard-library/atomic.md)
