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
ms.openlocfilehash: 7ce5b07f5eb4272db1b00b7f0105b790ddbb28fe
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142980"
---
# <a name="iresourcemanager-structure"></a>IResourceManager Yapısı

Eşzamanlılık Çalışma Zamanı Kaynak Yöneticisi arabirimi. Bu, zamanlayıcılar ile iletişim kuran arabirimdir Kaynak Yöneticisi.

## <a name="syntax"></a>Sözdizimi

```cpp
struct IResourceManager;
```

## <a name="members"></a>Üyeler

### <a name="public-enumerations"></a>Ortak numaralandırmalar

|Ad|Açıklama|
|----------|-----------------|
|[IResourceManager:: OSVersion](#osversion)|İşletim sistemi sürümünü temsil eden numaralandırılmış tür.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[IResourceManager:: CreateNodeTopology](#createnodetopology)|Yalnızca çalışma zamanının hata ayıklama yapılarında bulunur, bu yöntem, yapılandırma ile eşleşen gerçek donanıma gerek kalmadan, değişen donanım topolojilerinde Kaynak Yöneticisi test etmeyi kolaylaştırmak için tasarlanan bir test kancasına sahiptir. Çalışma zamanının perakende Derlemeleriyle, bu yöntem herhangi bir eylem yapılmadan döndürülür.|
|[IResourceManager:: GetAvailableNodeCount](#getavailablenodecount)|Kaynak Yöneticisi kullanılabilen düğüm sayısını döndürür.|
|[IResourceManager:: GetFirstNode](#getfirstnode)|Kaynak Yöneticisi tarafından tanımlanan numaralandırma sırasındaki ilk düğümü döndürür.|
|[IResourceManager:: Reference](#reference)|Kaynak Yöneticisi örneğindeki başvuru sayısını artırır.|
|[IResourceManager:: RegisterScheduler](#registerscheduler)|Kaynak Yöneticisi bir Zamanlayıcı kaydeder. Zamanlayıcı kaydolduktan sonra, döndürülen `ISchedulerProxy` arabirimini kullanarak Kaynak Yöneticisi ile iletişim kurması gerekir.|
|[IResourceManager:: Release](#release)|Kaynak Yöneticisi örneğindeki başvuru sayısını azaltır. Başvuru sayısı `0`gittiğinde Kaynak Yöneticisi yok edilir.|

## <a name="remarks"></a>Açıklamalar

Singleton Kaynak Yöneticisi örneğine bir arabirim elde etmek için [CreateResourceManager](concurrency-namespace-functions.md) işlevini kullanın. Yöntemi Kaynak Yöneticisi bir başvuru sayısını artırır ve Kaynak Yöneticisi işiniz bittiğinde başvuruyu serbest bırakmak için [IResourceManager:: Release](#release) metodunu çağırmanız gerekir. Genellikle, oluşturduğunuz her Zamanlayıcı oluşturma sırasında bu yöntemi çağırır ve kapatıldıktan sonra Kaynak Yöneticisi başvurusunu serbest bırakacaktır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IResourceManager`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrtrm. h

**Ad alanı:** eşzamanlılık

## <a name="createnodetopology"></a>IResourceManager:: CreateNodeTopology yöntemi

Yalnızca çalışma zamanının hata ayıklama yapılarında bulunur, bu yöntem, yapılandırma ile eşleşen gerçek donanıma gerek kalmadan, değişen donanım topolojilerinde Kaynak Yöneticisi test etmeyi kolaylaştırmak için tasarlanan bir test kancasına sahiptir. Çalışma zamanının perakende Derlemeleriyle, bu yöntem herhangi bir eylem yapılmadan döndürülür.

```cpp
virtual void CreateNodeTopology(
    unsigned int nodeCount,
    _In_reads_(nodeCount) unsigned int* pCoreCount,
    _In_reads_opt_(nodeCount) unsigned int** pNodeDistance,
    _In_reads_(nodeCount) unsigned int* pProcessorGroups) = 0;
```

### <a name="parameters"></a>Parametreler

*nodeCount*<br/>
Benzetimli işlemci düğümlerinin sayısı.

*pCoreCount*<br/>
Her düğümdeki çekirdek sayısını belirten bir dizi.

*pNodeDistance*<br/>
İki düğüm arasındaki düğüm uzaklığını belirten bir matris. Bu parametrenin değeri `NULL`olabilir.

*pProcessorGroups*<br/>
Her düğümün ait olduğu işlemci grubunu belirten bir dizi.

### <a name="remarks"></a>Açıklamalar

[invalid_argument](../../../standard-library/invalid-argument-class.md) , `nodeCount` parametresinin `0` değeri varsa veya `pCoreCount` parametresinin değeri `NULL`olduğunda oluşturulur.

[invalid_operation](invalid-operation-class.md) , bu yöntem işlem içinde diğer zamanlayıcılar olduğunda çağrılırsa oluşturulur.

## <a name="getavailablenodecount"></a>IResourceManager:: GetAvailableNodeCount yöntemi

Kaynak Yöneticisi kullanılabilen düğüm sayısını döndürür.

```cpp
virtual unsigned int GetAvailableNodeCount() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Kaynak Yöneticisi kullanılabilen düğüm sayısı.

## <a name="getfirstnode"></a>IResourceManager:: GetFirstNode yöntemi

Kaynak Yöneticisi tarafından tanımlanan numaralandırma sırasındaki ilk düğümü döndürür.

```cpp
virtual ITopologyNode* GetFirstNode() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Kaynak Yöneticisi tarafından tanımlanan numaralandırma sırasındaki ilk düğüm.

## <a name="osversion"></a>IResourceManager:: OSVersion numaralandırması

İşletim sistemi sürümünü temsil eden numaralandırılmış tür.

```cpp
enum OSVersion;
```

## <a name="reference"></a>IResourceManager:: Reference yöntemi

Kaynak Yöneticisi örneğindeki başvuru sayısını artırır.

```cpp
virtual unsigned int Reference() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Elde edilen başvuru sayısı.

## <a name="registerscheduler"></a>IResourceManager:: RegisterScheduler Yöntemi

Kaynak Yöneticisi bir Zamanlayıcı kaydeder. Zamanlayıcı kaydolduktan sonra, döndürülen `ISchedulerProxy` arabirimini kullanarak Kaynak Yöneticisi ile iletişim kurması gerekir.

```cpp
virtual ISchedulerProxy *RegisterScheduler(
    _Inout_ IScheduler* pScheduler,
    unsigned int version) = 0;
```

### <a name="parameters"></a>Parametreler

*pScheduler*<br/>
Kaydedilecek Zamanlayıcı için `IScheduler` arabirimi.

*version*<br/>
Scheduler 'ın Kaynak Yöneticisi iletişim kurmak için kullandığı iletişim arabirimi sürümü. Bir sürümü kullanmak Kaynak Yöneticisi, zamanlayıcılar 'in daha eski özelliklere erişim almasına izin verirken iletişim arabirimini gelişmesine izin verir. Visual Studio 2010 ' de bulunan Kaynak Yöneticisi özelliklerini kullanmak isteyen zamanlayıcılar sürüm `CONCRT_RM_VERSION_1`kullanmalıdır.

### <a name="return-value"></a>Dönüş Değeri

Kaynak Yöneticisi Scheduler ile ilişkilendirilen `ISchedulerProxy` arabirimi. Scheduler bu noktadan itibaren Kaynak Yöneticisi ile iletişim kurmak için bu arabirimi kullanmalıdır.

### <a name="remarks"></a>Açıklamalar

Kaynak Yöneticisi iletişim başlatmak için bu yöntemi kullanın. Yöntemi, Scheduler için `IScheduler` arabirimini bir `ISchedulerProxy` arabirimiyle ilişkilendirir ve size geri gönderir. Zamanlayıcı tarafından kullanılmak üzere yürütme kaynakları istemek veya Kaynak Yöneticisi iş parçacıklarını abone olmak için döndürülen arabirimi kullanabilirsiniz. Kaynak Yöneticisi, Scheduler 'ın işi yürütmesi gereken iş parçacığı türlerini belirlemek için [IComparer:: GetPolicy](ischeduler-structure.md#getpolicy) yöntemi tarafından döndürülen Zamanlayıcı ilkesindeki ilke öğelerini kullanacaktır. `SchedulerKind` ilke anahtarınız `UmsThreadDefault` değeri varsa ve değer ilke `UmsThreadDefault`değeri olarak geri okunmışsa, yönteme geçirilen `IScheduler` arabirimi bir `IUMSScheduler` arabirimi olmalıdır.

Parametre `pScheduler` `NULL` değere sahipse veya `version` parametresi iletişim arabirimi için geçerli bir sürüm değilse, yöntemi `invalid_argument` bir özel durum oluşturur.

## <a name="release"></a>IResourceManager:: Release yöntemi

Kaynak Yöneticisi örneğindeki başvuru sayısını azaltır. Başvuru sayısı `0`gittiğinde Kaynak Yöneticisi yok edilir.

```cpp
virtual unsigned int Release() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Elde edilen başvuru sayısı.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[ISchedulerProxy Yapısı](ischedulerproxy-structure.md)<br/>
[IScheduler Yapısı](ischeduler-structure.md)
