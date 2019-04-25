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
ms.openlocfilehash: bdf083e2ad418269e49e53dc164f2a60f693d5d6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62180225"
---
# <a name="iumsunblocknotification-structure"></a>IUMSUnblockNotification Yapısı

Bir bildirim kaynak engellenir ve zamanlama bağlam belirlenen Zamanlayıcının dön tetiklenen iş parçacığı proxy'sini engeli kaldırılmış ve zamanlanması hazır Yöneticisi'nden temsil eder. Sağlayıcıdan döndürülen iş parçacığı proxy'sinin ilişkili yürütme bağlamı, sonra bu arabirim geçersiz `GetContext` yöntemi, işlemi yeniden zamanlanacak.

## <a name="syntax"></a>Sözdizimi

```
struct IUMSUnblockNotification;
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Iumsunblocknotification::getcontext](#getcontext)|Döndürür `IExecutionContext` hangi engeli kaldırılmış iş parçacığı proxy ile ilişkili yürütme bağlamı için arabirim. Bu yöntem döndürür ve temel alınan yürütme bağlamı için bir çağrı aracılığıyla yeniden sonra `IThreadProxy::SwitchTo` yöntemi, bu arabirim artık geçerli değil.|
|[Iumsunblocknotification::getnextunblocknotification](#getnextunblocknotification)|Sonraki döndürür `IUMSUnblockNotification` arabirimi yönteminden döndürülen zincirindeki `IUMSCompletionList::GetUnblockNotifications`.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IUMSUnblockNotification`

## <a name="requirements"></a>Gereksinimler

**Başlık:** concrtrm.h

**Namespace:** eşzamanlılık

##  <a name="getcontext"></a>  Iumsunblocknotification::getcontext metodu

Döndürür `IExecutionContext` hangi engeli kaldırılmış iş parçacığı proxy ile ilişkili yürütme bağlamı için arabirim. Bu yöntem döndürür ve temel alınan yürütme bağlamı için bir çağrı aracılığıyla yeniden sonra `IThreadProxy::SwitchTo` yöntemi, bu arabirim artık geçerli değil.

```
virtual IExecutionContext* GetContext() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Bir `IExecutionContext` engeli kaldırılmış bir iş parçacığı proxy için yürütme bağlamı için arabirim.

##  <a name="getnextunblocknotification"></a>  Iumsunblocknotification::getnextunblocknotification metodu

Sonraki döndürür `IUMSUnblockNotification` arabirimi yönteminden döndürülen zincirindeki `IUMSCompletionList::GetUnblockNotifications`.

```
virtual IUMSUnblockNotification* GetNextUnblockNotification() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Sonraki `IUMSUnblockNotification` arabirimi yönteminden döndürülen zincirindeki `IUMSCompletionList::GetUnblockNotifications`.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[IUMSScheduler Yapısı](iumsscheduler-structure.md)<br/>
[IUMSCompletionList Yapısı](iumscompletionlist-structure.md)
