---
description: 'Daha fazla bilgi edinin: &lt; mutex &gt; işlevleri ve değişkenleri'
title: '&lt;mutex &gt; işlevleri ve değişkenleri'
ms.date: 11/04/2016
f1_keywords:
- mutex/std::adopt_lock
- mutex/std::call_once
- mutex/std::defer_lock
- mutex/std::lock
- mutex/std::try_to_lock
ms.assetid: 78ab3c8b-c7db-4226-ac93-e2e78ff8b964
helpviewer_keywords:
- std::adopt_lock [C++]
- std::call_once [C++]
- std::defer_lock [C++]
- std::lock [C++]
- std::try_to_lock [C++]
ms.openlocfilehash: e06fe09c78d8b79f5dd804e64ef11e84c558ba24
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338265"
---
# <a name="ltmutexgt-functions-and-variables"></a>&lt;mutex &gt; işlevleri ve değişkenleri

## <a name="adopt_lock"></a><a name="adopt_lock"></a> adopt_lock

[Lock_guard](../standard-library/lock-guard-class.md) için oluşturuculara geçirilebilecek bir nesneyi temsil eder ve ayrıca, oluşturucuya geçirilen mutex nesnesinin kilitli olduğunu göstermek için [unique_lock](../standard-library/unique-lock-class.md) .

```cpp
const adopt_lock_t adopt_lock;
```

## <a name="call_once"></a><a name="call_once"></a> call_once

Belirtilen çağrılabilir nesneyi yürütme sırasında tam olarak bir kez çağırmak için bir mekanizma sağlar.

```cpp
template <class Callable, class... Args>
void call_once(once_flag& Flag,
    Callable F&&, Args&&... A);
```

### <a name="parameters"></a>Parametreler

*Bayrağıyla*\
Çağrılabilir nesnenin yalnızca bir kez çağrıldığından emin olan [once_flag](../standard-library/once-flag-structure.md) nesne.

*Vadeli*\
Çağrılabilir nesne.

*A*\
Bağımsız değişken listesi.

### <a name="remarks"></a>Açıklamalar

*Bayrak* geçerli değilse, işlev hata kodu olan bir [system_error](../standard-library/system-error-class.md) oluşturur `invalid_argument` . Aksi halde, şablon işlevi,  `F(A...)` şablon işlevinin kaç kez çağrıldığına bakmaksızın, başarıyla bir kez çağrı yapıldığından emin olmak için kendi bayrak bağımsız değişkenini kullanır. `F(A...)`Bir özel durum oluşturarak çıkılırken çağrı başarılı olmadı.

## <a name="defer_lock"></a><a name="defer_lock"></a> defer_lock

[Unique_lock](../standard-library/unique-lock-class.md)için oluşturucuya geçirilebilecek bir nesneyi temsil eder. Bu, oluşturucunun geçirilen Mutex nesnesini de kilitleyemeyeceğini belirtir.

```cpp
const defer_lock_t defer_lock;
```

## <a name="lock"></a><a name="lock"></a> ine

Tüm bağımsız değişkenleri kilitlenme olmadan kilitlemeye çalışır.

```cpp
template <class L1, class L2, class... L3>
void lock(L1&, L2&, L3&...);
```

### <a name="remarks"></a>Açıklamalar

' A yapılan çağrılar özel durum oluşturabilecek olması dışında, şablon işlevinin bağımsız değişkenleri *Mutex türleri* olmalıdır `try_lock` .

İşlevi,, ve çağrıları ile kilitlenme olmadan bağımsız değişkenlerini kilitler `lock` `try_lock` `unlock` . Bir çağrısı `lock` veya `try_lock` bir özel durum oluşturursa, işlev, `unlock` özel durum yeniden oluşturulmadan önce başarıyla kilitlenen mutex nesnelerinden herhangi birine çağrı yapılır.

## <a name="swap"></a><a name="swap"></a> Kur

```cpp
template <class Mutex>
void swap(unique_lock<Mutex>& x, unique_lock<Mutex>& y) noexcept;
```

## <a name="try_lock"></a><a name="try_lock"></a> try_lock

```cpp
template <class L1, class L2, class... L3> int try_lock(L1&, L2&, L3&...);
```

## <a name="try_to_lock"></a><a name="try_to_lock"></a> try_to_lock

Oluşturucunun, [](../standard-library/unique-lock-class.md) `mutex` engellemeden de kendisine geçirilen öğesinin kilidini açmaya çalıştığını belirtmek için unique_lock oluşturucuya geçirilebilecek bir nesneyi temsil eder.

```cpp
const try_to_lock_t try_to_lock;
```
