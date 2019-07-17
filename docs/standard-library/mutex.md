---
title: '&lt;Mutex&gt;'
ms.date: 11/04/2016
f1_keywords:
- <mutex>
ms.assetid: efb60c89-687a-4e38-8fe4-694e11c4e8a3
ms.openlocfilehash: 377ec995f4e61c957e8e620749f96523b60fed3e
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68240590"
---
# <a name="ltmutexgt"></a>&lt;Mutex&gt;

Standart üst bilgiyi dahil \<mutex > sınıflarını tanımlamak için `mutex`, `recursive_mutex`, `timed_mutex`, ve `recursive_timed_mutex`; şablonları `lock_guard` ve `unique_lock`; ve türleri ve işlevleri tanımlayın karşılıklı dışlama kod bölgeleri.

> [!WARNING]
> Visual Studio 2015'te başlayarak, C++ Standart Kitaplığı eşitleme türleri üzerinde Windows eşitleme temellerine temel alır ve artık ConcRT (hedef platformu Windows XP olduğunda hariç) kullanın. İçinde tanımlanmış türlere \<mutex > herhangi bir ConcRT türleri ve işlevleri ile birlikte kullanılmamalıdır.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<mutex >

**Namespace:** std

## <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Derlenmiş kodda **/CLR**, bu başlığı engellenir.

Sınıfları `mutex` ve `recursive_mutex` olan *mutex türleri*. Varsayılan bir oluşturucu ve özel durum oluşturmadığını bir yok edici bir mutex türü vardır. Bu nesneler, birden çok iş parçacığı aynı nesne kilitleme çalıştığınızda karşılıklı dışlama sağlayan yöntemler vardır. Özellikle, bir mutex türünü yöntemleri içeren `lock`, `try_lock`, ve `unlock`:

- `lock` Yöntemi iş parçacığı mutex sahipliğini alana kadar çağıran iş parçacığını engeller. Dönüş değeri yok sayıldı.

- `try_lock` Yöntemi engellemeden mutex bir sahipliğini almayı dener. Kendi dönüş türüne dönüştürülebilir **bool** ve **true** yöntemi sahipliğini alır, ancak aksi **false**.

- `unlock` Yöntemi çağıran iş parçacığından mutex sahipliğini serbest bırakır.

Şablonları örneklemek için tür bağımsız değişkeni olarak mutex türlerini kullanabilirsiniz `lock_guard` ve `unique_lock`. Nesne bu tür kullanabileceğiniz `Lock` şablondaki bekleme üye işlevler için bağımsız değişken [condition_variable_any](../standard-library/condition-variable-any-class.md).

A *mutex türünü zaman aşımına* mutex türü için gereksinimleri karşılar. Ayrıca, sahip `try_lock_for` ve `try_lock_until` bir bağımsız değişken kullanılarak çağrılabilir olmalıdır ve dönüştürülebilen bir türü döndürmelidir yöntemler **bool**. Tüm ek bağımsız değişkenleri varsayılan değerlere sahip olması koşuluyla zaman aşımına mutex türünü ek bağımsız değişkenler kullanarak bu işlevler tanımlayabilirsiniz.

- `try_lock_for` Metot olmalı çağrılabilir tek bir bağımsız değişken kullanarak `Rel_time`, türü olan örneklemesi [chrono::duration](../standard-library/duration-class.md). Yöntemi, mutex sahipliğini almayı dener, ancak tarafından belirlenen süre içinde döndürür `Rel_time`başarı ne olursa olsun. Dönüş değeri dönüştürür **true** sahipliği; yöntemi alır, aksi takdirde, dönüş değeri dönüştürür **false**.

- `try_lock_until` Metot olmalı çağrılabilir tek bir bağımsız değişken kullanarak `Abs_time`, türü olan örneklemesi [chrono::time_point](../standard-library/time-point-class.md). Yöntemi, mutex sahipliğini almayı dener, ancak tarafından belirlenen zamanı en geç döndürür `Abs_time`başarı ne olursa olsun. Dönüş değeri dönüştürür **true** sahipliği; yöntemi alır, aksi takdirde, dönüş değeri dönüştürür **false**.

Bir mutex türü olarak da bilinen, bir *kilitlenebilir türü*. Üye işlevi sağlamıyorsa `try_lock`, bunun bir *temel kilitlenebilir türü*. Bir zaman aşımına mutex türü olarak da bilinen, bir *kilitlenebilir türü zaman aşımına*.

## <a name="members"></a>Üyeler

### <a name="classes"></a>Sınıflar

|||
|-|-|
|[lock_guard Sınıfı](../standard-library/lock-guard-class.md)|Yok Edicisi kilidini açarak bir nesne oluşturmak için örneği bir şablonunu temsil eden bir `mutex`.|
|[mutex Sınıfı (C++ Standart Kitaplığı)](../standard-library/mutex-class-stl.md)|Mutex türünü temsil eder. Bir programın içinde karşılıklı dışlamayı zorlamak için bu tür nesnelerin kullanın.|
|[recursive_mutex Sınıfı](../standard-library/recursive-mutex-class.md)|Mutex türünü temsil eder. İçin constrast içinde `mutex` sınıfı zaten kilitli olan nesneler için kilitleme yöntemlerini çağırma davranıştır iyi tanımlanmış.|
|[recursive_timed_mutex Sınıfı](../standard-library/recursive-timed-mutex-class.md)|Zamanlanmış mutex türünü temsil eder. Bir program içindeki süre sınırlı engelleme olan karşılıklı dışlama zorlamak için bu tür nesnelerin kullanın. Türündeki nesneler aksine `timed_mutex`, kilitleme yöntemleri çağırma etkisini `recursive_timed_mutex` nesneleri, iyi tanımlanmış.|
|[scoped_lock sınıfı](../standard-library/scoped-lock-class.md)||
|[timed_mutex Sınıfı](../standard-library/timed-mutex-class.md)|Zamanlanmış mutex türünü temsil eder. Bir program içindeki süre sınırlı engelleme olan karşılıklı dışlama zorlamak için bu tür nesnelerin kullanın.|
|[unique_lock Sınıfı](../standard-library/unique-lock-class.md)|Kilitleme ve, kilidini açma yönetme nesneleri oluşturmak için örneği bir şablonunu temsil eden bir `mutex`.|

### <a name="functions"></a>İşlevler

|||
|-|-|
|[call_once](../standard-library/mutex-functions.md#call_once)|Yürütme sırasında tam bir kez belirli bir çağrılabilir nesnesini çağırmak için bir mekanizma sağlar.|
|[lock](../standard-library/mutex-functions.md#lock)|Tüm bağımsız değişkenler olmadan kilitlenme kilitlemek çalışır.|
|[değiştirme](../standard-library/mutex-functions.md#swap)||
|[try_lock](../standard-library/mutex-functions.md#try_lock)||

### <a name="structs"></a>Yapılar

|||
|-|-|
|[adopt_lock_t Yapısı](../standard-library/adopt-lock-t-structure.md)|Tanımlamak için kullanılan bir türü temsil eder bir `adopt_lock`.|
|[defer_lock_t Yapısı](../standard-library/defer-lock-t-structure.md)|Tanımlayan bir türünü temsil eden bir `defer_lock` aşırı yüklü oluşturucular birini seçmek için kullanılan nesne `unique_lock`.|
|[once_flag Yapısı](../standard-library/once-flag-structure.md)|Temsil eden bir **yapı** şablon işlevi ile kullanılan `call_once` başlatmanın emin olmak için kodu bile birden çok yürütme iş parçacığının varlığında yalnızca bir kez çağrılır.|
|[try_to_lock_t Yapısı](../standard-library/try-to-lock-t-structure.md)|Temsil eden bir **yapı** tanımlayan bir `try_to_lock` nesne ve aşırı yüklü oluşturucular birini seçmek için kullanılan `unique_lock`.|

### <a name="variables"></a>Değişkenler

|||
|-|-|
|[adopt_lock](../standard-library/mutex-functions.md#adopt_lock)|Oluşturucular için geçirilecek bir nesneyi temsil ediyor `lock_guard` ve `unique_lock` ayrıca oluşturucuya geçirilen mutex nesnesi kilitli olmadığını belirtmek için.|
|[defer_lock](../standard-library/mutex-functions.md#defer_lock)|İçin oluşturucuya geçirilen nesneyi temsil eden `unique_lock`Oluşturucu ayrıca için geçirilmiş mutex nesnesi kilitlemenizi değil belirtmek için.|
|[try_to_lock](../standard-library/mutex-functions.md#try_to_lock)|İçin oluşturucuya geçirilen nesneyi temsil eden `unique_lock` Oluşturucu kilidini açma denemesi gerektiğini belirtmek için `mutex` de yapan kendisine engellemeden.|

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
