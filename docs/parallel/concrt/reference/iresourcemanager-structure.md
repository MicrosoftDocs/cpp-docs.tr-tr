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
ms.openlocfilehash: 7afb37fb35040975d6e9471a1d12465e5163fafc
ms.sourcegitcommit: 309dc532f13242854b47759cef846de59bb807f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/28/2019
ms.locfileid: "58565210"
---
# <a name="iresourcemanager-structure"></a>IResourceManager Yapısı

Eşzamanlılık Çalışma zamanı kaynak yöneticisi için arabirim. Bu, zamanlayıcılar Resource Manager ile iletişim kurmak arabirimidir.

## <a name="syntax"></a>Sözdizimi

```
struct IResourceManager;
```

## <a name="members"></a>Üyeler

### <a name="public-enumerations"></a>Ortak numaralandırmalar

|Ad|Açıklama|
|----------|-----------------|
|[Iresourcemanager::osversion](#osversion)|İşletim sistemi sürümünü temsil eden numaralandırılmış tür.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Iresourcemanager::createnodetopology](#createnodetopology)|Yalnızca hata ayıklama içinde mevcut çalışma zamanı oluşturur, bu yöntem kaynak gerçek donanım yapılandırması ile eşleşen gerek kalmadan donanım topolojileri değişen şirket Yöneticisi'nin test kolaylaştırmak için tasarlanmış bir sınama kancası. Herhangi bir işlem yapmadan ile perakende derlemeleri çalışma zamanı bu yöntemi döndürür.|
|[Iresourcemanager::getavailablenodecount](#getavailablenodecount)|Kaynak Yöneticisi için kullanılabilir düğüm sayısını döndürür.|
|[Iresourcemanager::getfirstnode](#getfirstnode)|Kaynak Yöneticisi tarafından tanımlandığı gibi ilk düğümü numaralandırma sırada döndürür.|
|[Iresourcemanager::Reference](#reference)|Resource Manager örneğindeki başvuru sayısını artırır.|
|[Iresourcemanager::registerscheduler](#registerscheduler)|Bir Zamanlayıcı'yı Resource Manager ile kaydeder. Zamanlayıcı kaydedildikten sonra bunu kullanarak Resource Manager ile iletişim kurmanız gerekir `ISchedulerProxy` döndürülen arabirimi.|
|[Iresourcemanager::Release](#release)|Resource Manager örneğinde başvuru sayısını azaltır. Resource Manager, başvuru sayısı görünümüne döndüğünde edildiğinde `0`.|

## <a name="remarks"></a>Açıklamalar

Kullanım [CreateResourceManager](concurrency-namespace-functions.md) işlevini tekil Resource Manager örneği için bir arabirim alabilirsiniz. Yöntemi Resource Manager üzerindeki bir başvuru sayısını artırır ve çağırması gereken [Iresourcemanager::Release](#release) Resource Manager ile işiniz bittiğinde başvuru serbest bırakmak için yöntemi. Genellikle, oluşturduğunuz her bir zamanlayıcı oluşturma sırasında bu yöntemini çağırmak ve bunu kapandıktan sonra Resource Manager'a başvuru bırakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IResourceManager`

## <a name="requirements"></a>Gereksinimler

**Başlık:** concrtrm.h

**Namespace:** eşzamanlılık

##  <a name="createnodetopology"></a>  Iresourcemanager::createnodetopology yöntemi

Yalnızca hata ayıklama içinde mevcut çalışma zamanı oluşturur, bu yöntem kaynak gerçek donanım yapılandırması ile eşleşen gerek kalmadan donanım topolojileri değişen şirket Yöneticisi'nin test kolaylaştırmak için tasarlanmış bir sınama kancası. Herhangi bir işlem yapmadan ile perakende derlemeleri çalışma zamanı bu yöntemi döndürür.

```
virtual void CreateNodeTopology(
    unsigned int nodeCount,
    _In_reads_(nodeCount) unsigned int* pCoreCount,
    _In_reads_opt_(nodeCount) unsigned int** pNodeDistance,
    _In_reads_(nodeCount) unsigned int* pProcessorGroups) = 0;
```

### <a name="parameters"></a>Parametreler

*NodeCount*<br/>
Benzetimli işlemci düğüm sayısı.

*pCoreCount*<br/>
Her bir düğümünde çekirdek sayısını belirten bir dizi.

*pNodeDistance*<br/>
Her iki düğüm arasındaki düğüm uzaklık belirterek bir matris. Bu parametre değerini alabilir `NULL`.

*pProcessorGroups*<br/>
İşlemci grubu belirtir bir dizi her düğüme ait.

### <a name="remarks"></a>Açıklamalar

[invalid_argument](../../../standard-library/invalid-argument-class.md) oluşturulur parametresi `nodeCount` değerine sahip `0` , geçirilen veya parametre `pCoreCount` değerine sahip `NULL`.

[invalid_operation](invalid-operation-class.md) işlemdeki diğer zamanlayıcılar mevcut olsa da bu yöntemi çağrılırsa oluşturulur.

##  <a name="getavailablenodecount"></a>  Iresourcemanager::getavailablenodecount metodu

Kaynak Yöneticisi için kullanılabilir düğüm sayısını döndürür.

```
virtual unsigned int GetAvailableNodeCount() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Kaynak Yöneticisi için kullanılabilir düğüm sayısı.

##  <a name="getfirstnode"></a>  Iresourcemanager::getfirstnode metodu

Kaynak Yöneticisi tarafından tanımlandığı gibi ilk düğümü numaralandırma sırada döndürür.

```
virtual ITopologyNode* GetFirstNode() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Kaynak Yöneticisi tarafından tanımlanan numaralandırma sırasında ilk düğümü.

##  <a name="osversion"></a>  Iresourcemanager::osversion numaralandırması

İşletim sistemi sürümünü temsil eden numaralandırılmış tür.

```
enum OSVersion;
```

##  <a name="reference"></a>  Iresourcemanager::Reference yöntemi

Resource Manager örneğindeki başvuru sayısını artırır.

```
virtual unsigned int Reference() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Sonuçta elde edilen başvuru sayısı.

##  <a name="registerscheduler"></a>  Iresourcemanager::registerscheduler yöntemi

Bir Zamanlayıcı'yı Resource Manager ile kaydeder. Zamanlayıcı kaydedildikten sonra bunu kullanarak Resource Manager ile iletişim kurmanız gerekir `ISchedulerProxy` döndürülen arabirimi.

```
virtual ISchedulerProxy *RegisterScheduler(
    _Inout_ IScheduler* pScheduler,
    unsigned int version) = 0;
```

### <a name="parameters"></a>Parametreler

*pScheduler*<br/>
Bir `IScheduler` kaydedilecek Zamanlayıcı arabirimi.

*version*<br/>
Resource Manager ile iletişim kurmak için Zamanlayıcı iletişim arabirimi sürümü kullanıyor. Bir sürümü kullanılarak Resource Manager, erişimi için eski özellikleri elde zamanlayıcılar verirken yönelik iletişim arabirimi gelişmesi sağlar. Visual Studio 2010'da mevcut bir kaynak yöneticisi özellikleri kullanmak isteyen zamanlayıcılar sürümü kullanması gereken `CONCRT_RM_VERSION_1`.

### <a name="return-value"></a>Dönüş Değeri

`ISchedulerProxy` Kaynak Yöneticisi scheduler ile ilişkili arabirimi. Scheduler, üzerinde bu noktadan itibaren Resource Manager ile iletişim kurmak için bu arabirimi kullanmanız gerekir.

### <a name="remarks"></a>Açıklamalar

Resource Manager ile iletişim başlatmak için bu yöntemi kullanın. Yöntem ilişkilendirir `IScheduler` ile scheduler arabirimdeki bir `ISchedulerProxy` arabirimi ve size geri uygulamalı. Döndürülen arabirim, Zamanlayıcı tarafından kullanılmak üzere yürütme kaynakları isteği ya da Resource Manager ile iş parçacığı abone olmak için kullanabilirsiniz. Kaynak Yöneticisi tarafından döndürülen Zamanlayıcı ilkesini ilke öğelerden kullanacağı [Ischeduler::getpolicy](ischeduler-structure.md#getpolicy) yöntemi Zamanlayıcı iş parçacıklarının ne tür belirlemek için iş yürütme gerekecektir. Varsa, `SchedulerKind` ilke anahtarı değerine sahip `UmsThreadDefault` ve ilke değeri olarak dışında geri değer okunur `UmsThreadDefault`, `IScheduler` yönteme arabirimi olmalıdır bir `IUMSScheduler` arabirimi.

Çağırılıyorsa yöntem bir `invalid_argument` özel durum, parametre `pScheduler` değerine sahip `NULL` veya parametre `version` iletişim arabirimi için geçerli bir sürüm değil.

##  <a name="release"></a>  Iresourcemanager::Release yöntemi

Resource Manager örneğinde başvuru sayısını azaltır. Resource Manager, başvuru sayısı görünümüne döndüğünde edildiğinde `0`.

```
virtual unsigned int Release() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Sonuçta elde edilen başvuru sayısı.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[ISchedulerProxy Yapısı](ischedulerproxy-structure.md)<br/>
[IScheduler Yapısı](ischeduler-structure.md)
