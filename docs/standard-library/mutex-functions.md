---
title: '&lt;Mutex&gt; işlevler ve değişkenler'
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
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68240574"
---
# <a name="ltmutexgt-functions-and-variables"></a>&lt;Mutex&gt; işlevler ve değişkenler

## <a name="adopt_lock"></a> adopt_lock

Oluşturucular için geçirilecek bir nesneyi temsil ediyor [lock_guard](../standard-library/lock-guard-class.md) ve [unique_lock](../standard-library/unique-lock-class.md) ayrıca oluşturucuya geçirilen mutex nesnesi kilitli olmadığını belirtmek için.

```cpp
const adopt_lock_t adopt_lock;
```

## <a name="call_once"></a> call_once

Yürütme sırasında tam bir kez belirli bir çağrılabilir nesnesini çağırmak için bir mekanizma sağlar.

```cpp
template <class Callable, class... Args>
void call_once(once_flag& Flag,
    Callable F&&, Args&&... A);
```

### <a name="parameters"></a>Parametreler

*Bayrağı*\
A [once_flag](../standard-library/once-flag-structure.md) çağrılabilir nesnenin yalnızca bir kez çağrılır sağlayan nesne.

*F*\
Aranabilir bir nesne.

*A*\
Bir bağımsız değişken listesi.

### <a name="remarks"></a>Açıklamalar

Varsa *bayrağı* işlevi oluşturur, geçersiz bir [system_error](../standard-library/system-error-class.md) bir hata koduna sahip `invalid_argument`. Aksi durumda şablon işlevi kullanır, *bayrağı* çağrı yaptığı emin olmak için bağımsız değişken `F(A...)` şablon işlevi bağımsız olarak kaç kez başarılı bir şekilde tam olarak bir kez çağrılır. Varsa `F(A...)` özel bir durum yaratarak sonlandırılır çağrı başarılı değildi.

## <a name="defer_lock"></a> defer_lock

İçin oluşturucuya geçirilen nesneyi temsil eden [unique_lock](../standard-library/unique-lock-class.md). Bu oluşturucu ayrıca için geçirilmiş mutex nesnesi kilitlemenizi değil gösterir.

```cpp
const defer_lock_t defer_lock;
```

## <a name="lock"></a> Kilit

Tüm bağımsız değişkenler olmadan kilitlenme kilitlemek çalışır.

```cpp
template <class L1, class L2, class... L3>
void lock(L1&, L2&, L3&...);
```

### <a name="remarks"></a>Açıklamalar

Şablon işlevi için bağımsız değişkenler olmalıdır *mutex türleri*, çağrılar dışında `try_lock` özel durumlar.

İşlevin tüm bağımsız değişkenleri kilitlenme olmadan yapılan çağrılar tarafından kilitler `lock`, `try_lock`, ve `unlock`. Bir çağrı, `lock` veya `try_lock` işlev çağrıları bir istisna atarsa `unlock` herhangi bir özel durum yeniden atma önce başarıyla kilitlenmiştir mutex nesneleri.

## <a name="swap"></a> değiştirme

```cpp
template <class Mutex>
void swap(unique_lock<Mutex>& x, unique_lock<Mutex>& y) noexcept;
```

## <a name="try_lock"></a> try_lock

```cpp
template <class L1, class L2, class... L3> int try_lock(L1&, L2&, L3&...);
```

## <a name="try_to_lock"></a> try_to_lock

İçin oluşturucuya geçirilen nesneyi temsil eden [unique_lock](../standard-library/unique-lock-class.md) Oluşturucu kilidini açma denemesi gerektiğini belirtmek için `mutex` de yapan kendisine engellemeden.

```cpp
const try_to_lock_t try_to_lock;
```
