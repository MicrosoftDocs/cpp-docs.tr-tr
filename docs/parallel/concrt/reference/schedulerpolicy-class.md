---
title: SchedulerPolicy Sınıfı
ms.date: 11/04/2016
f1_keywords:
- SchedulerPolicy
- concrt/concurrency::SchedulerPolicy
- concrt/concurrency::SchedulerPolicy::SchedulerPolicy
- concrt/concurrency::SchedulerPolicy::GetPolicyValue
- concrt/concurrency::SchedulerPolicy::SetConcurrencyLimits
- concrt/concurrency::SchedulerPolicy::SetPolicyValue
helpviewer_keywords:
- SchedulerPolicy class
ms.assetid: bcebf51a-65f8-45a3-809b-d1ff93527dc4
ms.openlocfilehash: 0d1c28501abc86d09b683b0ed91f831fe8697306
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50462057"
---
# <a name="schedulerpolicy-class"></a>SchedulerPolicy Sınıfı

`SchedulerPolicy` Sınıfı içeren bir zamanlayıcı örneğini davranışını denetleyen anahtar/değer çiftleri, her ilke öğesi için bir dizi.

## <a name="syntax"></a>Sözdizimi

```
class SchedulerPolicy;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[SchedulerPolicy](#ctor)|Fazla Yüklendi. Yeni bir zamanlayıcı ilkesi oluşturur ve ile doldurur [ilke anahtarları](concurrency-namespace-enums.md) eşzamanlılık çalışma zamanı planlayıcıları ve kaynak yöneticisi tarafından desteklenir.|
|[~ SchedulerPolicy yok Edicisi](#dtor)|Bir zamanlayıcı ilkesini yok eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[GetPolicyValue](#getpolicyvalue)|Olarak sağlanan ilke anahtarının değerini alır `key` parametresi.|
|[SetConcurrencyLimits](#setconcurrencylimits)|Aynı anda ayarlar `MinConcurrency` ve `MaxConcurrency` ilkeleri `SchedulerPolicy` nesne.|
|[SetPolicyValue](#setpolicyvalue)|Olarak sağlanan ilke anahtarının değerini ayarlar `key` parametresi ve eski değeri döndürür.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[operator=](#operator_eq)|Zamanlayıcı ilkesini başka bir zamanlayıcı ilkesini atar.|

## <a name="remarks"></a>Açıklamalar

Kullanılarak denetlenebilir ilkeleri hakkında daha fazla bilgi için `SchedulerPolicy` sınıfı [PolicyElementKey](concurrency-namespace-enums.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`SchedulerPolicy`

## <a name="requirements"></a>Gereksinimler

**Başlık:** concrt.h, concrtrm.h

**Namespace:** eşzamanlılık

##  <a name="getpolicyvalue"></a> GetPolicyValue

Olarak sağlanan ilke anahtarının değerini alır `key` parametresi.

```
unsigned int GetPolicyValue(PolicyElementKey key) const;
```

### <a name="parameters"></a>Parametreler

*Anahtarı*<br/>
İçin bir değer almak için ilke anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen anahtar `key` parametresi desteklenen, anahtar ilke değeri dönüştürüldü bir `unsigned int`.

### <a name="remarks"></a>Açıklamalar

Yöntemi [invalid_scheduler_policy_key](invalid-scheduler-policy-key-class.md) geçersiz ilke anahtarı.

##  <a name="operator_eq"></a> işleç =

Zamanlayıcı ilkesini başka bir zamanlayıcı ilkesini atar.

```
SchedulerPolicy& operator= (const SchedulerPolicy& _RhsPolicy);
```

### <a name="parameters"></a>Parametreler

*_RhsPolicy*<br/>
Bu ilkenin atanacağı ilke.

### <a name="return-value"></a>Dönüş Değeri

Zamanlayıcı ilkesini bir başvuru.

### <a name="remarks"></a>Açıklamalar

Genellikle, varolan bir ilkeyi kopyalamak ve kullanarak değiştirmek için yeni bir zamanlayıcı ilkesini tanımlamanın en kolay yolu olan `SetPolicyValue` veya `SetConcurrencyLimits` yöntemleri.

##  <a name="ctor"></a> SchedulerPolicy

Yeni bir zamanlayıcı ilkesi oluşturur ve ile doldurur [ilke anahtarları](concurrency-namespace-enums.md) eşzamanlılık çalışma zamanı planlayıcıları ve kaynak yöneticisi tarafından desteklenir.

```
SchedulerPolicy();

SchedulerPolicy(
    size_t _PolicyKeyCount,
...);

SchedulerPolicy(
    const SchedulerPolicy& _SrcPolicy);
```

### <a name="parameters"></a>Parametreler

*_PolicyKeyCount*<br/>
Sayısı, anahtar/değer çiftlerini izleyen `_PolicyKeyCount` parametresi.

*_SrcPolicy*<br/>
Kopyalanacak kaynak ilkesi.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu, tüm ilkelerin varsayılan değerlerine burada başlatılacağı yeni bir zamanlayıcı ilkesi oluşturur.

İkinci oluşturucu isimli parametre stili başlatma kullanan yeni bir zamanlayıcı ilkesi oluşturur. Sonraki değerler `_PolicyKeyCount` parametresi, anahtar/değer çiftleri sağlanır. Bu oluşturucu içinde belirtilmemiş ilke anahtarları kendi varsayılan değerine sahip olacaktır. Bu oluşturucu özel durumlarını oluşturabilir [invalid_scheduler_policy_key](invalid-scheduler-policy-key-class.md), [invalid_scheduler_policy_value](invalid-scheduler-policy-value-class.md) veya [invalid_scheduler_policy_thread_specification](invalid-scheduler-policy-thread-specification-class.md).

Üçüncü Oluşturucu bir kopya oluşturucudur. Genellikle, varolan bir ilkeyi kopyalamak ve kullanarak değiştirmek için yeni bir zamanlayıcı ilkesini tanımlamanın en kolay yolu olan `SetPolicyValue` veya `SetConcurrencyLimits` yöntemleri.

##  <a name="dtor"></a> ~ SchedulerPolicy

Bir zamanlayıcı ilkesini yok eder.

```
~SchedulerPolicy();
```

##  <a name="setconcurrencylimits"></a> SetConcurrencyLimits

Aynı anda ayarlar `MinConcurrency` ve `MaxConcurrency` ilkeleri `SchedulerPolicy` nesne.

```
void SetConcurrencyLimits(
    unsigned int _MinConcurrency,
    unsigned int _MaxConcurrency = MaxExecutionResources);
```

### <a name="parameters"></a>Parametreler

*_MinConcurrency*<br/>
Değeri `MinConcurrency` ilke anahtarı.

*_MaxConcurrency*<br/>
Değeri `MaxConcurrency` ilke anahtarı.

### <a name="remarks"></a>Açıklamalar

Yöntemi [invalid_scheduler_policy_thread_specification](invalid-scheduler-policy-thread-specification-class.md) için belirtilen değer, `MinConcurrency` ilkesi için belirtilen'den büyük `MaxConcurrency` ilkesi.

Yöntemi de oluşturabilecek [invalid_scheduler_policy_value](invalid-scheduler-policy-value-class.md) diğer geçersiz değerler için.

##  <a name="setpolicyvalue"></a> SetPolicyValue

Olarak sağlanan ilke anahtarının değerini ayarlar `key` parametresi ve eski değeri döndürür.

```
unsigned int SetPolicyValue(
    PolicyElementKey key,
    unsigned int value);
```

### <a name="parameters"></a>Parametreler

*Anahtarı*<br/>
İçin bir değer ayarlamak için ilke anahtarı.

*value*<br/>
İlke anahtarı ayarlanacak değer.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen anahtar `key` parametresi desteklenen, anahtar eski ilke değeri dönüştürüldü bir `unsigned int`.

### <a name="remarks"></a>Açıklamalar

Yöntemi [invalid_scheduler_policy_key](invalid-scheduler-policy-key-class.md) geçersiz ilke anahtarı veya değeri tarafından ayarlanamaz ilke anahtarları `SetPolicyValue` yöntemi.

Yöntemi [invalid_scheduler_policy_value](invalid-scheduler-policy-value-class.md) tarafından belirtilen anahtar için desteklenmeyen bir değer için `key` parametresi.

Bu yöntem ayarlamak için izin verilmiyor Not `MinConcurrency` veya `MaxConcurrency` ilkeleri. Bu değerleri ayarlamak için kullanın [SetConcurrencyLimits](#setconcurrencylimits) yöntemi.

## <a name="see-also"></a>Ayrıca Bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[PolicyElementKey](concurrency-namespace-enums.md)<br/>
[CurrentScheduler Sınıfı](currentscheduler-class.md)<br/>
[Zamanlayıcı Sınıfı](scheduler-class.md)<br/>
[Görev Zamanlayıcısı](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)

