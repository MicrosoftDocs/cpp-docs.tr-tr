---
description: 'Daha fazla bilgi edinin: IUMSUnblockNotification yapısı'
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
ms.openlocfilehash: bec40ee1e7326ad37e205c3035f965cb3f0ec8d4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334312"
---
# <a name="iumsunblocknotification-structure"></a>IUMSUnblockNotification Yapısı

, Bir iş parçacığı proxy 'sinin, Scheduler 'ın belirlenen zamanlama bağlamına geri dönme ve tetiklediği Kaynak Yöneticisi bir bildirimi temsil eder ve zamanlanmaya hazırlanın. Bu arabirim, iş parçacığı proxy 'sinin ilişkili yürütme bağlamı yönteminden döndürülen bir kez yeniden `GetContext` zamanlanırsa geçersizdir.

## <a name="syntax"></a>Syntax

```cpp
struct IUMSUnblockNotification;
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[IUMSUnblockNotification:: GetContext](#getcontext)|`IExecutionContext`Engeli kaldırılmış olan iş parçacığı proxy 'si ile ilişkili yürütme bağlamı için arabirimi döndürür. Bu yöntem geri döndüğünde ve temel alınan yürütme bağlamı yöntemine yapılan bir çağrı yoluyla yeniden zamanlanmışsa `IThreadProxy::SwitchTo` , bu arabirim artık geçerli değildir.|
|[IUMSUnblockNotification:: GetNextUnblockNotification](#getnextunblocknotification)|`IUMSUnblockNotification`Yönteminden döndürülen zincirdeki bir sonraki arabirimi döndürür `IUMSCompletionList::GetUnblockNotifications` .|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IUMSUnblockNotification`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrtrm. h

**Ad alanı:** eşzamanlılık

## <a name="iumsunblocknotificationgetcontext-method"></a><a name="getcontext"></a> IUMSUnblockNotification:: GetContext yöntemi

`IExecutionContext`Engeli kaldırılmış olan iş parçacığı proxy 'si ile ilişkili yürütme bağlamı için arabirimi döndürür. Bu yöntem geri döndüğünde ve temel alınan yürütme bağlamı yöntemine yapılan bir çağrı yoluyla yeniden zamanlanmışsa `IThreadProxy::SwitchTo` , bu arabirim artık geçerli değildir.

```cpp
virtual IExecutionContext* GetContext() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

`IExecutionContext`Engeli kaldırılmış olan bir iş parçacığı proxy 'sine yürütme bağlamı için arabirim.

## <a name="iumsunblocknotificationgetnextunblocknotification-method"></a><a name="getnextunblocknotification"></a> IUMSUnblockNotification:: GetNextUnblockNotification yöntemi

`IUMSUnblockNotification`Yönteminden döndürülen zincirdeki bir sonraki arabirimi döndürür `IUMSCompletionList::GetUnblockNotifications` .

```cpp
virtual IUMSUnblockNotification* GetNextUnblockNotification() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

`IUMSUnblockNotification`Yöntemden döndürülen zincirdeki sonraki arabirim `IUMSCompletionList::GetUnblockNotifications` .

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)<br/>
[IUMSScheduler Yapısı](iumsscheduler-structure.md)<br/>
[IUMSCompletionList Yapısı](iumscompletionlist-structure.md)
