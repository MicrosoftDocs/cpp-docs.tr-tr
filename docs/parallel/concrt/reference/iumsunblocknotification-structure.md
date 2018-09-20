---
title: Iumsunblocknotification yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- IUMSUnblockNotification
- CONCRTRM/concurrency::IUMSUnblockNotification
- CONCRTRM/concurrency::IUMSUnblockNotification::IUMSUnblockNotification::GetContext
- CONCRTRM/concurrency::IUMSUnblockNotification::IUMSUnblockNotification::GetNextUnblockNotification
dev_langs:
- C++
helpviewer_keywords:
- IUMSUnblockNotification structure
ms.assetid: eaca9529-c1cc-472b-8ec6-722a1ff0fa2a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 63dcd78af0804a6921d34a35611591f044c2633f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46438034"
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

## <a name="see-also"></a>Ayrıca Bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[IUMSScheduler Yapısı](iumsscheduler-structure.md)<br/>
[IUMSCompletionList Yapısı](iumscompletionlist-structure.md)
