---
title: '&lt;Mutex&gt; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: <mutex>
dev_langs: C++
ms.assetid: efb60c89-687a-4e38-8fe4-694e11c4e8a3
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 65629b16b03503f70f7c966e19282391c512e4ee
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ltmutexgt"></a>&lt;Mutex&gt;
Standart üstbilgisini \<mutex > sınıflarını tanımlamak için `mutex`, `recursive_mutex`, `timed_mutex`, ve `recursive_timed_mutex`; şablonları `lock_guard` ve `unique_lock`; destekleyici türler ve İşlevler tanımlayın karşılıklı dışlama kod bölgeleri.  
  
> [!WARNING]
>  Visual Studio 2015'te başlayarak, C++ Standart Kitaplığı eşitleme türleri Windows eşitleme temelleri dayanır ve artık ConcRT (hedef platformu Windows XP olduğunda dışında) kullanın. Tanımlanan türleri \<mutex > tüm ConcRT türlerin veya işlevlerin kullanılmamalıdır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
#include <mutex>  
```  
  
## <a name="remarks"></a>Açıklamalar  
  
> [!NOTE]
>  Kullanarak derlenmiş kod **/CLR**, bu başlığı engellenir.  
  
 Sınıfları `mutex` ve `recursive_mutex` olan *mutex türleri*. Varsayılan bir oluşturucu ve özel durumlar oluşturmadığını yıkıcı bir mutex türü vardır. Bu nesnelerin aynı nesne kilitlemek birden çok iş parçacığı çalıştığınızda, karşılıklı dışlama sağlayan yöntemler vardır. Özellikle, bir mutex türü yöntemleri içeren `lock`, `try_lock`, ve `unlock`:  
  
-   `lock` Yöntemini çağıran iş parçacığı iş parçacığı mutex sahipliğini alıncaya kadar engeller. Dönüş değeri yok sayılır.  
  
-   `try_lock` Yöntemi çalıştığında engellenmeden mutex sahipliğini elde edilir. Dönüş türü dönüştürülebilir `bool` ve `true` yöntemi sahipliği alır, ancak aksi `false`.  
  
-   `unlock` Yöntemini çağıran iş parçacığı gelen mutex sahipliğini serbest bırakır.  
  
 Mutex türleri tür bağımsız değişkenleri şablonları örneği oluşturmak için kullanabileceğiniz `lock_guard` ve `unique_lock`. Bu tür nesneler kullanabilirsiniz `Lock` şablondaki bekleme üye işlevleri bağımsız değişkeni [condition_variable_any](../standard-library/condition-variable-any-class.md).  
  
 A *mutex türü zaman aşımına* mutex türü için gereksinimleri karşılıyor. Ayrıca, sahip `try_lock_for` ve `try_lock_until` bir bağımsız değişken kullanılarak aranabilir olmalıdır ve parametresinin türü döndürmelidir yöntemleri `bool`. Bu ek bağımsız değişkenler tüm varsayılan değerlere sahip olması koşuluyla zamanlanmış mutex türü ek bağımsız değişkenler kullanarak bu işlevler tanımlayabilirsiniz.  
  
-   `try_lock_for` Yöntemi olmalıdır aranabilir tek bir bağımsız değişken kullanarak `Rel_time`, türü olan bir örnek oluşturma, [chrono::duration](../standard-library/duration-class.md). Yöntem mutex sahipliğini almayı dener, ancak tarafından belirlenen süre içinde döndürür `Rel_time`başarı ne olursa olsun. Dönüş değeri dönüştürür `true` sahipliği; yöntemi alır, aksi takdirde, dönüş değeri dönüştürür `false`.  
  
-   `try_lock_until` Yöntemi olmalıdır aranabilir tek bir bağımsız değişken kullanarak `Abs_time`, türü olan bir örnek oluşturma, [chrono::time_point](../standard-library/time-point-class.md). Yöntem mutex sahipliğini almayı dener, ancak tarafından atanan zamandan sonra döndürür `Abs_time`başarı ne olursa olsun. Dönüş değeri dönüştürür `true` sahipliği; yöntemi alır, aksi takdirde, dönüş değeri dönüştürür `false`.  
  
 Mutex türü olarak da bilinen olan bir *kilitlenebilir türü*. Üye işlevini sağlamıyorsa `try_lock`, bu bir *temel kilitlenebilir türü*. Zamanlanmış mutex türü olarak da bilinen olan bir *kilitlenebilir türü zaman aşımına*.  
  
### <a name="classes"></a>Sınıflar  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[lock_guard sınıfı](../standard-library/lock-guard-class.md)|Yıkıcı kilidini açarak nesne oluşturmak için örneği bir şablon temsil eden bir `mutex`.|  
|[Mutex sınıfı (Standart C++ Kitaplığı)](../standard-library/mutex-class-stl.md)|Mutex türünü temsil eder. Bir programdan karşılıklı dışlama zorlamak için bu tür nesneler kullanın.|  
|[recursive_mutex sınıfı](../standard-library/recursive-mutex-class.md)|Mutex türünü temsil eder. İçin constrast içinde `mutex` sınıfı, zaten kilitli olan nesneler için kilitleme yöntemleri çağırma davranışını iyi tanımlanmış.|  
|[recursive_timed_mutex sınıfı](../standard-library/recursive-timed-mutex-class.md)|Zamanlanmış mutex türünü temsil eder. Zaman sınırlı bir program içinden engelleme sahip karşılıklı dışlama zorlamak için bu tür nesneler kullanın. Nesne türü aksine `timed_mutex`, kilitleme yöntemleri çağırma etkisini `recursive_timed_mutex` nesneleri iyi tanımlanmış.|  
|[timed_mutex sınıfı](../standard-library/timed-mutex-class.md)|Zamanlanmış mutex türünü temsil eder. Zaman sınırlı bir program içinden engelleme sahip karşılıklı dışlama zorlamak için bu tür nesneler kullanın.|  
|[unique_lock sınıfı](../standard-library/unique-lock-class.md)|Kilitleme ve, kilidini açma yönetmek nesneleri oluşturmak için örneği bir şablon temsil eden bir `mutex`.|  
  
### <a name="functions"></a>İşlevler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[call_once](../standard-library/mutex-functions.md#call_once)|Yürütme sırasında tam olarak bir kez belirtilen bir aranabilir nesne çağırmak için bir mekanizma sağlar.|  
|[kilitleme](../standard-library/mutex-functions.md#lock)|Tüm bağımsız değişkenler olmadan kilitlenme kilitlemek çalışır.|  
  
### <a name="structs"></a>Yapılar  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[adopt_lock_t yapısı](../standard-library/adopt-lock-t-structure.md)|Tanımlamak için kullanılan bir türü temsil eden bir `adopt_lock`.|  
|[defer_lock_t yapısı](../standard-library/defer-lock-t-structure.md)|Tanımlayan bir türü temsil eden bir `defer_lock` aşırı yüklü oluşturucular birini seçmek için kullanılan nesne `unique_lock`.|  
|[once_flag yapısı](../standard-library/once-flag-structure.md)|Temsil eden bir `struct` şablonu işleviyle kullanılan `call_once` başlatmanın emin olmak için kod bile birden çok iş parçacığı yürütme varlığında yalnızca bir kez çağrılır.|  
|[try_to_lock_t yapı](../standard-library/try-to-lock-t-structure.md)|Temsil eden bir `struct` tanımlayan bir `try_to_lock` nesne ve aşırı yüklü oluşturucular birini seçmek için kullanılan `unique_lock`.|  
  
### <a name="variables"></a>Değişkenler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[adopt_lock](../standard-library/mutex-functions.md#adopt_lock)|Oluşturucuları için geçirilecek bir nesneyi temsil ediyor `lock_guard` ve `unique_lock` de oluşturucuya geçirilen mutex nesnesi kilitli olup olmadığını belirtmek için.|  
|[defer_lock](../standard-library/mutex-functions.md#defer_lock)|İçin oluşturucuya geçirilen nesneyi temsil eden `unique_lock`Oluşturucusu de ona geçirilmiş mutex nesnesi kilitlemeniz değil belirtmek için.|  
|[try_to_lock](../standard-library/mutex-functions.md#try_to_lock)|İçin oluşturucuya geçirilen nesneyi temsil eden `unique_lock` Oluşturucusu kilidini açmak denemelisiniz belirtmek için `mutex` , ayrıca geçirilen kendisine engellenmeden.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)



