---
title: "&lt;atomik&gt; işlevleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
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
ms.workload: cplusplus
ms.openlocfilehash: 232333280ae44838b0afd41bf0e00255d8a78dc7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
  
##  <a name="atomic_compare_exchange_strong"></a>atomic_compare_exchange_strong  
 Atomik Karşılaştır ve exchange işlemi gerçekleştirir.  
  
```
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
 `Atom`  
 Bir işaretçi bir `atomic` türünde bir değer depolar nesne `Ty`.  
  
 `Exp`  
 Türünde bir değer için bir işaretçi `Ty`.  
  
 `Value`  
 Türünde bir değer `Ty`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `bool` değer karşılaştırması sonucunu gösterir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem örtük kullanarak bir atomik Karşılaştır ve exchange işlem gerçekleştirir `memory_order_seq_cst` [memory_order](../standard-library/atomic-enums.md#memory_order_enum) bağımsız değişkenler. Daha fazla bilgi için bkz: [atomic_compare_exchange_strong_explicit](../standard-library/atomic-functions.md#atomic_compare_exchange_strong_explicit).  
  
##  <a name="atomic_compare_exchange_strong_explicit"></a>atomic_compare_exchange_strong_explicit  
 Gerçekleştiren bir *atomik Karşılaştır ve exchange* işlemi.  
  
```
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
 `Atom`  
 Bir işaretçi bir `atomic` türünde bir değer depolar nesne `Ty`.  
  
 `Exp`  
 Türünde bir değer için bir işaretçi `Ty`.  
  
 `Value`  
 Türünde bir değer `Ty`.  
  
 `Order1`  
 İlk [memory_order](../standard-library/atomic-enums.md#memory_order_enum) bağımsız değişkeni.  
  
 `Order2`  
 İkinci `memory_order` bağımsız değişkeni. Değeri `Order2` olamaz `memory_order_release` veya `memory_order_acq_rel`, değerinden daha güçlü olamaz `Order1`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `bool` değer karşılaştırması sonucunu gösterir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir *atomik Karşılaştır ve exchange işlemi* işaret ediyor nesnesinde saklanan değerle karşılaştırır `Atom` işaret ediyor değerle `Exp`. Değerleri aynıysa işaret ediyor nesnesinde depolanan değer `atom` ile değiştirilir `Val` kullanarak bir `read-modify-write` işlem ve bellek uygulama tarafından belirtilen kısıtlamaları sipariş `Order1`. Değerlerin eşit değilse, işlem işaret ediyor değeri değiştirir `Exp` işaret ediyor nesnesinde depolanan değerle `Atom` ve tarafından belirtilen bellek sipariş kısıtlamaları geçerlidir `Order2`.  
  
##  <a name="atomic_compare_exchange_weak"></a>atomic_compare_exchange_weak  
 Gerçekleştiren bir *zayıf atomik karşılaştırın ve exchange* işlemi.  
  
```
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
 `Atom`  
 Bir işaretçi bir `atomic` türünde bir değer depolar nesne `Ty`.  
  
 `Exp`  
 Türünde bir değer için bir işaretçi `Ty`.  
  
 `Value`  
 Türünde bir değer `Ty`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `bool` değer karşılaştırması sonucunu gösterir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem gerçekleştiren bir *zayıf atomik karşılaştırın ve exchange işlemi* örtük sahip `memory_order_seq_cst` [memory_order](../standard-library/atomic-enums.md#memory_order_enum) bağımsız değişkenler. Daha fazla bilgi için bkz: [atomic_compare_exchange_weak_explicit](../standard-library/atomic-functions.md#atomic_compare_exchange_weak_explicit).  
  
##  <a name="atomic_compare_exchange_weak_explicit"></a>atomic_compare_exchange_weak_explicit  
 Gerçekleştiren bir *zayıf atomik karşılaştırın ve exchange* işlemi.  
  
```
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
 `Atom`  
 Bir işaretçi bir `atomic` türünde bir değer depolar nesne `Ty`.  
  
 `Exp`  
 Türünde bir değer için bir işaretçi `Ty`.  
  
 `Value`  
 Türünde bir değer `Ty`.  
  
 `Order1`  
 İlk [memory_order](../standard-library/atomic-enums.md#memory_order_enum) bağımsız değişkeni.  
  
 `Order2`  
 İkinci `memory_order` bağımsız değişkeni. Değeri `Order2` olamaz `memory_order_release` veya `memory_order_acq_rel`, veya değerinden daha güçlü olabilir `Order1`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `bool` değer karşılaştırması sonucunu gösterir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir *atomik Karşılaştır ve exchange işlemi* işaret ediyor nesnesinde saklanan değerle karşılaştırır `Atom` işaret ediyor değerle `Exp`. Değerlerin eşit olup olmadığını işlemi işaret ediyor nesnesinde depolanan değeri değiştirir `Atom` ile `Val` kullanarak bir `read-modify-write` işlemi ve tarafından belirtilen bellek sipariş kısıtlamalarını uygulama `Order1`. Değerlerin eşit değilse, işlem işaret ediyor değeri değiştirir `Exp` işaret ediyor nesnesinde depolanan değerle `Atom` ve tarafından belirtilen bellek sipariş kısıtlamalar geçerlidir `Order2`.  
  
 A *zayıf* karşılaştırılan değer eşitse, bir exchange atomik Karşılaştır ve exchange işlemi gerçekleştirir. Değerlerin eşit değilse, ancak işlemi bir exchange gerçekleştirmek için kesin değildir.  
  
##  <a name="atomic_exchange"></a>atomic_exchange  
 Kullanan `Value` saklı değerini değiştirmek için `Atom`.  
  
```
template <class T>
inline Ty atomic_exchange(volatile atomic<Ty>* _Atom, Ty Value) noexcept;

template <class Ty>
inline T atomic_exchange(atomic<Ty>* Atom, Ty Value) noexcept;
```  
  
### <a name="parameters"></a>Parametreler  
 `Atom`  
 Bir işaretçi bir `atomic` türünde bir değer depolar nesne `Ty`.  
  
 `Value`  
 Türünde bir değer `Ty`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Saklı değeri `Atom` exchange önce.  
  
### <a name="remarks"></a>Açıklamalar  
 `atomic_exchange` İşlevi gerçekleştiren bir `read-modify-write` depolanan değer exchange işlemi `Atom` ile `Value`kullanarak `memory_order_seq_cst` [memory_order](../standard-library/atomic-enums.md#memory_order_enum).  
  
##  <a name="atomic_exchange_explicit"></a>atomic_exchange_explicit  
 Saklı değerini değiştirir `Atom` ile `Value`.  
  
```
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
 `Atom`  
 Bir işaretçi bir `atomic` türünde bir değer depolar nesne `Ty`.  
  
 `Value`  
 Türünde bir değer `Ty`.  
  
 `Order`  
 A [memory_order](../standard-library/atomic-enums.md#memory_order_enum).  
  
### <a name="return-value"></a>Dönüş Değeri  
 Saklı değeri `Atom` exchange önce.  
  
### <a name="remarks"></a>Açıklamalar  
 `atomic_exchange_explicit` İşlevi gerçekleştiren bir `read-modify-write` depolanan değer exchange işlemi `Atom` ile `Value`, tarafından belirtilen bellek kısıtlamaları içinde `Order`.  
  
##  <a name="atomic_fetch_add"></a>atomic_fetch_add  
 Depolanan var olan bir değer için bir değer ekler bir `atomic` nesnesi.  
  
```
template <class T>  
T* atomic_fetch_add(volatile atomic<T*>* Atom, ptrdiff_t Value) noexcept;
template <class T>  
T* atomic_fetch_add(atomic<T*>* Atom, ptrdiff_t Value) noexcept;
```  
  
### <a name="parameters"></a>Parametreler  
 `Atom`  
 Bir işaretçi bir `atomic` yazmanız için bir işaretçi depolar nesne `T`.  
  
 `Value`  
 Türünde bir değer `ptrdiff_t`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Hemen işlem gerçekleştirildi önce atomik nesnenin içerdiği işaretçi değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 `atomic_fetch_add` İşlevi gerçekleştiren bir `read-modify-write` otomatik olarak eklemek için işlem `Value` saklı değerine `Atom`kullanarak `memory_order_seq_cst` [memory_order](../standard-library/atomic-enums.md#memory_order_enum) kısıtlaması.  
  
 Atomik türü olduğunda `atomic_address`, `Value` türüne sahip `ptrdiff_t` ve saklı işaretçi işlemi değerlendirir bir `char *`.  
  
 Bu işlem ayrıca tam sayı türleri için aşırı:  
  
```
integral atomic_fetch_add(volatile atomic-integral* Atom, integral Value) noexcept;

integral atomic_fetch_add(atomic-integral* Atom, integral Value) noexcept;
```  
  
##  <a name="atomic_fetch_add_explicit"></a>atomic_fetch_add_explicit  
 Depolanan var olan bir değer için bir değer ekler bir `atomic` nesnesi.  
  
```
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
 `Atom`  
 Bir işaretçi bir `atomic` yazmanız için bir işaretçi depolar nesne `T`.  
  
 `Value`  
 Türünde bir değer `ptrdiff_t`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Hemen işlem gerçekleştirildi önce atomik nesnenin içerdiği işaretçi değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 `atomic_fetch_add_explicit` İşlevi gerçekleştiren bir `read-modify-write` işlemi otomatik olarak eklemek için `Value` saklı değerine `Atom`, içinde [memory_order](../standard-library/atomic-enums.md#memory_order_enum) tarafından belirtilen kısıtlamaları `Order`.  
  
 Atomik türü olduğunda `atomic_address`, `Value` türüne sahip `ptrdiff_t` ve saklı işaretçi işlemi değerlendirir bir `char *`.  
  
 Bu işlem ayrıca tam sayı türleri için aşırı:  
  
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
  
##  <a name="atomic_fetch_and"></a>atomic_fetch_and  
 Bit tabanlı gerçekleştirir `and` bir değer ve depolanan var olan bir değerle bir `atomic` nesnesi.  
  
```
template <class T>
inline T atomic_fetch_and(volatile atomic<T>* Atom, T Value) noexcept; 
template <class T>
inline T atomic_fetch_and(volatile atomic<T>* Atom, T Value) noexcept; 
```  
  
### <a name="parameters"></a>Parametreler  
 `Atom`  
 Bir işaretçi bir `atomic` türünde bir değer depolar nesne `T`.  
  
 `Value`  
 Türünde bir değer `T`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Hemen işlem gerçekleştirildi önce atomik nesne tarafından bulunan değer.  
  
### <a name="remarks"></a>Açıklamalar  
 `atomic_fetch_and` İşlevi gerçekleştiren bir `read-modify-write` saklı değerini değiştirmek için işlem `Atom` bit ile `and` , `Value` ve içinde depolanan geçerli değeri `Atom`kullanarak `memory_order_seq_cst` [memory_order](../standard-library/atomic-enums.md#memory_order_enum) kısıtlaması.  
  
##  <a name="atomic_fetch_and_explicit"></a>atomic_fetch_and_explicit  
 Bit tabanlı gerçekleştirir `and` bir ve depolanan mevcut değeri olan bir `atomic` nesnesi.  
  
```
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
 `Atom`  
 Bir işaretçi bir `atomic` türünde bir değer depolar nesne `T`.  
  
 `Value`  
 Türünde bir değer `T`.  
  
 `Order`  
 A [memory_order](../standard-library/atomic-enums.md#memory_order_enum).  
  
### <a name="return-value"></a>Dönüş Değeri  
 Hemen işlem gerçekleştirildi önce atomik nesne tarafından bulunan değer.  
  
### <a name="remarks"></a>Açıklamalar  
 `atomic_fetch_and_explicit` İşlevi gerçekleştirir bir `read-modify-write` saklı değerini değiştirmek için işlem `Atom` bit ile `and` , `Value` ve içinde depolanan geçerli değeri `Atom`, içinde olan bellek kısıtlamaları tarafından belirtilen `Order`.  
  
##  <a name="atomic_fetch_or"></a>atomic_fetch_or  
 Bit tabanlı gerçekleştirir `or` bir değer ve depolanan var olan bir değerle bir `atomic` nesnesi.  
  
```
template <class T>
inline T atomic_fetch_or (volatile atomic<T>* Atom, T Value) noexcept;
template <class T>
inline T atomic_fetch_or (volatile atomic<T>* Atom, T Value) noexcept;
```  
  
### <a name="parameters"></a>Parametreler  
 `Atom`  
 Bir işaretçi bir `atomic` türünde bir değer depolar nesne `T`.  
  
 `Value`  
 Türünde bir değer `T`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Hemen işlem gerçekleştirildi önce atomik nesne tarafından bulunan değer.  
  
### <a name="remarks"></a>Açıklamalar  
 `atomic_fetch_or` İşlevi gerçekleştiren bir `read-modify-write` saklı değerini değiştirmek için işlem `Atom` bit ile `or` , `Value` ve içinde depolanan geçerli değeri `Atom`kullanarak `memory_order_seq_cst` [memory_order](../standard-library/atomic-enums.md#memory_order_enum).  
  
##  <a name="atomic_fetch_or_explicit"></a>atomic_fetch_or_explicit  
 Bit tabanlı gerçekleştirir `or` bir değer ve depolanan var olan bir değerle bir `atomic` nesnesi.  
  
```
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
 `Atom`  
 Bir işaretçi bir `atomic` türünde bir değer depolar nesne `T`.  
  
 `Value`  
 Türünde bir değer `T`.  
  
 `Order`  
 A [memory_order](../standard-library/atomic-enums.md#memory_order_enum).  
  
### <a name="return-value"></a>Dönüş Değeri  
 Hemen işlem gerçekleştirildi önce atomik nesne tarafından bulunan değer.  
  
### <a name="remarks"></a>Açıklamalar  
 `atomic_fetch_or_explicit` İşlevi gerçekleştiren bir `read-modify-write` saklı değerini değiştirmek için işlem `Atom` bit ile `or` , `Value` ve içinde depolanan geçerli değeri `Atom`, içinde [memory_ Sipariş](../standard-library/atomic-enums.md#memory_order_enum) tarafından belirlenen kısıtlamalar `Order`.  
  
##  <a name="atomic_fetch_sub"></a>atomic_fetch_sub  
 Depolanan var olan bir değer arasında bir değer çıkarır bir `atomic` nesnesi.  
  
```
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
 `Atom`  
 Bir işaretçi bir `atomic` yazmanız için bir işaretçi depolar nesne `T`.  
  
 `Value`  
 Türünde bir değer `ptrdiff_t`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Hemen işlem gerçekleştirildi önce atomik nesnenin içerdiği işaretçi değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 `atomic_fetch_sub` İşlevi gerçekleştiren bir `read-modify-write` otomatik olarak çıkarma işlemi `Value` saklı değerinden `Atom`kullanarak `memory_order_seq_cst` [memory_order](../standard-library/atomic-enums.md#memory_order_enum) kısıtlaması.  
  
 Atomik türü olduğunda `atomic_address`, `Value` türüne sahip `ptrdiff_t` ve saklı işaretçi işlemi değerlendirir bir `char *`.  
  
 Bu işlem ayrıca tam sayı türleri için aşırı:  
  
```
integral atomic_fetch_sub(volatile atomic-integral* Atom, integral Value) noexcept;
integral atomic_fetch_sub(atomic-integral* Atom, integral Value) noexcept;
```  
  
##  <a name="atomic_fetch_sub_explicit"></a>atomic_fetch_sub_explicit  
 Depolanan var olan bir değer arasında bir değer çıkarır bir `atomic` nesnesi.  
  
```
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
 `Atom`  
 Bir işaretçi bir `atomic` yazmanız için bir işaretçi depolar nesne `T`.  
  
 `Value`  
 Türünde bir değer `ptrdiff_t`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Hemen işlem gerçekleştirildi önce atomik nesnenin içerdiği işaretçi değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 `atomic_fetch_sub_explicit` İşlevi gerçekleştiren bir `read-modify-write` otomatik olarak çıkarma işlemi `Value` saklı değerinden `Atom`, içinde [memory_order](../standard-library/atomic-enums.md#memory_order_enum) tarafından belirtilen kısıtlamaları `Order`.  
  
 Atomik türü olduğunda `atomic_address`, `Value` türüne sahip `ptrdiff_t` ve saklı işaretçi işlemi değerlendirir bir `char *`.  
  
 Bu işlem ayrıca tam sayı türleri için aşırı:  
  
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
  
##  <a name="atomic_fetch_xor"></a>atomic_fetch_xor  
 Bit tabanlı gerçekleştirir `exclusive or` bir değer ve depolanan var olan bir değerle bir `atomic` nesnesi.  
  
```
template <class T>
inline T atomic_fetch_xor(volatile atomic<T>* Atom, T Value) noexcept; 

template <class T>
inline T atomic_fetch_xor(volatile atomic<T>* Atom, T Value) noexcept;
```  
  
### <a name="parameters"></a>Parametreler  
 `Atom`  
 Bir işaretçi bir `atomic` türünde bir değer depolar nesne `T`.  
  
 `Value`  
 Türünde bir değer `T`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Hemen işlem gerçekleştirildi önce atomik nesne tarafından bulunan değer.  
  
### <a name="remarks"></a>Açıklamalar  
 `atomic_fetch_xor` İşlevi gerçekleştiren bir `read-modify-write` saklı değerini değiştirmek için işlem `Atom` bit ile `exclusive or` , `Value` ve içinde depolanan geçerli değeri `Atom`kullanarak `memory_order_seq_cst` [memory_order](../standard-library/atomic-enums.md#memory_order_enum).  
  
##  <a name="atomic_fetch_xor_explicit"></a>atomic_fetch_xor_explicit  
 Bit tabanlı gerçekleştirir `exclusive or` bir değer ve depolanan var olan bir değerle bir `atomic` nesnesi.  
  
```
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
 `Atom`  
 Bir işaretçi bir `atomic` türünde bir değer depolar nesne `T`.  
  
 `Value`  
 Türünde bir değer `T`.  
  
 `Order`  
 A [memory_order](../standard-library/atomic-enums.md#memory_order_enum).  
  
### <a name="return-value"></a>Dönüş Değeri  
 Hemen işlem gerçekleştirildi önce atomik nesne tarafından bulunan değer.  
  
### <a name="remarks"></a>Açıklamalar  
 `atomic_fetch_xor_explicit` İşlevi gerçekleştiren bir `read-modify-write` saklı değerini değiştirmek için işlem `Atom` bit ile `exclusive or` , `Value` ve içinde depolanan geçerli değeri `Atom`, içinde [memory_ Sipariş](../standard-library/atomic-enums.md#memory_order_enum) tarafından belirtilen kısıtlamaları `Order`.  
  
##  <a name="atomic_flag_clear"></a>atomic_flag_clear  
 Ayarlar `bool` içinde bayrak bir [atomic_flag](../standard-library/atomic-flag-structure.md) nesnesini `false`, içinde `memory_order_seq_cst` [memory_order](../standard-library/atomic-enums.md#memory_order_enum).  
  
```
inline void atomic_flag_clear(volatile atomic_flag* Flag) noexcept;
inline void atomic_flag_clear(atomic_flag* Flag) noexcept;
```  
  
### <a name="parameters"></a>Parametreler  
 `Flag`  
 Bir işaretçi bir `atomic_flag` nesnesi.  
  
##  <a name="atomic_flag_clear_explicit"></a>atomic_flag_clear_explicit  
 Ayarlar `bool` içinde bayrak bir [atomic_flag](../standard-library/atomic-flag-structure.md) nesnesini `false`, belirtilen içinde [memory_order](../standard-library/atomic-enums.md#memory_order_enum) kısıtlamaları.  
  
```
inline void atomic_flag_clear_explicit(volatile atomic_flag* Flag, memory_order Order) noexcept;
inline void atomic_flag_clear_explicit(atomic_flag* Flag, memory_order Order) noexcept;
```  
  
### <a name="parameters"></a>Parametreler  
 `Flag`  
 Bir işaretçi bir `atomic_flag` nesnesi.  
  
 `Order`  
 A [memory_order](../standard-library/atomic-enums.md#memory_order_enum).  
  
##  <a name="atomic_flag_test_and_set"></a>atomic_flag_test_and_set  
 Ayarlar `bool` içinde bayrak bir [atomic_flag](../standard-library/atomic-flag-structure.md) nesnesini `true`, kısıtlamaları dahilinde `memory_order_seq_cst` [memory_order](../standard-library/atomic-enums.md#memory_order_enum).  
  
```
inline bool atomic_flag_test_and_set(volatile atomic_flag* Flag,) noexcept;
inline bool atomic_flag_test_and_set(atomic_flag* Flag,) noexcept;
```  
  
### <a name="parameters"></a>Parametreler  
 `Flag`  
 Bir işaretçi bir `atomic_flag` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başlangıç değeri `Flag`.  
  
##  <a name="atomic_flag_test_and_set_explicit"></a>atomic_flag_test_and_set_explicit  
 Ayarlar `bool` içinde bayrak bir [atomic_flag](../standard-library/atomic-flag-structure.md) nesnesini `true`, belirtilen içinde [memory_order](../standard-library/atomic-enums.md#memory_order_enum) kısıtlamaları.  
  
```
inline bool atomic_flag_test_and_set_explicit(volatile atomic_flag* Flag, memory_order Order) noexcept;
inline bool atomic_flag_test_and_set_explicit(atomic_flag* Flag, memory_order Order) noexcept;
```  
  
### <a name="parameters"></a>Parametreler  
 `Flag`  
 Bir işaretçi bir `atomic_flag` nesnesi.  
  
 `Order`  
 A [memory_order](../standard-library/atomic-enums.md#memory_order_enum).  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başlangıç değeri `Flag`.  
  
##  <a name="atomic_init"></a>atomic_init  
 Saklanan değeri ayarlar bir `atomic` nesnesi.  
  
```
template <class Ty>
inline void atomic_init(volatile atomic<Ty>* Atom, Ty Value) noexcept;
template <class Ty>
inline void atomic_init(atomic<Ty>* Atom, Ty Value) noexcept;
```  
  
### <a name="parameters"></a>Parametreler  
 `Atom`  
 Bir işaretçi bir `atomic` türünde bir değer depolar nesne `Ty`.  
  
 `Value`  
 Türünde bir değer `Ty`.  
  
### <a name="remarks"></a>Açıklamalar  
 `atomic_init`atomik bir işlem değil. İş parçacığı açısından güvenli değil.  
  
##  <a name="atomic_is_lock_free"></a>atomic_is_lock_free  
 Belirtir olup olmadığını atomik işlemleri bir `atomic` nesnesine *kilidi serbest*.  
  
```
template <class T>
inline bool atomic_is_lock_free(const volatile atomic<T>* Atom) noexcept;
template <class T>
inline bool atomic_is_lock_free(const atomic<T>* Atom) noexcept;
```  
  
### <a name="parameters"></a>Parametreler  
 `Atom`  
 Bir işaretçi bir `atomic` türünde bir değer depolar nesne `T`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`varsa atomik işlemleri `Atom` kilidi serbest; tersi durumda, `false`.  
  
### <a name="remarks"></a>Açıklamalar  
 Atomik bir tür olduğundan bu tür hiçbir atomik işlemleri kilitleri kullanırsanız kilidi serbest. Bu işlevi true değerini döndürür, sinyal-işleyicilerini kullanmak güvenli bir türüdür.  
  
##  <a name="atomic_load"></a>atomic_load  
 Saklı değerinde alır bir `atomic` nesnesi.  
  
```
template <class Ty>
inline Ty atomic_load(const volatile atomic<Ty>* Atom) noexcept;
template <class Ty>
inline Ty atomic_load(const atomic<Ty>* Atom) noexcept;
```  
  
### <a name="parameters"></a>Parametreler  
 `Atom`  
 Bir işaretçi bir `atomic` türünde bir değer içeren nesne `Ty`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Depolanan alınan değerin `Atom`.  
  
### <a name="remarks"></a>Açıklamalar  
 `atomic_load`örtük olarak kullanan `memory_order_seq_cst` [memory_order](../standard-library/atomic-enums.md#memory_order_enum).  
  
##  <a name="atomic_load_explicit"></a>atomic_load_explicit  
 Saklı değerinde alır bir `atomic` içinde belirtilen bir nesne [memory_order](../standard-library/atomic-enums.md#memory_order_enum).  
  
```
template <class Ty>
inline Ty atomic_load_explicit(const volatile atomic<Ty>* Atom, memory_order Order) noexcept;
template <class Ty>
inline Ty atomic_load_explicit(const atomic<Ty>* Atom, memory_order Order) noexcept;
```  
  
### <a name="parameters"></a>Parametreler  
 `Atom`  
 Bir işaretçi bir `atomic` türünde bir değer içeren nesne `Ty`.  
  
 `Order`  
 A [memory_order](../standard-library/atomic-enums.md#memory_order_enum). Kullanmayın `memory_order_release` veya `memory_order_acq_rel`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Depolanan alınan değerin `Atom`.  
  
##  <a name="atomic_signal_fence"></a>atomic_signal_fence  
 Görevi gören bir *dilimi*— arasında yük/deposu işlemleri sıralama zorlar bellek eşitleme ilkel olduğu — iş parçacığında yürütülen sinyal işleyicileri sahip diğer dilimleri çağıran bir iş parçacığı arasında.  
  
```
inline void atomic_signal_fence(memory_order Order) noexcept;
```  
  
### <a name="parameters"></a>Parametreler  
 `Order`  
 Dilimi türü belirler kısıtlaması sıralama bellek.  
  
### <a name="remarks"></a>Açıklamalar  
 `Order` Bağımsız değişkeni dilimi türünü belirler.  
  
|||  
|-|-|  
|`memory_order_relaxed`|Dilimi hiçbir etkisi olmaz.|  
|`memory_order_consume`|Dilimi edinme dilimi ' dir.|  
|`memory_order_acquire`|Dilimi edinme dilimi ' dir.|  
|`memory_order_release`|Dilimi yayın dilimi ' dir.|  
|`memory_order_acq_rel`|Dilimi edinme dilimi ve yayın dilimi ' dir.|  
|`memory_order_seq_cst`|Dilimi edinme dilimi ve yayın dilimi ve sırayla tutarlıdır.|  
  
##  <a name="atomic_store"></a>atomic_store  
 Otomatik olarak bir değer bir atomik nesnesinde depolar.  
  
```
template <class Ty>
inline Ty atomic_store_explicit(const volatile atomic<Ty>* Atom, Ty Value) noexcept;
template <class Ty>
inline Ty atomic_store_explicit(const atomic<Ty>* Atom, T Value) noexcept;
```  
  
### <a name="parameters"></a>Parametreler  
 `Atom`  
 Türünde bir değer içeren bir atomik nesne için bir işaretçi `Ty`.  
  
 `Value`  
 Türünde bir değer `Ty`.  
  
### <a name="remarks"></a>Açıklamalar  
 `atomic_store`depolar `Value` işaret ediyor nesnesinde `Atom`, içinde `memory_order_seq_cst` [memory_order](../standard-library/atomic-enums.md#memory_order_enum) kısıtlaması.  
  
##  <a name="atomic_store_explicit"></a>atomic_store_explicit  
 Otomatik olarak bir değer bir atomik nesnesinde depolar.  
  
```
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
 `Atom`  
 Bir işaretçi bir `atomic` türünde bir değer içeren nesne `Ty`.  
  
 `Value`  
 Türünde bir değer `Ty`.  
  
 `Order`  
 A [memory_order](../standard-library/atomic-enums.md#memory_order_enum). Kullanmayın `memory_order_consume`, `memory_order_acquire`, veya `memory_order_acq_rel`.  
  
### <a name="remarks"></a>Açıklamalar  
 `atomic_store`depolar `Value` işaret ediyor nesnesinde `Atom`, içinde `memory_order` tarafından belirtilen `Order`.  
  
##  <a name="atomic_thread_fence"></a>atomic_thread_fence  
 Görevi gören bir *dilimi*— arasında yük/deposu işlemleri sıralama zorlar bellek eşitleme ilkel olduğu — ilişkili atomik bir işlem olmadan.  
  
```
inline void atomic_thread_fence(memory_order Order) noexcept;
```  
  
### <a name="parameters"></a>Parametreler  
 `Order`  
 Dilimi türü belirler kısıtlaması sıralama bellek.  
  
### <a name="remarks"></a>Açıklamalar  
 `Order` Bağımsız değişkeni dilimi türünü belirler.  
  
|||  
|-|-|  
|`memory_order_relaxed`|Dilimi hiçbir etkisi olmaz.|  
|`memory_order_consume`|Dilimi edinme dilimi ' dir.|  
|`memory_order_acquire`|Dilimi edinme dilimi ' dir.|  
|`memory_order_release`|Dilimi yayın dilimi ' dir.|  
|`memory_order_acq_rel`|Dilimi edinme dilimi ve yayın dilimi ' dir.|  
|`memory_order_seq_cst`|Dilimi edinme dilimi ve yayın dilimi ve sırayla tutarlıdır.|  
  
##  <a name="kill_dependency"></a>kill_dependency  
 Bir bağımlılığı kaldırır.  
  
```
template <class Ty>
Ty kill_dependency(Ty Arg) noexcept;
```  
  
### <a name="parameters"></a>Parametreler  
 `Arg`  
 Türünde bir değer `Ty`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dönüş değeri `Arg`. Değerlendirmesi `Arg` işlev çağrısı için bir bağımlılık taşımaz. Olası bağımlılık zinciri bölerek işlevi derleyicinin daha verimli kodu oluşturmasına izin verebilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<atomik >](../standard-library/atomic.md)



