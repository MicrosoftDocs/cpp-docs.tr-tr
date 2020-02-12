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
ms.openlocfilehash: fed33c198502b75e824bcaf698227d283f4b85f9
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142748"
---
# <a name="schedulerpolicy-class"></a>SchedulerPolicy Sınıfı

`SchedulerPolicy` sınıfı, bir Zamanlayıcı örneğinin davranışını denetleyen her ilke öğesi için bir olan anahtar/değer çiftleri kümesi içerir.

## <a name="syntax"></a>Sözdizimi

```cpp
class SchedulerPolicy;
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[SchedulerPolicy](#ctor)|Fazla Yüklendi. Yeni bir Zamanlayıcı İlkesi oluşturur ve Eşzamanlılık Çalışma Zamanı zamanlayıcılar ve Kaynak Yöneticisi tarafından desteklenen [ilke anahtarlarının](concurrency-namespace-enums.md) değerleriyle doldurur.|
|[~ SchedulerPolicy yıkıcısı](#dtor)|Zamanlayıcı ilkesini yok eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[GetPolicyValue](#getpolicyvalue)|`key` parametresi olarak sağlanan ilke anahtarının değerini alır.|
|[SetConcurrencyLimits](#setconcurrencylimits)|`SchedulerPolicy` nesnesindeki `MinConcurrency` ve `MaxConcurrency` ilkelerini eşzamanlı olarak ayarlar.|
|[SetPolicyValue](#setpolicyvalue)|`key` parametresi olarak sağlanan ilke anahtarının değerini ayarlar ve eski değeri döndürür.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[işleç =](#operator_eq)|Zamanlayıcı ilkesini başka bir Zamanlayıcı ilkesinden atar.|

## <a name="remarks"></a>Açıklamalar

`SchedulerPolicy` sınıfı kullanılarak denetlenebilecek ilkeler hakkında daha fazla bilgi için, bkz. [PolicyElementKey](concurrency-namespace-enums.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`SchedulerPolicy`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrt. h, concrtrm. h

**Ad alanı:** eşzamanlılık

## <a name="getpolicyvalue"></a>GetPolicyValue

`key` parametresi olarak sağlanan ilke anahtarının değerini alır.

```cpp
unsigned int GetPolicyValue(PolicyElementKey key) const;
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
İçin bir değer alınacak ilke anahtarı.

### <a name="return-value"></a>Dönüş Değeri

`key` parametresi tarafından belirtilen anahtar destekleniyorsa, anahtarın bir `unsigned int`ataması için ilke değeri.

### <a name="remarks"></a>Açıklamalar

Yöntem geçersiz bir ilke anahtarı için [invalid_scheduler_policy_key](invalid-scheduler-policy-key-class.md) oluşturacak.

## <a name="operator_eq"></a>işleç =

Zamanlayıcı ilkesini başka bir Zamanlayıcı ilkesinden atar.

```cpp
SchedulerPolicy& operator= (const SchedulerPolicy& _RhsPolicy);
```

### <a name="parameters"></a>Parametreler

*_RhsPolicy*<br/>
Bu ilkeye atanacak ilke.

### <a name="return-value"></a>Dönüş Değeri

Zamanlayıcı ilkesine bir başvuru.

### <a name="remarks"></a>Açıklamalar

Genellikle, yeni bir Zamanlayıcı İlkesi tanımlamanın en kolay yolu, mevcut bir ilkeyi kopyalamak ve `SetPolicyValue` veya `SetConcurrencyLimits` yöntemlerini kullanarak değiştirmektir.

## <a name="ctor"></a>SchedulerPolicy

Yeni bir Zamanlayıcı İlkesi oluşturur ve Eşzamanlılık Çalışma Zamanı zamanlayıcılar ve Kaynak Yöneticisi tarafından desteklenen [ilke anahtarlarının](concurrency-namespace-enums.md) değerleriyle doldurur.

```cpp
SchedulerPolicy();

SchedulerPolicy(
    size_t _PolicyKeyCount,
...);

SchedulerPolicy(
    const SchedulerPolicy& _SrcPolicy);
```

### <a name="parameters"></a>Parametreler

*_PolicyKeyCount*<br/>
`_PolicyKeyCount` parametresini izleyen anahtar/değer çiftleri sayısı.

*_SrcPolicy*<br/>
Kopyalanacak kaynak ilkesi.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu, tüm ilkelerin varsayılan değerlerine başlatıldığı yeni bir Zamanlayıcı İlkesi oluşturur.

İkinci Oluşturucu, başlatma adlandırılmış parametre stilini kullanan yeni bir Zamanlayıcı İlkesi oluşturur. `_PolicyKeyCount` parametresinden sonraki değerler anahtar/değer çiftleri olarak sağlanır. Bu oluşturucuda belirtilmeyen herhangi bir ilke anahtarı varsayılan değerine sahip olacaktır. Bu Oluşturucu [invalid_scheduler_policy_key](invalid-scheduler-policy-key-class.md), [invalid_scheduler_policy_value](invalid-scheduler-policy-value-class.md) veya [invalid_scheduler_policy_thread_specification](invalid-scheduler-policy-thread-specification-class.md)özel durumları oluşturabilir.

Üçüncü Oluşturucu bir kopya oluşturucudur. Genellikle, yeni bir Zamanlayıcı İlkesi tanımlamanın en kolay yolu, mevcut bir ilkeyi kopyalamak ve `SetPolicyValue` veya `SetConcurrencyLimits` yöntemlerini kullanarak değiştirmektir.

## <a name="dtor"></a>~ SchedulerPolicy

Zamanlayıcı ilkesini yok eder.

```cpp
~SchedulerPolicy();
```

## <a name="setconcurrencylimits"></a>SetConcurrencyLimits

`SchedulerPolicy` nesnesindeki `MinConcurrency` ve `MaxConcurrency` ilkelerini eşzamanlı olarak ayarlar.

```cpp
void SetConcurrencyLimits(
    unsigned int _MinConcurrency,
    unsigned int _MaxConcurrency = MaxExecutionResources);
```

### <a name="parameters"></a>Parametreler

*_MinConcurrency*<br/>
`MinConcurrency` ilkesi anahtarının değeri.

*_MaxConcurrency*<br/>
`MaxConcurrency` ilkesi anahtarının değeri.

### <a name="remarks"></a>Açıklamalar

`MinConcurrency` ilkesi için belirtilen değer `MaxConcurrency` ilkesi için belirtilenden daha büyükse Yöntem [invalid_scheduler_policy_thread_specification](invalid-scheduler-policy-thread-specification-class.md) oluşturur.

Yöntemi, diğer geçersiz değerler için [invalid_scheduler_policy_value](invalid-scheduler-policy-value-class.md) de oluşturabilir.

## <a name="setpolicyvalue"></a>SetPolicyValue

`key` parametresi olarak sağlanan ilke anahtarının değerini ayarlar ve eski değeri döndürür.

```cpp
unsigned int SetPolicyValue(
    PolicyElementKey key,
    unsigned int value);
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
İçin bir değer ayarlanacak ilke anahtarı.

*value*<br/>
İlke anahtarının ayarlanacağı değer.

### <a name="return-value"></a>Dönüş Değeri

`key` parametresi tarafından belirtilen anahtar destekleniyorsa, anahtar için eski ilke değeri bir `unsigned int`.

### <a name="remarks"></a>Açıklamalar

Yöntemi, geçersiz bir ilke anahtarı ya da değeri `SetPolicyValue` yöntemi tarafından ayarlanmayacak olan herhangi bir ilke anahtarı için [invalid_scheduler_policy_key](invalid-scheduler-policy-key-class.md) oluşturur.

Yöntem, `key` parametresi tarafından belirtilen anahtar için desteklenmeyen bir değer için [invalid_scheduler_policy_value](invalid-scheduler-policy-value-class.md) oluşturur.

Bu yöntemin `MinConcurrency` veya `MaxConcurrency` ilkelerini ayarlamaya izin verilmediğini unutmayın. Bu değerleri ayarlamak için [SetConcurrencyLimits](#setconcurrencylimits) yöntemini kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[PolicyElementKey](concurrency-namespace-enums.md)<br/>
[CurrentScheduler Sınıfı](currentscheduler-class.md)<br/>
[Zamanlayıcı Sınıfı](scheduler-class.md)<br/>
[Görev Zamanlayıcı](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)
