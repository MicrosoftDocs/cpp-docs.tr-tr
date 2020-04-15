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
ms.openlocfilehash: 0b88ddd4184e982a5e07c536efc301eaa16f4a41
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368068"
---
# <a name="iumsunblocknotification-structure"></a>IUMSUnblockNotification Yapısı

Kaynak Yöneticisi'nden, zamanlayıcının atanmış zamanlama bağlamına dönüşü engelleyen ve tetikleyen bir iş parçacığı proxy'sinin engellendiğini ve zamanlanmaya hazır olduğunu bildiren bir bildirimi temsil eder. İş parçacığı proxy'nin ilişkili yürütme bağlamı `GetContext` yöntemden döndürülen yeniden zamanlandıktan sonra bu arabirim geçersiz dir.

## <a name="syntax"></a>Sözdizimi

```cpp
struct IUMSUnblockNotification;
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[IUMSUnblockBildirim::GetContext](#getcontext)|Engeli `IExecutionContext` kaldıran iş parçacığı proxy'si ile ilişkili yürütme bağlamı için arabirimi döndürür. Bu yöntem döndürülür ve altta yatan yürütme bağlamı `IThreadProxy::SwitchTo` yönteme bir çağrı yoluyla yeniden zamanlandıktan sonra, bu arabirim artık geçerli değildir.|
|[IUMSUnblockBildirim::GetNextUnblockBildirimi](#getnextunblocknotification)|Yöntemden `IUMSCompletionList::GetUnblockNotifications` `IUMSUnblockNotification` döndürülen zincirdeki bir sonraki arabirimi döndürür.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IUMSUnblockNotification`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrtrm.h

**Ad alanı:** eşzamanlılık

## <a name="iumsunblocknotificationgetcontext-method"></a><a name="getcontext"></a>IUMSUnblockBildirim::GetContext Yöntemi

Engeli `IExecutionContext` kaldıran iş parçacığı proxy'si ile ilişkili yürütme bağlamı için arabirimi döndürür. Bu yöntem döndürülür ve altta yatan yürütme bağlamı `IThreadProxy::SwitchTo` yönteme bir çağrı yoluyla yeniden zamanlandıktan sonra, bu arabirim artık geçerli değildir.

```cpp
virtual IExecutionContext* GetContext() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Engeli kaldıran bir iş parçacığı proxy'sine yürütme bağlamı için bir `IExecutionContext` arabirim.

## <a name="iumsunblocknotificationgetnextunblocknotification-method"></a><a name="getnextunblocknotification"></a>IUMSUnblockBildirim::GetNextUnblockBildirim Yöntemi

Yöntemden `IUMSCompletionList::GetUnblockNotifications` `IUMSUnblockNotification` döndürülen zincirdeki bir sonraki arabirimi döndürür.

```cpp
virtual IUMSUnblockNotification* GetNextUnblockNotification() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Zincirdeki `IUMSUnblockNotification` bir sonraki arabirim `IUMSCompletionList::GetUnblockNotifications`yöntemden döndürülür.

## <a name="see-also"></a>Ayrıca bkz.

[concurrency Ad Alanı](concurrency-namespace.md)<br/>
[IUMSScheduler Yapısı](iumsscheduler-structure.md)<br/>
[IUMSCompletionList Yapısı](iumscompletionlist-structure.md)
