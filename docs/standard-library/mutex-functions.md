---
title: '&lt;mutex&gt; işlevleri ve değişkenleri'
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
ms.openlocfilehash: f6bd6a86e91c2d59fec2083dcf0ec6314d7c41ab
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79419849"
---
# <a name="ltmutexgt-functions-and-variables"></a>&lt;mutex&gt; işlevleri ve değişkenleri

## <a name="adopt_lock"></a>adopt_lock

[Lock_guard](../standard-library/lock-guard-class.md) için oluşturuculara geçirilebilecek bir nesneyi temsil eder ve ayrıca, oluşturucuya geçirilen mutex nesnesinin kilitli olduğunu göstermek için [unique_lock](../standard-library/unique-lock-class.md) .

```cpp
const adopt_lock_t adopt_lock;
```

## <a name="call_once"></a>call_once

Belirtilen çağrılabilir nesneyi yürütme sırasında tam olarak bir kez çağırmak için bir mekanizma sağlar.

```cpp
template <class Callable, class... Args>
void call_once(once_flag& Flag,
    Callable F&&, Args&&... A);
```

### <a name="parameters"></a>Parametreler

*Bayrak*\
Çağrılabilir nesnenin yalnızca bir kez çağrıldığından emin olan [once_flag](../standard-library/once-flag-structure.md) nesne.

*F*\
Çağrılabilir nesne.

*Bir*\
Bağımsız değişken listesi.

### <a name="remarks"></a>Açıklamalar

*Bayrak* geçerli değilse, işlev `invalid_argument`hata koduna sahip bir [system_error](../standard-library/system-error-class.md) atar. Aksi halde, şablon işlevi, şablon işlevinin kaç kez çağrıldığına bakmaksızın `F(A...)` başarıyla bir kez çağırdığından emin olmak için kendi *bayrak* bağımsız değişkenini kullanır. `F(A...)` bir özel durum oluşturarak çıkış yaparsanız, çağrı başarılı olmadı.

## <a name="defer_lock"></a>defer_lock

[Unique_lock](../standard-library/unique-lock-class.md)için oluşturucuya geçirilebilecek bir nesneyi temsil eder. Bu, oluşturucunun geçirilen Mutex nesnesini de kilitleyemeyeceğini belirtir.

```cpp
const defer_lock_t defer_lock;
```

## <a name="lock"></a>ine

Tüm bağımsız değişkenleri kilitlenme olmadan kilitlemeye çalışır.

```cpp
template <class L1, class L2, class... L3>
void lock(L1&, L2&, L3&...);
```

### <a name="remarks"></a>Açıklamalar

Şablon işlevinin bağımsız değişkenleri, `try_lock` çağrıları özel durumlar oluşturmasının dışında, *Mutex türleri*olmalıdır.

İşlevi, `lock`, `try_lock`ve `unlock`çağrıları aracılığıyla kilitlenme olmadan tüm bağımsız değişkenlerini kilitler. `lock` veya `try_lock` çağrısı bir özel durum oluşturursa, işlev, özel durum yeniden oluşturulmadan önce başarıyla kilitlenen mutex nesnelerinin herhangi birinde `unlock` çağırır.

## <a name="swap"></a>Kur

```cpp
template <class Mutex>
void swap(unique_lock<Mutex>& x, unique_lock<Mutex>& y) noexcept;
```

## <a name="try_lock"></a>try_lock

```cpp
template <class L1, class L2, class... L3> int try_lock(L1&, L2&, L3&...);
```

## <a name="try_to_lock"></a>try_to_lock

Oluşturucunun, engellenmeden de kendisine geçirilen `mutex` kilidini açmaya çalıştığını belirtmek için [unique_lock](../standard-library/unique-lock-class.md) oluşturucuya geçirilebilecek bir nesneyi temsil eder.

```cpp
const try_to_lock_t try_to_lock;
```
