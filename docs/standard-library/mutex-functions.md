---
title: "&lt;Mutex&gt; işlevleri ve değişkenler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- mutex/std::adopt_lock
- mutex/std::call_once
- mutex/std::defer_lock
- mutex/std::lock
- mutex/std::try_to_lock
ms.assetid: 78ab3c8b-c7db-4226-ac93-e2e78ff8b964
caps.latest.revision: "11"
manager: ghogen
helpviewer_keywords:
- std::adopt_lock [C++]
- std::call_once [C++]
- std::defer_lock [C++]
- std::lock [C++]
- std::try_to_lock [C++]
ms.openlocfilehash: a81d134a4fb49f9123dbed5b4146976d5c676379
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ltmutexgt-functions-and-variables"></a>&lt;Mutex&gt; işlevleri ve değişkenler
||||  
|-|-|-|  
|[adopt_lock](#adopt_lock)|[call_once](#call_once)|[defer_lock](#defer_lock)|  
|[kilitleme](#lock)|[try_to_lock](#try_to_lock)|  
  
##  <a name="adopt_lock"></a>adopt_lock değişkeni  
 Oluşturucuları için geçirilecek bir nesneyi temsil ediyor [lock_guard](../standard-library/lock-guard-class.md) ve [unique_lock](../standard-library/unique-lock-class.md) de oluşturucuya geçirilen mutex nesnesi kilitli olup olmadığını belirtmek için.  
  
```cpp  
const adopt_lock_t adopt_lock;
```  
  
##  <a name="call_once"></a>call_once  
 Yürütme sırasında tam olarak bir kez belirtilen bir aranabilir nesne çağırmak için bir mekanizma sağlar.  
  
```
template <class Callable, class... Args>
void call_once(once_flag& Flag,
    Callable F&&, Args&&... A);
```  
  
### <a name="parameters"></a>Parametreler  
 `Flag`  
 A [once_flag](../standard-library/once-flag-structure.md) aranabilir nesne yalnızca bir kez çağrılır sağlar nesnesi.  
  
 `F`  
 Aranabilir bir nesne.  
  
 `A`  
 Bir bağımsız değişken listesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `Flag` işlevi oluşturur, geçersiz bir [system_error](../standard-library/system-error-class.md) hata kodunu olan `invalid_argument`. Aksi durumda, şablon işlevi kullanır, `Flag` çağırır emin olmak için bağımsız değişken `F(A...)` bağımsız olarak kaç kez şablon işlevi başarıyla tam olarak bir kez çağrılır. Varsa `F(A...)` bir özel durum atma tarafından sonlandırılır çağrı başarılı değildi.  
  
##  <a name="defer_lock"></a>defer_lock değişkeni  
 İçin oluşturucuya geçirilen nesneyi temsil eden [unique_lock](../standard-library/unique-lock-class.md). Bu oluşturucu de ona geçirilmiş mutex nesnesi kilitlemeniz değil gösterir.  
  
```cpp  
const defer_lock_t defer_lock;
```  
  
##  <a name="lock"></a>kilitleme  
 Tüm bağımsız değişkenler olmadan kilitlenme kilitlemek çalışır.  
  
```cpp  
template <class L1, class L2, class... L3>
void lock(L1&, L2&, L3&...);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon işlevi bağımsız değişken olmalıdır *mutex türleri*, çağrılar, dışında `try_lock` özel durumlar oluşturma.  
  
 İşlev bağımsız değişkenlerini kilitlenme olmadan tümünün yapılan çağrılar tarafından kilitler `lock`, `try_lock`, ve `unlock`. Çağrı, `lock` veya `try_lock` , işlev çağrıları aykırı `unlock` herhangi bir özel durum yeniden atma önce başarıyla kilitlenmiştir mutex nesneleri.  
  
##  <a name="try_to_lock"></a>try_to_lock değişkeni  
 İçin oluşturucuya geçirilen nesneyi temsil eden [unique_lock](../standard-library/unique-lock-class.md) Oluşturucusu kilidini açmak denemelisiniz belirtmek için `mutex` , ayrıca geçirilen kendisine engellenmeden.  
  
```cpp  
const try_to_lock_t try_to_lock;
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<Mutex >](../standard-library/mutex.md)



