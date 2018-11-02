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
ms.openlocfilehash: 6ec4ff879b70e4d2cc16a3328217660db695e859
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50533763"
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

## <a name="atomic_compare_exchange_strong"></a>  atomic_compare_exchange_strong

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

*Atom*<br/>
Bir işaretçi bir *atomik* türünde bir değer depolar nesne `Ty`.

*exp*<br/>
Bir değer türünün işaretçisi `Ty`.

*Değer*<br/>
Türünde bir değer `Ty`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** aksi değerler eşitse, **false**.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi kullanarak bir atomik karşılaştırma ve değişim işlemi gerçekleştirir. `memory_order_seq_cst` [memory_order](../standard-library/atomic-enums.md#memory_order_enum) bağımsız değişkenler. Daha fazla bilgi için [atomic_compare_exchange_strong_explicit](../standard-library/atomic-functions.md#atomic_compare_exchange_strong_explicit).

## <a name="atomic_compare_exchange_strong_explicit"></a>  atomic_compare_exchange_strong_explicit

Gerçekleştiren bir *atomik karşılaştırma ve değişim* işlemi.

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

*Atom*<br/>
Bir işaretçi bir `atomic` türünde bir değer depolar nesne `Ty`.

*exp*<br/>
Bir değer türünün işaretçisi `Ty`.

*Değer*<br/>
Türünde bir değer `Ty`.

*Order1*<br/>
İlk [memory_order](../standard-library/atomic-enums.md#memory_order_enum) bağımsız değişken.

*Order2*<br/>
İkinci `memory_order` bağımsız değişken. Değerini *Order2* olamaz `memory_order_release` veya `memory_order_acq_rel`, değerinden daha güçlü olamaz *Order1*.

### <a name="return-value"></a>Dönüş Değeri

**doğru** aksi değerler eşitse, **false**.

### <a name="remarks"></a>Açıklamalar

Bir *atomik karşılaştırma ve değişim işlemi* tarafından işaret edilen nesnede depolanan değeri karşılaştırır *Atom* tarafından işaret edilen değere karşı *Exp*. Değerler eşit, tarafından işaret edilen nesnede depolanan değeri *atom* ile değiştirilir *değer* kullanarak bir `read-modify-write` işlemi ve olan bellek sırası kısıtlamalarını uygulayarak tarafından belirtilen *Order1*. Değerler eşit değilse işlem tarafından işaret edilen değerin yerini alır *Exp* tarafından işaret edilen nesnede depolanan değeri *Atom* olan bellek sırası kısıtlamalarını uygular. tarafından belirtilen *Order2*.

## <a name="atomic_compare_exchange_weak"></a>  atomic_compare_exchange_weak

Gerçekleştiren bir *zayıf atomik karşılaştırma ve exchange* işlemi.

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

*Atom*<br/>
Bir işaretçi bir `atomic` türünde bir değer depolar nesne `Ty`.

*exp*<br/>
Bir değer türünün işaretçisi `Ty`.

*Değer*<br/>
Türünde bir değer `Ty`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** aksi değerler eşitse, **false**.

### <a name="remarks"></a>Açıklamalar

Bu yöntem gerçekleştiren bir *zayıf atomik karşılaştırma ve exchange işlemi* olan `memory_order_seq_cst` [memory_order](../standard-library/atomic-enums.md#memory_order_enum) bağımsız değişkenler. Daha fazla bilgi için [atomic_compare_exchange_weak_explicit](../standard-library/atomic-functions.md#atomic_compare_exchange_weak_explicit).

## <a name="atomic_compare_exchange_weak_explicit"></a>  atomic_compare_exchange_weak_explicit

Gerçekleştiren bir *zayıf atomik karşılaştırma ve exchange* işlemi.

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

*Atom*<br/>
Bir işaretçi bir `atomic` türünde bir değer depolar nesne `Ty`.

*exp*<br/>
Bir değer türünün işaretçisi `Ty`.

*Değer*<br/>
Türünde bir değer `Ty`.

*Order1*<br/>
İlk [memory_order](../standard-library/atomic-enums.md#memory_order_enum) bağımsız değişken.

*Order2*<br/>
İkinci `memory_order` bağımsız değişken. Değerini *Order2* olamaz `memory_order_release` veya `memory_order_acq_rel`, ya da değerinden daha güçlü olabilir *Order1*.

### <a name="return-value"></a>Dönüş Değeri

**doğru** aksi değerler eşitse, **false**.

### <a name="remarks"></a>Açıklamalar

Her iki güçlü ve zayıf türde bir *atomik karşılaştırma ve değişim işlemi* garantisi geçerli ve beklenen değerler eşit değilse, yeni değer depolamayın. Güçlü özellik geçerli ve beklenen değerler eşitse, yeni değer depolayacak garanti eder. Zayıf flavor bazen döndürebilir **false** ve geçerli ve beklenen değerleri eşit olsa bile, yeni bir değer değil. Diğer bir deyişle, bir işlev döndürür **false**, ancak bir sonraki beklenen değerle incelenmesi, değişmedi ve bu nedenle eşit olarak karşılaştırılır ortaya çıkarabilir.

## <a name="atomic_exchange"></a>  atomic_exchange

Kullanan *değer* depolanan değeri değiştirmek için *Atom*.

```cpp
template <class T>
inline Ty atomic_exchange(volatile atomic<Ty>* _Atom, Ty Value) noexcept;

template <class Ty>
inline T atomic_exchange(atomic<Ty>* Atom, Ty Value) noexcept;
```

### <a name="parameters"></a>Parametreler

*Atom*<br/>
Bir işaretçi bir `atomic` türünde bir değer depolar nesne `Ty`.

*Değer*<br/>
Türünde bir değer `Ty`.

### <a name="return-value"></a>Dönüş Değeri

Depolanan değeri *Atom* exchange önce.

### <a name="remarks"></a>Açıklamalar

`atomic_exchange` İşlevi gerçekleştiren bir `read-modify-write` içinde depolanmış değerle değiştirmek için işlem *Atom* ile *değer*kullanarak `memory_order_seq_cst` [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

## <a name="atomic_exchange_explicit"></a>  atomic_exchange_explicit

Depolanmış değerini değiştirir *Atom* ile *değer*.

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

*Atom*<br/>
Bir işaretçi bir `atomic` türünde bir değer depolar nesne `Ty`.

*Değer*<br/>
Türünde bir değer `Ty`.

*Sırası*<br/>
A [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

### <a name="return-value"></a>Dönüş Değeri

Depolanan değeri *Atom* exchange önce.

### <a name="remarks"></a>Açıklamalar

`atomic_exchange_explicit` İşlevi gerçekleştiren bir `read-modify-write` içinde depolanmış değerle değiştirmek için işlem *Atom* ile *değer*, tarafından belirtilen bellek kısıtlamaları dahilinde  *Sipariş*.

## <a name="atomic_fetch_add"></a>  atomic_fetch_add

Bir değeri depolanan varolan değeri ekler bir `atomic` nesne.

```cpp
template <class T>
T* atomic_fetch_add(volatile atomic<T*>* Atom, ptrdiff_t Value) noexcept;
template <class T>
T* atomic_fetch_add(atomic<T*>* Atom, ptrdiff_t Value) noexcept;
```

### <a name="parameters"></a>Parametreler

*Atom*<br/>
Bir işaretçi bir `atomic` yazmanız için bir işaretçi depolayan nesneyi `T`.

*Değer*<br/>
Türünde bir değer `ptrdiff_t`.

### <a name="return-value"></a>Dönüş Değeri

İşlem gerçekleştirilmeden hemen önce atomik nesnenin içerdiği işaretçinin değeri.

### <a name="remarks"></a>Açıklamalar

`atomic_fetch_add` İşlevi gerçekleştiren bir `read-modify-write` otomatik olarak eklemek için işlemi *değer* içinde depolanmış değere *Atom*kullanarak `memory_order_seq_cst` [memory_order](../standard-library/atomic-enums.md#memory_order_enum)kısıtlaması.

Atomik türü olduğunda `atomic_address`, *değer* türünde `ptrdiff_t` ve işlem depolanmış işaretçiyi olarak değerlendirir bir `char *`.

Bu işlem de tamsayı türleri için aşırı yüklenmiştir:

```cpp
integral atomic_fetch_add(volatile atomic-integral* Atom, integral Value) noexcept;

integral atomic_fetch_add(atomic-integral* Atom, integral Value) noexcept;
```

## <a name="atomic_fetch_add_explicit"></a>  atomic_fetch_add_explicit

Bir değeri depolanan varolan değeri ekler bir `atomic` nesne.

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

*Atom*<br/>
Bir işaretçi bir `atomic` yazmanız için bir işaretçi depolayan nesneyi `T`.

*Değer*<br/>
Türünde bir değer `ptrdiff_t`.

### <a name="return-value"></a>Dönüş Değeri

İşlem gerçekleştirilmeden hemen önce atomik nesnenin içerdiği işaretçinin değeri.

### <a name="remarks"></a>Açıklamalar

`atomic_fetch_add_explicit` İşlevi gerçekleştiren bir `read-modify-write` otomatik olarak eklemek için işlemi *değer* içinde depolanmış değere *Atom*dahilinde [memory_order](../standard-library/atomic-enums.md#memory_order_enum) kısıtlamaları tarafından belirtilen `Order`.

Atomik türü olduğunda `atomic_address`, `Value` türünde `ptrdiff_t` ve işlem depolanmış işaretçiyi olarak değerlendirir bir `char *`.

Bu işlem de tamsayı türleri için aşırı yüklenmiştir:

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

## <a name="atomic_fetch_and"></a>  atomic_fetch_and

Bit düzeyinde gerçekleştirir `and` bir değer ve depolanan varolan değeri bir `atomic` nesne.

```cpp
template <class T>
inline T atomic_fetch_and(volatile atomic<T>* Atom, T Value) noexcept;
template <class T>
inline T atomic_fetch_and(volatile atomic<T>* Atom, T Value) noexcept;
```

### <a name="parameters"></a>Parametreler

*Atom*<br/>
Bir işaretçi bir `atomic` türünde bir değer depolar nesne `T`.

*Değer*<br/>
Türünde bir değer `T`.

### <a name="return-value"></a>Dönüş Değeri

İşlem gerçekleştirilmeden hemen önce atomik nesnenin içerdiği değer.

### <a name="remarks"></a>Açıklamalar

`atomic_fetch_and` İşlevi gerçekleştiren bir `read-modify-write` depolanan değeri değiştirmek için işlem *Atom* bit düzeyinde `and` , *değer* içindedepolanmışgeçerlideğerle*Atom*kullanarak `memory_order_seq_cst` [memory_order](../standard-library/atomic-enums.md#memory_order_enum) kısıtlaması.

## <a name="atomic_fetch_and_explicit"></a>  atomic_fetch_and_explicit

Bit düzeyinde gerçekleştirir `and` bir değer ve depolanan varolan değeri bir `atomic` nesne.

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

*Atom*<br/>
Bir işaretçi bir `atomic` türünde bir değer depolar nesne `T`.

*Değer*<br/>
Türünde bir değer `T`.

*Sırası*<br/>
A [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

### <a name="return-value"></a>Dönüş Değeri

İşlem gerçekleştirilmeden hemen önce atomik nesnenin içerdiği değer.

### <a name="remarks"></a>Açıklamalar

`atomic_fetch_and_explicit` İşlevi gerçekleştiren bir `read-modify-write` depolanan değeri değiştirmek için işlem *Atom* bit düzeyinde `and` , *değer* içindedepolanmışgeçerlideğerle*Atom*, tarafından belirtilen bellek kısıtlamaları dahilinde *sipariş*.

## <a name="atomic_fetch_or"></a>  atomic_fetch_or

Bit düzeyinde gerçekleştirir `or` bir değer ve depolanan varolan değeri bir `atomic` nesne.

```cpp
template <class T>
inline T atomic_fetch_or (volatile atomic<T>* Atom, T Value) noexcept;
template <class T>
inline T atomic_fetch_or (volatile atomic<T>* Atom, T Value) noexcept;
```

### <a name="parameters"></a>Parametreler

*Atom*<br/>
Bir işaretçi bir `atomic` türünde bir değer depolar nesne `T`.

*Değer*<br/>
Türünde bir değer `T`.

### <a name="return-value"></a>Dönüş Değeri

İşlem gerçekleştirilmeden hemen önce atomik nesnenin içerdiği değer.

### <a name="remarks"></a>Açıklamalar

`atomic_fetch_or` İşlevi gerçekleştiren bir `read-modify-write` depolanan değeri değiştirmek için işlem *Atom* bit düzeyinde `or` , *değer* içindedepolanmışgeçerlideğerle*Atom*kullanarak `memory_order_seq_cst` [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

## <a name="atomic_fetch_or_explicit"></a>  atomic_fetch_or_explicit

Bit düzeyinde gerçekleştirir `or` bir değer ve depolanan varolan değeri bir `atomic` nesne.

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

*Atom*<br/>
Bir işaretçi bir `atomic` türünde bir değer depolar nesne `T`.

*Değer*<br/>
Türünde bir değer `T`.

*Sırası*<br/>
A [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

### <a name="return-value"></a>Dönüş Değeri

İşlem gerçekleştirilmeden hemen önce atomik nesnenin içerdiği değer.

### <a name="remarks"></a>Açıklamalar

`atomic_fetch_or_explicit` İşlevi gerçekleştiren bir `read-modify-write` depolanan değeri değiştirmek için işlem *Atom* bit düzeyinde `or` , *değer* içindedepolanmışgeçerlideğerle*Atom*dahilinde [memory_order](../standard-library/atomic-enums.md#memory_order_enum) tarafından belirlenen kısıtlamalar *sipariş*.

## <a name="atomic_fetch_sub"></a>  atomic_fetch_sub

Bir değeri depolanan varolan değeri çıkarır bir `atomic` nesne.

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

*Atom*<br/>
Bir işaretçi bir `atomic` yazmanız için bir işaretçi depolayan nesneyi `T`.

*Değer*<br/>
Türünde bir değer `ptrdiff_t`.

### <a name="return-value"></a>Dönüş Değeri

İşlem gerçekleştirilmeden hemen önce atomik nesnenin içerdiği işaretçinin değeri.

### <a name="remarks"></a>Açıklamalar

`atomic_fetch_sub` İşlevi gerçekleştiren bir `read-modify-write` atomik çıkartmak üzere işlem *değer* içinde depolanmış değerden *Atom*kullanarak `memory_order_seq_cst` [memory_order](../standard-library/atomic-enums.md#memory_order_enum) kısıtlaması.

Atomik türü olduğunda `atomic_address`, *değer* türünde `ptrdiff_t` ve işlem depolanmış işaretçiyi olarak değerlendirir bir `char *`.

Bu işlem de tamsayı türleri için aşırı yüklenmiştir:

```cpp
integral atomic_fetch_sub(volatile atomic-integral* Atom, integral Value) noexcept;
integral atomic_fetch_sub(atomic-integral* Atom, integral Value) noexcept;
```

## <a name="atomic_fetch_sub_explicit"></a>  atomic_fetch_sub_explicit

Bir değeri depolanan varolan değeri çıkarır bir `atomic` nesne.

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

*Atom*<br/>
Bir işaretçi bir `atomic` yazmanız için bir işaretçi depolayan nesneyi `T`.

*Değer*<br/>
Türünde bir değer `ptrdiff_t`.

### <a name="return-value"></a>Dönüş Değeri

İşlem gerçekleştirilmeden hemen önce atomik nesnenin içerdiği işaretçinin değeri.

### <a name="remarks"></a>Açıklamalar

`atomic_fetch_sub_explicit` İşlevi gerçekleştiren bir `read-modify-write` atomik çıkartmak üzere işlem *değer* içinde depolanmış değerden *Atom*dahilinde [memory_order](../standard-library/atomic-enums.md#memory_order_enum) tarafından belirtilen kısıtlamalarını `Order`.

Atomik türü olduğunda `atomic_address`, *değer* türünde `ptrdiff_t` ve işlem depolanmış işaretçiyi olarak değerlendirir bir `char *`.

Bu işlem de tamsayı türleri için aşırı yüklenmiştir:

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

## <a name="atomic_fetch_xor"></a>  atomic_fetch_xor

Bit düzeyinde gerçekleştirir `exclusive or` bir değer ve depolanan varolan değeri bir `atomic` nesne.

```cpp
template <class T>
inline T atomic_fetch_xor(volatile atomic<T>* Atom, T Value) noexcept;

template <class T>
inline T atomic_fetch_xor(volatile atomic<T>* Atom, T Value) noexcept;
```

### <a name="parameters"></a>Parametreler

*Atom*<br/>
Bir işaretçi bir `atomic` türünde bir değer depolar nesne `T`.

*Değer*<br/>
Türünde bir değer `T`.

### <a name="return-value"></a>Dönüş Değeri

İşlem gerçekleştirilmeden hemen önce atomik nesnenin içerdiği değer.

### <a name="remarks"></a>Açıklamalar

`atomic_fetch_xor` İşlevi gerçekleştiren bir `read-modify-write` depolanan değeri değiştirmek için işlem *Atom* bit düzeyinde `exclusive or` , *değer* içindedepolanmışgeçerlideğerle*Atom*kullanarak `memory_order_seq_cst` [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

## <a name="atomic_fetch_xor_explicit"></a>  atomic_fetch_xor_explicit

Bit düzeyinde gerçekleştirir `exclusive or` bir değer ve depolanan varolan değeri bir `atomic` nesne.

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

*Atom*<br/>
Bir işaretçi bir `atomic` türünde bir değer depolar nesne `T`.

*Değer*<br/>
Türünde bir değer `T`.

*Sırası*<br/>
A [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

### <a name="return-value"></a>Dönüş Değeri

İşlem gerçekleştirilmeden hemen önce atomik nesnenin içerdiği değer.

### <a name="remarks"></a>Açıklamalar

`atomic_fetch_xor_explicit` İşlevi gerçekleştiren bir `read-modify-write` depolanan değeri değiştirmek için işlem *Atom* bit düzeyinde `exclusive or` , *değer* içindedepolanmışgeçerlideğerle*Atom*dahilinde [memory_order](../standard-library/atomic-enums.md#memory_order_enum) tarafından belirtilen kısıtlamalarını *sipariş*.

## <a name="atomic_flag_clear"></a>  atomic_flag_clear

Kümeleri **bool** bayrağını bir [atomic_flag](../standard-library/atomic-flag-structure.md) nesnesini **false**dahilinde `memory_order_seq_cst` [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

```cpp
inline void atomic_flag_clear(volatile atomic_flag* Flag) noexcept;
inline void atomic_flag_clear(atomic_flag* Flag) noexcept;
```

### <a name="parameters"></a>Parametreler

*Bayrağı*<br/>
Bir işaretçi bir `atomic_flag` nesne.

## <a name="atomic_flag_clear_explicit"></a>  atomic_flag_clear_explicit

Kümeleri **bool** bayrağını bir [atomic_flag](../standard-library/atomic-flag-structure.md) nesnesini **false**, dahilinde belirtilen [memory_order](../standard-library/atomic-enums.md#memory_order_enum) kısıtlamaları.

```cpp
inline void atomic_flag_clear_explicit(volatile atomic_flag* Flag, memory_order Order) noexcept;
inline void atomic_flag_clear_explicit(atomic_flag* Flag, memory_order Order) noexcept;
```

### <a name="parameters"></a>Parametreler

*Bayrağı*<br/>
Bir işaretçi bir `atomic_flag` nesne.

*Sırası*<br/>
A [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

## <a name="atomic_flag_test_and_set"></a>  atomic_flag_test_and_set

Kümeleri **bool** bayrağını bir [atomic_flag](../standard-library/atomic-flag-structure.md) nesnesini **true**, kısıtlamaları dahilinde `memory_order_seq_cst` [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

```cpp
inline bool atomic_flag_test_and_set(volatile atomic_flag* Flag,) noexcept;
inline bool atomic_flag_test_and_set(atomic_flag* Flag,) noexcept;
```

### <a name="parameters"></a>Parametreler

*Bayrağı*<br/>
Bir işaretçi bir `atomic_flag` nesne.

### <a name="return-value"></a>Dönüş Değeri

Başlangıç değeri oluşan *bayrağı*.

## <a name="atomic_flag_test_and_set_explicit"></a>  atomic_flag_test_and_set_explicit

Kümeleri **bool** bayrağını bir [atomic_flag](../standard-library/atomic-flag-structure.md) nesnesini **true**, dahilinde belirtilen [memory_order](../standard-library/atomic-enums.md#memory_order_enum) kısıtlamaları.

```cpp
inline bool atomic_flag_test_and_set_explicit(volatile atomic_flag* Flag, memory_order Order) noexcept;
inline bool atomic_flag_test_and_set_explicit(atomic_flag* Flag, memory_order Order) noexcept;
```

### <a name="parameters"></a>Parametreler

*Bayrağı*<br/>
Bir işaretçi bir `atomic_flag` nesne.

*Sırası*<br/>
A [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

### <a name="return-value"></a>Dönüş Değeri

Başlangıç değeri oluşan *bayrağı*.

## <a name="atomic_init"></a>  atomic_init

Depolanan değeri ayarlar bir `atomic` nesne.

```cpp
template <class Ty>
inline void atomic_init(volatile atomic<Ty>* Atom, Ty Value) noexcept;
template <class Ty>
inline void atomic_init(atomic<Ty>* Atom, Ty Value) noexcept;
```

### <a name="parameters"></a>Parametreler

*Atom*<br/>
Bir işaretçi bir `atomic` türünde bir değer depolar nesne `Ty`.

*Değer*<br/>
Türünde bir değer `Ty`.

### <a name="remarks"></a>Açıklamalar

`atomic_init` atomik bir işlem değildir. İş parçacığı açısından güvenli değildir.

## <a name="atomic_is_lock_free"></a>  atomic_is_lock_free

Belirtir olup olmadığını üzerinde yapılan atomik işlemlerin bir `atomic` nesnesine *kilitsizdir*.

```cpp
template <class T>
inline bool atomic_is_lock_free(const volatile atomic<T>* Atom) noexcept;
template <class T>
inline bool atomic_is_lock_free(const atomic<T>* Atom) noexcept;
```

### <a name="parameters"></a>Parametreler

*Atom*<br/>
Bir işaretçi bir `atomic` türünde bir değer depolar nesne `T`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** , üzerinde yapılan atomik işlemlerin *Atom* olan kilitsizdir; Aksi takdirde **false**.

### <a name="remarks"></a>Açıklamalar

Atomik tür yok Bu türdeki atomik işlemler kilit kullanmıyorsa kilitsizdir. Bu işlev true değerini döndürür, sinyal işleyiciler içinde kullanmak güvenli bir türdür.

## <a name="atomic_load"></a>  atomic_load

Depolanan değeri alır bir `atomic` nesne.

```cpp
template <class Ty>
inline Ty atomic_load(const volatile atomic<Ty>* Atom) noexcept;
template <class Ty>
inline Ty atomic_load(const atomic<Ty>* Atom) noexcept;
```

### <a name="parameters"></a>Parametreler

*Atom*<br/>
Bir işaretçi bir `atomic` türünde bir değer içeren nesne `Ty`.

### <a name="return-value"></a>Dönüş Değeri

Depolanan alınan değeri *Atom*.

### <a name="remarks"></a>Açıklamalar

`atomic_load` örtülü olarak kullanan `memory_order_seq_cst` [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

## <a name="atomic_load_explicit"></a>  atomic_load_explicit

Depolanan değeri alır bir `atomic` içinde belirtilen bir nesne [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

```cpp
template <class Ty>
inline Ty atomic_load_explicit(const volatile atomic<Ty>* Atom, memory_order Order) noexcept;
template <class Ty>
inline Ty atomic_load_explicit(const atomic<Ty>* Atom, memory_order Order) noexcept;
```

### <a name="parameters"></a>Parametreler

*Atom*<br/>
Bir işaretçi bir `atomic` türünde bir değer içeren nesne `Ty`.

*Sırası*<br/>
A [memory_order](../standard-library/atomic-enums.md#memory_order_enum). Kullanmayın `memory_order_release` veya `memory_order_acq_rel`.

### <a name="return-value"></a>Dönüş Değeri

Depolanan alınan değeri *Atom*.

## <a name="atomic_signal_fence"></a>  atomic_signal_fence

Görevi gören bir *dilimi*— yükleme depolama işlemleri arasında sıralamayı zorlayan bellek eşitleme temel öğesi olduğu — bir çağıran iş parçacığında aynı iş parçacığında çalıştırılan sinyal işleyicileri olan diğer dilimleri arasında.

```cpp
inline void atomic_signal_fence(memory_order Order) noexcept;
```

### <a name="parameters"></a>Parametreler

*Sırası*<br/>
Bellek sıralaması Çit türünü belirleyen kısıtlaması.

### <a name="remarks"></a>Açıklamalar

*Sipariş* bağımsız değişken sınır türü.

|||
|-|-|
|`memory_order_relaxed`|Sınır etkisi yoktur.|
|`memory_order_consume`|Sınır bir Al Çit.|
|`memory_order_acquire`|Sınır bir Al Çit.|
|`memory_order_release`|Çit serbest bırakma sınırıdır.|
|`memory_order_acq_rel`|Sınır hem bir Al Çit hem de serbest bırakma sınırıdır ' dir.|
|`memory_order_seq_cst`|Sınır hem bir Al Çit, hem de serbest bırakma sınırıdır ve sıralı olarak tutarlıdır.|

## <a name="atomic_store"></a>  atomic_store

Atomik olarak atomik bir nesnedeki değeri depolar.

```cpp
template <class Ty>
inline Ty atomic_store_explicit(const volatile atomic<Ty>* Atom, Ty Value) noexcept;
template <class Ty>
inline Ty atomic_store_explicit(const atomic<Ty>* Atom, T Value) noexcept;
```

### <a name="parameters"></a>Parametreler

*Atom*<br/>
Türünde bir değer içeren bir atomik nesne işaretçisi `Ty`.

*Değer*<br/>
Türünde bir değer `Ty`.

### <a name="remarks"></a>Açıklamalar

`atomic_store` depolar *değer* tarafından işaret edilen nesnede *Atom*dahilinde `memory_order_seq_cst` [memory_order](../standard-library/atomic-enums.md#memory_order_enum) kısıtlaması.

## <a name="atomic_store_explicit"></a>  atomic_store_explicit

Atomik olarak atomik bir nesnedeki değeri depolar.

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

*Atom*<br/>
Bir işaretçi bir `atomic` türünde bir değer içeren nesne `Ty`.

*Değer*<br/>
Türünde bir değer `Ty`.

*Sırası*<br/>
A [memory_order](../standard-library/atomic-enums.md#memory_order_enum). Kullanmayın `memory_order_consume`, `memory_order_acquire`, veya `memory_order_acq_rel`.

### <a name="remarks"></a>Açıklamalar

`atomic_store` depolar *değer* tarafından işaret edilen nesnede *Atom*dahilinde `memory_order` tarafından belirtilen *sipariş*.

## <a name="atomic_thread_fence"></a>  atomic_thread_fence

Görevi gören bir *dilimi*— yükleme depolama işlemleri arasında sıralamayı zorlayan bellek eşitleme temel öğesi olduğu — ilişkilendirilmiş bir atomik işlem olmaksızın.

```cpp
inline void atomic_thread_fence(memory_order Order) noexcept;
```

### <a name="parameters"></a>Parametreler

*Sırası*<br/>
Bellek sıralaması Çit türünü belirleyen kısıtlaması.

### <a name="remarks"></a>Açıklamalar

*Sipariş* bağımsız değişken sınır türü.

|||
|-|-|
|`memory_order_relaxed`|Sınır etkisi yoktur.|
|`memory_order_consume`|Sınır bir Al Çit.|
|`memory_order_acquire`|Sınır bir Al Çit.|
|`memory_order_release`|Çit serbest bırakma sınırıdır.|
|`memory_order_acq_rel`|Sınır hem bir Al Çit hem de serbest bırakma sınırıdır ' dir.|
|`memory_order_seq_cst`|Sınır hem bir Al Çit, hem de serbest bırakma sınırıdır ve sıralı olarak tutarlıdır.|

## <a name="kill_dependency"></a>  kill_dependency

Bir bağımlılık kaldırır.

```cpp
template <class Ty>
Ty kill_dependency(Ty Arg) noexcept;
```

### <a name="parameters"></a>Parametreler

*bağımsız değişken*<br/>
Türünde bir değer `Ty`.

### <a name="return-value"></a>Dönüş Değeri

Dönüş değeri *Arg*. Değerlendirmesi *Arg* işlev çağrısı için bir bağımlılık içermez. Olası bir bağımlılık zinciri ayırarak, işlev daha verimli kod oluşturmak için derleyicinin izin verebilir.

## <a name="see-also"></a>Ayrıca bkz.

[\<atomik >](../standard-library/atomic.md)<br/>
