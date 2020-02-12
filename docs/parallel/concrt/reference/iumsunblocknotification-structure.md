---
title: IUMSUnblockNotification Yapısı
ms.date: 11/04/2016
f1_keywords:
- IUMSUnblockNotification
- CONCRTRM/concurrency::IUMSUnblockNotification
- CONCRTRM/concurrency::IUMSUnblockNotification::IUMSUnblockNotification::GetContext
- CONCRTRM/concurrency::IUMSUnblockNotification::IUMSUnblockNotification::GetNextUnblockNotification
helpviewer_keywords:
- IUMSUnblockNotification structure
ms.assetid: eaca9529-c1cc-472b-8ec6-722a1ff0fa2a
ms.openlocfilehash: d4fd95b1f11ed6edac26cb03e41e8b650acfafa3
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77139978"
---
# <a name="iumsunblocknotification-structure"></a>IUMSUnblockNotification Yapısı

, Bir iş parçacığı proxy 'sinin, Scheduler 'ın belirlenen zamanlama bağlamına geri dönme ve tetiklediği Kaynak Yöneticisi bir bildirimi temsil eder ve zamanlanmaya hazırlanın. Bu arabirim, iş parçacığı proxy 'sinin ilişkili yürütme bağlamı `GetContext` yönteminden döndürülen bir kez yeniden zamanlanırsa geçersizdir.

## <a name="syntax"></a>Sözdizimi

```cpp
struct IUMSUnblockNotification;
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[IUMSUnblockNotification:: GetContext](#getcontext)|Engeli kaldırılmış olan iş parçacığı proxy 'si ile ilişkili yürütme bağlamı için `IExecutionContext` arabirimini döndürür. Bu yöntem geri döndüğünde ve temel alınan yürütme bağlamı `IThreadProxy::SwitchTo` yöntemine yapılan bir çağrı aracılığıyla yeniden zamanlanırsa, bu arabirim artık geçerli değildir.|
|[IUMSUnblockNotification:: GetNextUnblockNotification](#getnextunblocknotification)|`IUMSCompletionList::GetUnblockNotifications`yönteminden döndürülen zincirde bir sonraki `IUMSUnblockNotification` arabirimini döndürür.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IUMSUnblockNotification`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrtrm. h

**Ad alanı:** eşzamanlılık

## <a name="getcontext"></a>IUMSUnblockNotification:: GetContext yöntemi

Engeli kaldırılmış olan iş parçacığı proxy 'si ile ilişkili yürütme bağlamı için `IExecutionContext` arabirimini döndürür. Bu yöntem geri döndüğünde ve temel alınan yürütme bağlamı `IThreadProxy::SwitchTo` yöntemine yapılan bir çağrı aracılığıyla yeniden zamanlanırsa, bu arabirim artık geçerli değildir.

```cpp
virtual IExecutionContext* GetContext() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Engeli kaldırılmış olan bir iş parçacığı proxy 'sine yürütme bağlamı için `IExecutionContext` arabirimi.

## <a name="getnextunblocknotification"></a>IUMSUnblockNotification:: GetNextUnblockNotification yöntemi

`IUMSCompletionList::GetUnblockNotifications`yönteminden döndürülen zincirde bir sonraki `IUMSUnblockNotification` arabirimini döndürür.

```cpp
virtual IUMSUnblockNotification* GetNextUnblockNotification() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

`IUMSCompletionList::GetUnblockNotifications`yönteminden döndürülen zincirdeki sonraki `IUMSUnblockNotification` arabirimi.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[IUMSScheduler Yapısı](iumsscheduler-structure.md)<br/>
[IUMSCompletionList Yapısı](iumscompletionlist-structure.md)
