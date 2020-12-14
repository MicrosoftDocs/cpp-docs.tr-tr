---
description: 'Daha fazla bilgi edinin: SchedulerPolicy Class'
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
ms.openlocfilehash: 2bb4c8961f46f077c203d1a49fb352171ad3f318
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97188709"
---
# <a name="schedulerpolicy-class"></a>SchedulerPolicy Sınıfı

Sınıfı, bir `SchedulerPolicy` Zamanlayıcı örneğinin davranışını denetleyen her ilke öğesi için bir olan anahtar/değer çiftleri kümesi içerir.

## <a name="syntax"></a>Syntax

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
|[GetPolicyValue](#getpolicyvalue)|Parametre olarak sağlanan ilke anahtarının değerini alır `key` .|
|[SetConcurrencyLimits](#setconcurrencylimits)|Aynı anda `MinConcurrency` `MaxConcurrency` nesne üzerindeki ve ilkelerini ayarlar `SchedulerPolicy` .|
|[SetPolicyValue](#setpolicyvalue)|Parametre olarak sağlanan ilke anahtarının değerini ayarlar `key` ve eski değeri döndürür.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[işleç =](#operator_eq)|Zamanlayıcı ilkesini başka bir Zamanlayıcı ilkesinden atar.|

## <a name="remarks"></a>Açıklamalar

Sınıfı kullanılarak denetlenebilecek ilkeler hakkında daha fazla bilgi için `SchedulerPolicy` bkz. [PolicyElementKey](concurrency-namespace-enums.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`SchedulerPolicy`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrt. h, concrtrm. h

**Ad alanı:** eşzamanlılık

## <a name="getpolicyvalue"></a><a name="getpolicyvalue"></a> GetPolicyValue

Parametre olarak sağlanan ilke anahtarının değerini alır `key` .

```cpp
unsigned int GetPolicyValue(PolicyElementKey key) const;
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
İçin bir değer alınacak ilke anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Parametresi tarafından belirtilen anahtar `key` destekleniyorsa, anahtar için ilke değeri bir olarak ayarlanır **`unsigned int`** .

### <a name="remarks"></a>Açıklamalar

Yöntem geçersiz bir ilke anahtarı için [invalid_scheduler_policy_key](invalid-scheduler-policy-key-class.md) oluşturacak.

## <a name="operator"></a><a name="operator_eq"></a> işleç =

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

Genellikle, yeni bir Zamanlayıcı İlkesi tanımlamanın en kolay yolu, mevcut bir ilkeyi kopyalamak ve `SetPolicyValue` veya yöntemlerini kullanarak değiştirmektir `SetConcurrencyLimits` .

## <a name="schedulerpolicy"></a><a name="ctor"></a> SchedulerPolicy

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
Parametreyi izleyen anahtar/değer çiftleri sayısı `_PolicyKeyCount` .

*_SrcPolicy*<br/>
Kopyalanacak kaynak ilkesi.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu, tüm ilkelerin varsayılan değerlerine başlatıldığı yeni bir Zamanlayıcı İlkesi oluşturur.

İkinci Oluşturucu, başlatma adlandırılmış parametre stilini kullanan yeni bir Zamanlayıcı İlkesi oluşturur. Parametreden sonraki değerler `_PolicyKeyCount` anahtar/değer çiftleri olarak sağlanır. Bu oluşturucuda belirtilmeyen herhangi bir ilke anahtarı varsayılan değerine sahip olacaktır. Bu Oluşturucu [invalid_scheduler_policy_key](invalid-scheduler-policy-key-class.md), [invalid_scheduler_policy_value](invalid-scheduler-policy-value-class.md) veya [invalid_scheduler_policy_thread_specification](invalid-scheduler-policy-thread-specification-class.md)özel durumları oluşturabilir.

Üçüncü Oluşturucu bir kopya oluşturucudur. Genellikle, yeni bir Zamanlayıcı İlkesi tanımlamanın en kolay yolu, mevcut bir ilkeyi kopyalamak ve `SetPolicyValue` veya yöntemlerini kullanarak değiştirmektir `SetConcurrencyLimits` .

## <a name="schedulerpolicy"></a><a name="dtor"></a> ~ SchedulerPolicy

Zamanlayıcı ilkesini yok eder.

```cpp
~SchedulerPolicy();
```

## <a name="setconcurrencylimits"></a><a name="setconcurrencylimits"></a> SetConcurrencyLimits

Aynı anda `MinConcurrency` `MaxConcurrency` nesne üzerindeki ve ilkelerini ayarlar `SchedulerPolicy` .

```cpp
void SetConcurrencyLimits(
    unsigned int _MinConcurrency,
    unsigned int _MaxConcurrency = MaxExecutionResources);
```

### <a name="parameters"></a>Parametreler

*_MinConcurrency*<br/>
`MinConcurrency`İlke anahtarının değeri.

*_MaxConcurrency*<br/>
`MaxConcurrency`İlke anahtarının değeri.

### <a name="remarks"></a>Açıklamalar

İlke için belirtilen değer [](invalid-scheduler-policy-thread-specification-class.md) `MinConcurrency` ilke için belirtilenden daha büyükse Yöntem invalid_scheduler_policy_thread_specification oluşturur `MaxConcurrency` .

Yöntemi, diğer geçersiz değerler için [invalid_scheduler_policy_value](invalid-scheduler-policy-value-class.md) de oluşturabilir.

## <a name="setpolicyvalue"></a><a name="setpolicyvalue"></a> SetPolicyValue

Parametre olarak sağlanan ilke anahtarının değerini ayarlar `key` ve eski değeri döndürür.

```cpp
unsigned int SetPolicyValue(
    PolicyElementKey key,
    unsigned int value);
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
İçin bir değer ayarlanacak ilke anahtarı.

*değer*<br/>
İlke anahtarının ayarlanacağı değer.

### <a name="return-value"></a>Dönüş Değeri

Parametresi tarafından belirtilen anahtar `key` destekleniyorsa, anahtar için eski ilke değeri bir olarak ayarlanır **`unsigned int`** .

### <a name="remarks"></a>Açıklamalar

Yöntemi, geçersiz bir ilke anahtarı ya da değeri yöntemiyle ayarlanmayacak olan herhangi bir ilke anahtarı için [invalid_scheduler_policy_key](invalid-scheduler-policy-key-class.md) oluşturur `SetPolicyValue` .

Yöntemi, parametresi tarafından belirtilen anahtar için desteklenmeyen bir değer için [invalid_scheduler_policy_value](invalid-scheduler-policy-value-class.md) oluşturur `key` .

Bu yöntemin veya ilkeleri ayarlamaya izin verilmediğini unutmayın `MinConcurrency` `MaxConcurrency` . Bu değerleri ayarlamak için [SetConcurrencyLimits](#setconcurrencylimits) yöntemini kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)<br/>
[PolicyElementKey](concurrency-namespace-enums.md)<br/>
[CurrentScheduler sınıfı](currentscheduler-class.md)<br/>
[Zamanlayıcı sınıfı](scheduler-class.md)<br/>
[Görev Zamanlayıcı](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)
