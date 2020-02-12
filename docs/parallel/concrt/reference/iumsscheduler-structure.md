---
title: IUMSScheduler Yapısı
ms.date: 11/04/2016
f1_keywords:
- IUMSScheduler
- CONCRTRM/concurrency::IUMSScheduler
- CONCRTRM/concurrency::IUMSScheduler::IUMSScheduler::SetCompletionList
helpviewer_keywords:
- IUMSScheduler structure
ms.assetid: 3a500225-4e02-4849-bb56-d744865f5870
ms.openlocfilehash: 45df744a9850510006e4bf887c8ed61b000a8e5c
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77139990"
---
# <a name="iumsscheduler-structure"></a>IUMSScheduler Yapısı

Eşzamanlılık Çalışma Zamanı Kaynak Yöneticisi, Kullanıcı modu zamanlanabilen (UMS) iş parçacıklarını ele almak isteyen bir iş Zamanlayıcı soyutlaması için arabirim. Kaynak Yöneticisi, UMS iş parçacığı zamanlayıcılar ile iletişim kurmak için bu arabirimi kullanır. `IUMSScheduler` arabirimi `IScheduler` arabiriminden devralır.

## <a name="syntax"></a>Sözdizimi

```cpp
struct IUMSScheduler : public IScheduler;
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[IUMSScheduler:: SetCompletionList](#setcompletionlist)|UMS iş parçacığı zamanlayıcısına bir `IUMSCompletionList` arabirimi atar.|

## <a name="remarks"></a>Açıklamalar

Kaynak Yöneticisi ile iletişim kuran özel bir Zamanlayıcı uygulamadıysanız ve UMS iş parçacıklarının sıradan Win32 iş parçacıkları yerine Scheduler 'a devredilmesi istiyorsanız `IUMSScheduler` arabiriminin bir uygulamasını sağlamanız gerekir. Ayrıca Zamanlayıcı ilke anahtarı `SchedulerKind` için ilke değerini `UmsThreadDefault`olarak ayarlamanız gerekir. İlke UMS iş parçacığını belirtiyorsa, [IResourceManager:: RegisterScheduler](iresourcemanager-structure.md#registerscheduler) metoduna parametre olarak geçirilen `IScheduler` arabirimi bir `IUMSScheduler` arabirimi olmalıdır.

Kaynak Yöneticisi, yalnızca UMS özelliğine sahip işletim sistemlerinde UMS iş parçacıklarını ele alır. Windows 7 sürümü ve daha yüksek olan 64 bitlik işletim sistemleri, UMS iş parçacıklarını destekler. `SchedulerKind` anahtarı ile `UmsThreadDefault` değerine ayarlanmış bir Zamanlayıcı İlkesi oluşturursanız ve temel alınan platform UMS 'yi desteklemiyorsa, bu ilkedeki `SchedulerKind` anahtarının değeri `ThreadScheduler`olarak değiştirilir. UMS iş parçacıklarını almayı beklemeden önce Bu ilke değerini her zaman okumanız gerekir.

`IUMSScheduler` arabirimi, bir Zamanlayıcı ve Kaynak Yöneticisi arasındaki iki yönlü bir kanalın bir bitişidir. Diğer son, Kaynak Yöneticisi tarafından uygulanan `IResourceManager` ve `ISchedulerProxy` arabirimleri tarafından temsil edilir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[IScheduler](ischeduler-structure.md)

`IUMSScheduler`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrtrm. h

**Ad alanı:** eşzamanlılık

## <a name="setcompletionlist"></a>IUMSScheduler:: SetCompletionList yöntemi

UMS iş parçacığı zamanlayıcısına bir `IUMSCompletionList` arabirimi atar.

```cpp
virtual void SetCompletionList(_Inout_ IUMSCompletionList* pCompletionList) = 0;
```

### <a name="parameters"></a>Parametreler

*pCompletionList*<br/>
Zamanlayıcı için tamamlanma listesi arabirimi. Zamanlayıcı başına tek bir liste vardır.

### <a name="remarks"></a>Açıklamalar

Kaynak Yöneticisi, Zamanlayıcı ilk kaynak ayırmayı istediğinde, bu yöntemi, UMS iş parçacıkları istediğini belirten bir Scheduler 'da çağıracaktır. Zamanlayıcı, UMS iş parçacığı proxy 'lerinin engellemesini nasıl engelleyeceğini öğrenmek için `IUMSCompletionList` arabirimini kullanabilir. Bu arabirime yalnızca, UMS Scheduler 'a atanmış sanal bir işlemci kökünde çalışan bir iş parçacığı proxy 'sinden erişim için geçerlidir.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[PolicyElementKey](concurrency-namespace-enums.md)<br/>
[IScheduler Yapısı](ischeduler-structure.md)<br/>
[IUMSCompletionList Yapısı](iumscompletionlist-structure.md)<br/>
[IResourceManager Yapısı](iresourcemanager-structure.md)
