---
title: '&lt;mutex&gt;'
ms.date: 11/04/2016
f1_keywords:
- <mutex>
ms.assetid: efb60c89-687a-4e38-8fe4-694e11c4e8a3
ms.openlocfilehash: e17488023d8de6eb5d341c719be8f1b36c14ffcd
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87228186"
---
# <a name="ltmutexgt"></a>&lt;mutex&gt;

\<mutex>Sınıfları `mutex` , `recursive_mutex` , `timed_mutex` , ve; `recursive_timed_mutex` Şablonlar `lock_guard` ve `unique_lock` ; ve karşılıklı dışlama kod bölgelerini tanımlayan destekleyici türleri ve işlevleri tanımlamak için standart üstbilgiyi ekleyin.

> [!WARNING]
> Visual Studio 2015 ' den başlayarak, C++ standart kitaplığı eşitleme türleri Windows eşitleme temel temellerine dayalıdır ve artık ConcRT kullanmaz (hedef platformun Windows XP olduğu durumlar dışında). İçinde tanımlanan türler, \<mutex> herhangi bir ConcRT türü veya işlevleriyle kullanılmamalıdır.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<mutex>

**Ad alanı:** std

## <a name="remarks"></a>Açıklamalar

> [!NOTE]
> **/Clr**kullanılarak derlenen kodda, bu üst bilgi engellenir.

Sınıflar `mutex` ve `recursive_mutex` *mutex türlerdir*. Mutex türü, bir varsayılan oluşturucuya ve özel durum oluşturmayan bir yıkıcıya sahiptir. Bu nesneler, birden çok iş parçacığı aynı nesneyi kilitlemeyi denediğinde karşılıklı dışlama sağlayan yöntemlere sahiptir. Özellikle, bir mutex türü, ve yöntemlerini `lock` içerir `try_lock` `unlock` :

- `lock`Yöntemi, iş parçacığı mutex sahipliğini edinene kadar çağıran iş parçacığını engeller. Dönüş değeri yok sayılır.

- `try_lock`Yöntemi, engelleme olmadan mutex 'in sahipliğini almaya çalışır. Dönüş türü öğesine dönüştürülebilir **`bool`** ve **`true`** yöntemin sahipliği elde ettiği, aksi durumda **`false`** .

- `unlock`Yöntemi, çağıran iş parçacığından mutex 'in sahipliğini serbest bırakır.

Şablon ve örnek oluşturmak için, Mutex türlerini tür bağımsız değişkeni olarak `lock_guard` kullanabilirsiniz `unique_lock` . Bu türdeki nesneleri, `Lock` şablon [condition_variable_any](../standard-library/condition-variable-any-class.md)bekleme üye işlevlerinin bağımsız değişkeni olarak kullanabilirsiniz.

*Zaman uyumu* türü, bir mutex türü için gereksinimleri karşılar. Buna ek olarak, `try_lock_for` `try_lock_until` bir bağımsız değişken kullanılarak çağrılabilir olması gereken ve ile dönüştürülebilir bir tür döndürmesi gereken yöntemleri vardır **`bool`** . Zaman uyumu veren bir tür, bu işlevleri ek bağımsız değişkenlerin varsayılan değerlerine sahip olması kaydıyla, ek bağımsız değişkenler kullanarak tanımlayabilir.

- `try_lock_for`Yöntemi bir bağımsız değişken kullanılarak çağrılabilir olmalıdır, türü bir zaman `Rel_time` [hatası::d urma](../standard-library/duration-class.md)örneklemedir. Yöntemi, mutex 'in sahipliğini almaya çalışır, ancak başarıya bakılmaksızın tarafından belirtilen süre içinde döndürülür `Rel_time` . Dönüş değeri, **`true`** Yöntem sahipliği alırsa öğesine dönüştürür; Aksi takdirde, dönüş değeri değerine dönüştürülür **`false`** .

- `try_lock_until`Yöntemi bir bağımsız değişken kullanılarak çağrılabilir olmalıdır, türü bir zaman `Abs_time` [hatası:: time_point](../standard-library/time-point-class.md)örneklemedir. Yöntemi, mutex 'in sahipliğini almaya çalışır, ancak `Abs_time` başarıyı ne olursa olsun tarafından belirtilen süreden daha sonra Hayır sonucunu döndürür. Dönüş değeri, **`true`** Yöntem sahipliği alırsa öğesine dönüştürür; Aksi takdirde, dönüş değeri değerine dönüştürülür **`false`** .

Mutex türü, *kilitlenebilir tür*olarak da bilinir. Üye işlevi sağlamıyorsa `try_lock` , bu, *temel bir kilitlenebilir türüdür*. Zaman uyumlu bir mutex türü, *zaman aşımına uğramış bir tür*olarak da bilinir.

## <a name="members"></a>Üyeler

### <a name="classes"></a>Sınıflar

|||
|-|-|
|[lock_guard sınıfı](../standard-library/lock-guard-class.md)|Yıkıcıya kilidi olan bir nesne oluşturmak için örneklenebilir bir şablonu temsil eder `mutex` .|
|[Mutex sınıfı (C++ Standart Kitaplığı)](../standard-library/mutex-class-stl.md)|Bir mutex türünü temsil eder. Bir programda karşılıklı dışlamayı zorlamak için bu türdeki nesneleri kullanın.|
|[recursive_mutex sınıfı](../standard-library/recursive-mutex-class.md)|Bir mutex türünü temsil eder. Sınıfına constrast içinde `mutex` , zaten kilitlenen nesneler için kilitleme yöntemlerinin çağrılması iyi tanımlanmış bir davranıştır.|
|[recursive_timed_mutex sınıfı](../standard-library/recursive-timed-mutex-class.md)|Süreli bir mutex türünü temsil eder. Bir program içinde zaman sınırlı engellemeye sahip karşılıklı dışlamayı zorlamak için bu türdeki nesneleri kullanın. Türündeki nesnelerden farklı olarak `timed_mutex` , nesneler için kilitleme yöntemlerinin çağrılması iyi tanımlanmış bir etkiye sahiptir `recursive_timed_mutex` .|
|[scoped_lock sınıfı](../standard-library/scoped-lock-class.md)||
|[timed_mutex sınıfı](../standard-library/timed-mutex-class.md)|Süreli bir mutex türünü temsil eder. Bir program içinde zaman sınırlı engellemeye sahip karşılıklı dışlamayı zorlamak için bu türdeki nesneleri kullanın.|
|[unique_lock sınıfı](../standard-library/unique-lock-class.md)|Bir öğesinin kilitlenmesini ve kilidinin açılmasını yöneten nesneler oluşturmak için örneklenebilir bir şablonu temsil eder `mutex` .|

### <a name="functions"></a>İşlevler

|||
|-|-|
|[call_once](../standard-library/mutex-functions.md#call_once)|Belirtilen çağrılabilir nesneyi yürütme sırasında tam olarak bir kez çağırmak için bir mekanizma sağlar.|
|[ine](../standard-library/mutex-functions.md#lock)|Tüm bağımsız değişkenleri kilitlenme olmadan kilitlemeye çalışır.|
|[Kur](../standard-library/mutex-functions.md#swap)||
|[try_lock](../standard-library/mutex-functions.md#try_lock)||

### <a name="structs"></a>Yapılar

|||
|-|-|
|[adopt_lock_t Yapısı](../standard-library/adopt-lock-t-structure.md)|Tanımlamak için kullanılan bir türü temsil eder `adopt_lock` .|
|[defer_lock_t Yapısı](../standard-library/defer-lock-t-structure.md)|`defer_lock`Aşırı yüklenmiş oluşturucularından birini seçmek için kullanılan bir nesneyi tanımlayan bir türü temsil eder `unique_lock` .|
|[once_flag Yapısı](../standard-library/once-flag-structure.md)|**`struct`** `call_once` Başlatma kodunun birden çok iş parçacığının bulunması durumunda bile, yalnızca bir kez çağrıldığından emin olmak için, şablon işleviyle birlikte kullanılan bir öğesini temsil eder.|
|[try_to_lock_t Yapısı](../standard-library/try-to-lock-t-structure.md)|Bir **`struct`** `try_to_lock` nesneyi tanımlayan ve ' nin aşırı yüklenmiş oluşturucularından birini seçmek için kullanılan bir öğesini temsil eder `unique_lock` .|

### <a name="variables"></a>Değişkenler

|||
|-|-|
|[adopt_lock](../standard-library/mutex-functions.md#adopt_lock)|`lock_guard` `unique_lock` Oluşturucuya geçirilen mutex nesnesinin kilitli olduğunu göstermek için ve yapıcısına geçirilebilecek bir nesneyi temsil eder.|
|[defer_lock](../standard-library/mutex-functions.md#defer_lock)|`unique_lock`Oluşturucunun kendisine geçirilen Mutex nesnesini kilitleyemeyeceğini göstermek için, için oluşturucusuna geçirilebilecek bir nesneyi temsil eder.|
|[try_to_lock](../standard-library/mutex-functions.md#try_to_lock)|`unique_lock`Oluşturucunun, `mutex` engellenmeden de kendisine geçirilen öğesinin kilidini açmaya çalıştığını göstermek için oluşturucusuna geçirilebilecek bir nesneyi temsil eder.|

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)
