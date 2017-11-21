---
title: "SchedulerPolicy sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SchedulerPolicy
- concrt/concurrency::SchedulerPolicy
- concrt/concurrency::SchedulerPolicy::SchedulerPolicy
- concrt/concurrency::SchedulerPolicy::GetPolicyValue
- concrt/concurrency::SchedulerPolicy::SetConcurrencyLimits
- concrt/concurrency::SchedulerPolicy::SetPolicyValue
dev_langs: C++
helpviewer_keywords: SchedulerPolicy class
ms.assetid: bcebf51a-65f8-45a3-809b-d1ff93527dc4
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 289c505cc66e70a9634e3c183ae9511d99276940
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="schedulerpolicy-class"></a>SchedulerPolicy Sınıfı
`SchedulerPolicy` Sınıfı bir zamanlayıcı örneğini davranışını denetleyen anahtar/değer çifti kümesi, her ilke öğesi için bir tane içeriyor.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class SchedulerPolicy;
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[SchedulerPolicy](#ctor)|Fazla Yüklendi. Yeni bir zamanlayıcı ilkesi oluşturur ve için değerlerle doldurur [İlkesi anahtarları](concurrency-namespace-enums.md) eşzamanlılık çalışma zamanı zamanlayıcılar ve kaynak yöneticisi tarafından desteklenir.|  
|[~ SchedulerPolicy yok Edicisi](#dtor)|Bir zamanlayıcı ilke yok eder.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[GetPolicyValue](#getpolicyvalue)|Sağlanan ilke anahtarının değeri olarak alır `key` parametresi.|  
|[SetConcurrencyLimits](#setconcurrencylimits)|Aynı anda ayarlar `MinConcurrency` ve `MaxConcurrency` ilkeleri `SchedulerPolicy` nesnesi.|  
|[SetPolicyValue](#setpolicyvalue)|Sağlanan ilke anahtarının değeri olarak ayarlar `key` parametre ve eski değer döndürür.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[işleç =](#operator_eq)|Zamanlayıcı İlkesi başka bir zamanlayıcı ilkesinden atar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanılarak denetlenebilir ilkeleri hakkında daha fazla bilgi için `SchedulerPolicy` sınıfı için bkz: [PolicyElementKey](concurrency-namespace-enums.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `SchedulerPolicy`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** concrt.h, concrtrm.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="getpolicyvalue"></a>GetPolicyValue 

 Sağlanan ilke anahtarının değeri olarak alır `key` parametresi.  
  
```
unsigned int GetPolicyValue(PolicyElementKey key) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `key`  
 İçin bir değer almak için ilke anahtarı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Anahtar belirtilen `key` parametresi desteklenmiyor, anahtar için ilke değeri dönüştürmek için bir `unsigned int`.  
  
### <a name="remarks"></a>Açıklamalar  
 Yöntemi özel durum oluşturacak [invalid_scheduler_policy_key](invalid-scheduler-policy-key-class.md) geçersiz ilke anahtarı için.  
  
##  <a name="operator_eq"></a>işleç = 

 Zamanlayıcı İlkesi başka bir zamanlayıcı ilkesinden atar.  
  
```
SchedulerPolicy& operator= (const SchedulerPolicy& _RhsPolicy);
```  
  
### <a name="parameters"></a>Parametreler  
 `_RhsPolicy`  
 Bu ilke atama ilkesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Zamanlayıcı İlkesi referansı.  
  
### <a name="remarks"></a>Açıklamalar  
 Genellikle, yeni bir zamanlayıcı ilke tanımlamak için en uygun mevcut bir ilkeyi kopyalayın ve kullanarak değiştirmek için yoludur `SetPolicyValue` veya `SetConcurrencyLimits` yöntemleri.  
  
##  <a name="ctor"></a>SchedulerPolicy 

 Yeni bir zamanlayıcı ilkesi oluşturur ve için değerlerle doldurur [İlkesi anahtarları](concurrency-namespace-enums.md) eşzamanlılık çalışma zamanı zamanlayıcılar ve kaynak yöneticisi tarafından desteklenir.  
  
```
SchedulerPolicy();

SchedulerPolicy(
    size_t _PolicyKeyCount,
 ...);

SchedulerPolicy(
    const SchedulerPolicy& _SrcPolicy);
```  
  
### <a name="parameters"></a>Parametreler  
 `_PolicyKeyCount`  
 Sayısı, anahtar/değer çiftleri anlatılmaktadır `_PolicyKeyCount` parametresi.  
  
 `_SrcPolicy`  
 Kopyalanacak kaynak ilkesi.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk Oluşturucusu tüm ilkeler varsayılan değerlerine burada başlatılacak yeni bir zamanlayıcı ilkesi oluşturur.  
  
 İkinci oluşturucu başlatma adlı parametre stili kullanan yeni bir zamanlayıcı ilkesi oluşturur. Sonra değerleri `_PolicyKeyCount` parametresi, anahtar/değer çiftleri olarak sağlanır. Bu oluşturucuda belirtilen olmayan herhangi bir ilke tuşa kendi varsayılan değere sahip. Bu oluşturucu özel durumlar oluşturma [invalid_scheduler_policy_key](invalid-scheduler-policy-key-class.md), [invalid_scheduler_policy_value](invalid-scheduler-policy-value-class.md) veya [invalid_scheduler_policy_thread_specification](invalid-scheduler-policy-thread-specification-class.md).  
  
 Üçüncü Oluşturucusu kopya Oluşturucu ' dir. Genellikle, yeni bir zamanlayıcı ilke tanımlamak için en uygun mevcut bir ilkeyi kopyalayın ve kullanarak değiştirmek için yoludur `SetPolicyValue` veya `SetConcurrencyLimits` yöntemleri.  
  
##  <a name="dtor"></a>~ SchedulerPolicy 

 Bir zamanlayıcı ilke yok eder.  
  
```
~SchedulerPolicy();
```  
  
##  <a name="setconcurrencylimits"></a>SetConcurrencyLimits 

 Aynı anda ayarlar `MinConcurrency` ve `MaxConcurrency` ilkeleri `SchedulerPolicy` nesnesi.  
  
```
void SetConcurrencyLimits(
    unsigned int _MinConcurrency,
    unsigned int _MaxConcurrency = MaxExecutionResources);
```  
  
### <a name="parameters"></a>Parametreler  
 `_MinConcurrency`  
 Değeri `MinConcurrency` ilke anahtarı.  
  
 `_MaxConcurrency`  
 Değeri `MaxConcurrency` ilke anahtarı.  
  
### <a name="remarks"></a>Açıklamalar  
 Yöntemi özel durum oluşturacak [invalid_scheduler_policy_thread_specification](invalid-scheduler-policy-thread-specification-class.md) için belirtilen değer, `MinConcurrency` ilkesi için belirtilen'den büyük `MaxConcurrency` ilkesi.  
  
 Yöntemi de atabilirsiniz [invalid_scheduler_policy_value](invalid-scheduler-policy-value-class.md) diğer geçersiz değerler için.  
  
##  <a name="setpolicyvalue"></a>SetPolicyValue 

 Sağlanan ilke anahtarının değeri olarak ayarlar `key` parametre ve eski değer döndürür.  
  
```
unsigned int SetPolicyValue(
    PolicyElementKey key,
    unsigned int value);
```  
  
### <a name="parameters"></a>Parametreler  
 `key`  
 İçin bir değer ayarlamak için ilke anahtarı.  
  
 `value`  
 İlke anahtarın ayarlanacağı değer.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Anahtar belirtilen `key` parametresi desteklenmiyor, anahtar eski ilke değeri dönüştürmek için bir `unsigned int`.  
  
### <a name="remarks"></a>Açıklamalar  
 Yöntemi özel durum oluşturacak [invalid_scheduler_policy_key](invalid-scheduler-policy-key-class.md) bir ilke geçersiz anahtar veya değeri tarafından ayarlanamaz herhangi bir ilke tuşa `SetPolicyValue` yöntemi.  
  
 Yöntemi özel durum oluşturacak [invalid_scheduler_policy_value](invalid-scheduler-policy-value-class.md) tarafından belirtilen anahtar için desteklenmeyen bir değeri `key` parametresi.  
  
 Bu yöntem ayarlamak için izin verilmiyor Not `MinConcurrency` veya `MaxConcurrency` ilkeleri. Bu değerleri ayarlamak için kullanma [SetConcurrencyLimits](#setconcurrencylimits) yöntemi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)   
 [PolicyElementKey](concurrency-namespace-enums.md)   
 [CurrentScheduler sınıfı](currentscheduler-class.md)   
 [Zamanlayıcı sınıfı](scheduler-class.md)   
 [Görev Zamanlayıcısı](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)



