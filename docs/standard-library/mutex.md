---
title: '&lt;mutex&gt;'
ms.date: 11/04/2016
f1_keywords:
- <mutex>
ms.assetid: efb60c89-687a-4e38-8fe4-694e11c4e8a3
ms.openlocfilehash: 515318cda2155db81406a5c23cb64e46e79c4e19
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68448419"
---
# <a name="ltmutexgt"></a>&lt;mutex&gt;

\<Sınıfları ,`mutex` ,,ve`recursive_timed_mutex`; Şablonlar`lock_guard` ve ;vedestekleyicitürlerveişlevleritanımlamakiçinstandartüstbilgimutex>dahiledin`unique_lock`. `recursive_mutex` `timed_mutex` karşılıklı dışlama kod bölgeleri.

> [!WARNING]
> Visual Studio 2015 ' den başlayarak C++ standart kitaplık eşitleme türleri Windows eşitleme temel temellerine dayalıdır ve artık ConcRT kullanmaz (hedef platformun Windows XP olduğu durumlar dışında). \<Mutex > tanımlı türler, herhangi bir ConcRT türü veya işlevleriyle kullanılmamalıdır.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<mutex >

**Ad alanı:** std

## <a name="remarks"></a>Açıklamalar

> [!NOTE]
> **/Clr**kullanılarak derlenen kodda, bu üst bilgi engellenir.

Sınıflar `mutex` ve `recursive_mutex` *mutex türlerdir*. Mutex türü, bir varsayılan oluşturucuya ve özel durum oluşturmayan bir yıkıcıya sahiptir. Bu nesneler, birden çok iş parçacığı aynı nesneyi kilitlemeyi denediğinde karşılıklı dışlama sağlayan yöntemlere sahiptir. Özellikle, bir mutex türü, ve `lock` `unlock`yöntemlerini `try_lock`içerir:

- `lock` Yöntemi, iş parçacığı mutex sahipliğini edinene kadar çağıran iş parçacığını engeller. Dönüş değeri yok sayılır.

- `try_lock` Yöntemi, engelleme olmadan mutex 'in sahipliğini almaya çalışır. Dönüş türü **bool** değerine dönüştürülebilir ve Yöntem sahipliği alırsa **true** , değilse **false 'tur**.

- `unlock` Yöntemi, çağıran iş parçacığından mutex 'in sahipliğini serbest bırakır.

Şablon `lock_guard` ve`unique_lock`örnek oluşturmak için, Mutex türlerini tür bağımsız değişkeni olarak kullanabilirsiniz. Bu türlerin nesnelerini, `Lock` [condition_variable_any](../standard-library/condition-variable-any-class.md)şablonundaki üye işlev işlevlerinin bağımsız değişkeni olarak kullanabilirsiniz.

*Zaman uyumu* türü, bir mutex türü için gereksinimleri karşılar. Ayrıca, bir bağımsız değişken kullanılarak `try_lock_for` çağrılabilir `try_lock_until` olması gereken ve, **bool**değerine dönüştürülebilir bir tür döndürmesi gereken yöntemleri vardır. Zaman uyumu veren bir tür, bu işlevleri ek bağımsız değişkenlerin varsayılan değerlerine sahip olması kaydıyla, ek bağımsız değişkenler kullanarak tanımlayabilir.

- Yöntemi bir bağımsız değişken kullanılarak çağrılabilir olmalıdır, türü bir zaman [hatası::d urma](../standard-library/duration-class.md)örneklemedir. `Rel_time` `try_lock_for` Yöntemi, mutex 'in sahipliğini almaya çalışır, ancak başarıya bakılmaksızın tarafından `Rel_time`belirtilen süre içinde döndürülür. Yöntem sahipliği alırsa dönüş değeri **true** olarak dönüştürülür; Aksi takdirde, dönüş değeri **false**değerine dönüştürülür.

- Yöntemi bir bağımsız değişken kullanılarak çağrılabilir olmalıdır, türü bir zaman [hatası:: time_point](../standard-library/time-point-class.md)örneklemedir. `Abs_time` `try_lock_until` Yöntemi, mutex 'in sahipliğini almaya çalışır, ancak başarıyı ne olursa olsun tarafından `Abs_time`belirtilen süreden daha sonra Hayır sonucunu döndürür. Yöntem sahipliği alırsa dönüş değeri **true** olarak dönüştürülür; Aksi takdirde, dönüş değeri **false**değerine dönüştürülür.

Mutex türü, *kilitlenebilir tür*olarak da bilinir. Üye işlevi `try_lock`sağlamıyorsa, bu, *temel bir kilitlenebilir türüdür*. Zaman uyumlu bir mutex türü, *zaman aşımına uğramış bir tür*olarak da bilinir.

## <a name="members"></a>Üyeler

### <a name="classes"></a>Sınıflar

|||
|-|-|
|[lock_guard Sınıfı](../standard-library/lock-guard-class.md)|Yıkıcıya kilidi olan bir `mutex`nesne oluşturmak için örneklenebilir bir şablonu temsil eder.|
|[mutex Sınıfı (C++ Standart Kitaplığı)](../standard-library/mutex-class-stl.md)|Bir mutex türünü temsil eder. Bir programda karşılıklı dışlamayı zorlamak için bu türdeki nesneleri kullanın.|
|[recursive_mutex Sınıfı](../standard-library/recursive-mutex-class.md)|Bir mutex türünü temsil eder. `mutex` Sınıfına constrast içinde, zaten kilitlenen nesneler için kilitleme yöntemlerinin çağrılması iyi tanımlanmış bir davranıştır.|
|[recursive_timed_mutex Sınıfı](../standard-library/recursive-timed-mutex-class.md)|Süreli bir mutex türünü temsil eder. Bir program içinde zaman sınırlı engellemeye sahip karşılıklı dışlamayı zorlamak için bu türdeki nesneleri kullanın. Türündeki `timed_mutex`nesnelerden farklı olarak, nesneler için `recursive_timed_mutex` kilitleme yöntemlerinin çağrılması iyi tanımlanmış bir etkiye sahiptir.|
|[scoped_lock sınıfı](../standard-library/scoped-lock-class.md)||
|[timed_mutex Sınıfı](../standard-library/timed-mutex-class.md)|Süreli bir mutex türünü temsil eder. Bir program içinde zaman sınırlı engellemeye sahip karşılıklı dışlamayı zorlamak için bu türdeki nesneleri kullanın.|
|[unique_lock Sınıfı](../standard-library/unique-lock-class.md)|Bir `mutex`öğesinin kilitlenmesini ve kilidinin açılmasını yöneten nesneler oluşturmak için örneklenebilir bir şablonu temsil eder.|

### <a name="functions"></a>İşlevler

|||
|-|-|
|[call_once](../standard-library/mutex-functions.md#call_once)|Belirtilen çağrılabilir nesneyi yürütme sırasında tam olarak bir kez çağırmak için bir mekanizma sağlar.|
|[lock](../standard-library/mutex-functions.md#lock)|Tüm bağımsız değişkenleri kilitlenme olmadan kilitlemeye çalışır.|
|[Kur](../standard-library/mutex-functions.md#swap)||
|[try_lock](../standard-library/mutex-functions.md#try_lock)||

### <a name="structs"></a>Yapılar

|||
|-|-|
|[adopt_lock_t Yapısı](../standard-library/adopt-lock-t-structure.md)|Tanımlamak için kullanılan bir türü temsil eder `adopt_lock`.|
|[defer_lock_t Yapısı](../standard-library/defer-lock-t-structure.md)|Aşırı yüklenmiş `defer_lock` `unique_lock`oluşturucularından birini seçmek için kullanılan bir nesneyi tanımlayan bir türü temsil eder.|
|[once_flag Yapısı](../standard-library/once-flag-structure.md)|Başlatma kodunun  birden çok iş parçacığının bulunması durumunda bile yalnızca `call_once` bir kez çağrıldığından emin olmak için, şablon işleviyle birlikte kullanılan bir yapıyı temsil eder.|
|[try_to_lock_t Yapısı](../standard-library/try-to-lock-t-structure.md)|`unique_lock`  Bir`try_to_lock` nesneyi tanımlayan ve ' nin aşırı yüklenmiş oluşturucularından birini seçmek için kullanılan bir yapıyı temsil eder.|

### <a name="variables"></a>Değişkenler

|||
|-|-|
|[adopt_lock](../standard-library/mutex-functions.md#adopt_lock)|Oluşturucuya geçirilen mutex nesnesinin kilitli olduğunu göstermek için `lock_guard` ve `unique_lock` yapıcısına geçirilebilecek bir nesneyi temsil eder.|
|[defer_lock](../standard-library/mutex-functions.md#defer_lock)|Oluşturucunun kendisine geçirilen Mutex nesnesini kilitleyemeyeceğini göstermek için, `unique_lock`için oluşturucusuna geçirilebilecek bir nesneyi temsil eder.|
|[try_to_lock](../standard-library/mutex-functions.md#try_to_lock)|Oluşturucunun, `unique_lock` `mutex` engellenmeden de kendisine geçirilen öğesinin kilidini açmaya çalıştığını göstermek için oluşturucusuna geçirilebilecek bir nesneyi temsil eder.|

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)
