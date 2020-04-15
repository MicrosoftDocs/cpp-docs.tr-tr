---
title: IResourceManager Yapısı
ms.date: 03/27/2019
f1_keywords:
- IResourceManager
- CONCRTRM/concurrency::IResourceManager
- CONCRTRM/concurrency::IResourceManager::IResourceManager::OSVersion
- CONCRTRM/concurrency::IResourceManager::IResourceManager::CreateNodeTopology
- CONCRTRM/concurrency::IResourceManager::IResourceManager::GetAvailableNodeCount
- CONCRTRM/concurrency::IResourceManager::IResourceManager::GetFirstNode
- CONCRTRM/concurrency::IResourceManager::IResourceManager::Reference
- CONCRTRM/concurrency::IResourceManager::IResourceManager::RegisterScheduler
- CONCRTRM/concurrency::IResourceManager::IResourceManager::Release
helpviewer_keywords:
- IResourceManager structure
ms.assetid: 3dd5ec2c-fe53-4121-ae77-1bc1d1167ff4
ms.openlocfilehash: 15e27a586fc039791255c01a053f6a1109183f90
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368182"
---
# <a name="iresourcemanager-structure"></a>IResourceManager Yapısı

Eşzamanlı Çalışma Zamanı Kaynak Yöneticisi'ne bir arabirim. Bu, zamanlayıcıların Kaynak Yöneticisi ile iletişim kurduğu arabirimdir.

## <a name="syntax"></a>Sözdizimi

```cpp
struct IResourceManager;
```

## <a name="members"></a>Üyeler

### <a name="public-enumerations"></a>Genel Hesaplamalar

|Adı|Açıklama|
|----------|-----------------|
|[IResourceManager::OSVersion](#osversion)|İşletim sistemi sürümünü temsil eden numaralandırılmış tür.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[IResourceManager::CreateNodeTopology](#createnodetopology)|Yalnızca çalışma zamanı hata ayıklama yapılarında bulunan bu yöntem, yapılandırmayla eşleşen gerçek donanımgerektirmeden Kaynak Yöneticisi'nin farklı donanım topolojileri üzerinde test ini kolaylaştırmak için tasarlanmış bir test kancasıdır. Çalışma zamanının perakende yapılarıyla, bu yöntem herhangi bir işlem gerçekleştirmeden geri döner.|
|[IResourceManager::GetAvailableNodeCount](#getavailablenodecount)|Kaynak Yöneticisi'ne kullanılabilen düğüm sayısını verir.|
|[IResourceManager::GetFirstNode](#getfirstnode)|Kaynak Yöneticisi tarafından tanımlanan numaralandırma emrindeki ilk düğümü döndürür.|
|[IResourceManager::Başvuru](#reference)|Kaynak Yöneticisi örneğinde başvuru sayısını artırımı.|
|[IResourceManager::RegisterScheduler](#registerscheduler)|Kaynak Yöneticisi'ne bir zamanlayıcı kaydeder. Zamanlayıcı kaydedildikten sonra, döndürülen `ISchedulerProxy` arabirimi kullanarak Kaynak Yöneticisi ile iletişim kurması gerekir.|
|[IResourceManager::Sürüm](#release)|Kaynak Yöneticisi örneğinde başvuru sayısını verir. Kaynak Yöneticisi, başvuru sayısı `0`.|

## <a name="remarks"></a>Açıklamalar

Singleton Resource Manager örneğine bir arabirim elde etmek için [CreateResourceManager](concurrency-namespace-functions.md) işlevini kullanın. Yöntem, Kaynak Yöneticisi'ne bir başvuru sayısı verir ve Kaynak Yöneticisi ile yaptığınızda başvuruyu serbest bırakmak için [IResourceManager::Release](#release) yöntemini çağırmalısınız. Genellikle, oluşturduğunuz her zamanlayıcı oluşturma sırasında bu yöntemi çağırır ve kapatıldıktan sonra Kaynak Yöneticisi'ne başvuru bırakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IResourceManager`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrtrm.h

**Ad alanı:** eşzamanlılık

## <a name="iresourcemanagercreatenodetopology-method"></a><a name="createnodetopology"></a>IResourceManager::CreateNodeTopology Yöntemi

Yalnızca çalışma zamanı hata ayıklama yapılarında bulunan bu yöntem, yapılandırmayla eşleşen gerçek donanımgerektirmeden Kaynak Yöneticisi'nin farklı donanım topolojileri üzerinde test ini kolaylaştırmak için tasarlanmış bir test kancasıdır. Çalışma zamanının perakende yapılarıyla, bu yöntem herhangi bir işlem gerçekleştirmeden geri döner.

```cpp
virtual void CreateNodeTopology(
    unsigned int nodeCount,
    _In_reads_(nodeCount) unsigned int* pCoreCount,
    _In_reads_opt_(nodeCount) unsigned int** pNodeDistance,
    _In_reads_(nodeCount) unsigned int* pProcessorGroups) = 0;
```

### <a name="parameters"></a>Parametreler

*düğümSayısı*<br/>
Simüle edilen işlemci düğümlerinin sayısı.

*pCoreCount*<br/>
Her düğümdeki çekirdek sayısını belirten bir dizi.

*pNodeDistance*<br/>
Herhangi iki düğüm arasındaki düğüm uzaklığı belirten bir matris. Bu parametre değerine `NULL`sahip olabilir.

*pİşlemer Grupları*<br/>
İşlemci grubunu belirten bir dizi, her düğüme aittir.

### <a name="remarks"></a>Açıklamalar

[invalid_argument,](../../../standard-library/invalid-argument-class.md) parametrenin `nodeCount` değeri `0` geçtiyse veya parametrede `pCoreCount` değer `NULL`varsa atılır.

Bu yöntem, işlemsırasında diğer zamanlayıcılar varken bu yöntem çağrılırsa [invalid_operation](invalid-operation-class.md) atılır.

## <a name="iresourcemanagergetavailablenodecount-method"></a><a name="getavailablenodecount"></a>IResourceManager::GetAvailableNodeCount Yöntemi

Kaynak Yöneticisi'ne kullanılabilen düğüm sayısını verir.

```cpp
virtual unsigned int GetAvailableNodeCount() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Kaynak Yöneticisi'nin kullanabileceği düğüm sayısı.

## <a name="iresourcemanagergetfirstnode-method"></a><a name="getfirstnode"></a>IResourceManager::GetFirstNode Yöntemi

Kaynak Yöneticisi tarafından tanımlanan numaralandırma emrindeki ilk düğümü döndürür.

```cpp
virtual ITopologyNode* GetFirstNode() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Kaynak Yöneticisi tarafından tanımlanan numaralandırma düzenindeki ilk düğüm.

## <a name="iresourcemanagerosversion-enumeration"></a><a name="osversion"></a>IResourceManager::OSVersion Numaralandırma

İşletim sistemi sürümünü temsil eden numaralandırılmış tür.

```cpp
enum OSVersion;
```

## <a name="iresourcemanagerreference-method"></a><a name="reference"></a>IResourceManager::Başvuru Yöntemi

Kaynak Yöneticisi örneğinde başvuru sayısını artırımı.

```cpp
virtual unsigned int Reference() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Ortaya çıkan başvuru sayısı.

## <a name="iresourcemanagerregisterscheduler-method"></a><a name="registerscheduler"></a>IResourceManager::RegisterScheduler Yöntemi

Kaynak Yöneticisi'ne bir zamanlayıcı kaydeder. Zamanlayıcı kaydedildikten sonra, döndürülen `ISchedulerProxy` arabirimi kullanarak Kaynak Yöneticisi ile iletişim kurması gerekir.

```cpp
virtual ISchedulerProxy *RegisterScheduler(
    _Inout_ IScheduler* pScheduler,
    unsigned int version) = 0;
```

### <a name="parameters"></a>Parametreler

*pScheduler*<br/>
Kaydedilecek zamanlayıcıya bir `IScheduler` arabirim.

*Sürüm*<br/>
Zamanlayıcının Kaynak Yöneticisi ile iletişim kurmak için kullandığı iletişim arabiriminin sürümü. Sürüm kullanmak, Zamanlayıcıların eski özelliklere erişmesine izin verirken Kaynak Yöneticisi'nin iletişim arabirimini geliştirmesine olanak tanır. Visual Studio 2010'da bulunan Kaynak Yöneticisi özelliklerini kullanmak `CONCRT_RM_VERSION_1`isteyen zamanlayıcılar bu sürümü kullanmalıdır.

### <a name="return-value"></a>Dönüş Değeri

Kaynak `ISchedulerProxy` Yöneticisi'nin zamanlayıcınızla ilişkilendirdiği arabirim. Zamanlayıcınız bu noktadan itibaren Kaynak Yöneticisi ile iletişim kurmak için bu arabirimi kullanmalıdır.

### <a name="remarks"></a>Açıklamalar

Kaynak Yöneticisi ile iletişimi başlatmak için bu yöntemi kullanın. Yöntem, zamanlayıcınızın arabirimini `IScheduler` `ISchedulerProxy` bir arabirimle ilişkilendirer ve size geri sunar. Döndürülen arabirimi, zamanlayıcınız tarafından kullanılmak üzere yürütme kaynaklarını istemek veya Kaynak Yöneticisi'ne iş parçacığı abone olmak için kullanabilirsiniz. Kaynak Yöneticisi, zamanlayıcının çalışması yürütmek için ne tür iş parçacıkları gerekeceğini belirlemek için [IScheduler](ischeduler-structure.md#getpolicy) tarafından döndürülen zamanlama ilkesindeki ilke öğelerini kullanır. İlke `SchedulerKind` anahtarınız değerine `UmsThreadDefault` sahipse ve değer ilkenin `UmsThreadDefault`değeri `IScheduler` olarak geri okunuyorsa, yönteme geçirilen arabirim bir `IUMSScheduler` arabirim olmalıdır.

Yöntem, parametre `invalid_argument` `pScheduler` değerine `NULL` sahipse veya parametre `version` iletişim arabirimi için geçerli bir sürüm değilse bir özel durum oluşturur.

## <a name="iresourcemanagerrelease-method"></a><a name="release"></a>IResourceManager::Sürüm Yöntemi

Kaynak Yöneticisi örneğinde başvuru sayısını verir. Kaynak Yöneticisi, başvuru sayısı `0`.

```cpp
virtual unsigned int Release() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Ortaya çıkan başvuru sayısı.

## <a name="see-also"></a>Ayrıca bkz.

[concurrency Ad Alanı](concurrency-namespace.md)<br/>
[ISchedulerProxy Yapısı](ischedulerproxy-structure.md)<br/>
[IScheduler Yapısı](ischeduler-structure.md)
