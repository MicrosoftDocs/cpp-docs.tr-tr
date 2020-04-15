---
title: IUMSCompletionList Yapısı
ms.date: 11/04/2016
f1_keywords:
- IUMSCompletionList
- CONCRTRM/concurrency::IUMSCompletionList
- CONCRTRM/concurrency::IUMSCompletionList::IUMSCompletionList::GetUnblockNotifications
helpviewer_keywords:
- IUMSCompletionList structure
ms.assetid: 81b5250e-3065-492c-b20d-2cdabf12271a
ms.openlocfilehash: c388cc98aedbd35b2d0e00a4653a85a47abcb838
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368117"
---
# <a name="iumscompletionlist-structure"></a>IUMSCompletionList Yapısı

UMS tamamlanma listesini temsil eder. Ums iş parçacığı engellediğinde, özgün iş parçacığı engellenirken temel sanal işlemci kökünde ne zamanlanması na karar vermek için zamanlayıcının atanmış zamanlama bağlamı gönderilir. Özgün iş parçacığı engellediğinde, işletim sistemi bu arabirim üzerinden erişilebilen tamamlanma listesine sıralar. Zamanlayıcı, belirlenen zamanlama bağlamında veya iş aradığı başka bir yerde tamamlanma listesini sorgulayabilir.

## <a name="syntax"></a>Sözdizimi

```cpp
struct IUMSCompletionList;
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[IUMSCompletionList::GetUnblockBildirimler](#getunblocknotifications)|İlişkili iş `IUMSUnblockNotification` parçacığı yakınlıkları bu yöntem çağrıldığından beri engelini kaldıran yürütme bağlamlarını temsil eden bir arabirim zincirini alır.|

## <a name="remarks"></a>Açıklamalar

Bir zamanlayıcı, bu arabirimi kullanarak öğeleri tamamlama listesinden çıkarmak için hangi eylemlerin gerçekleştirildiği konusunda olağanüstü dikkatli olmalıdır. Öğeler zamanlayıcının çalıştırılabilir bağlamlar listesine yerleştirilmeli ve genellikle mümkün olan en kısa sürede erişilebilir olmalıdır. Dequeued öğelerden birine rasgele bir kilit sahipliği verilmiş olması tamamen mümkündür. Zamanlayıcı, öğeleri sıradan kaldırma çağrısı yla bu öğelerin genellikle zamanlayıcı nın içinden erişilebilen bir listedeki yerleşimi arasında engelleyebilecek rasgele işlev çağrıları yapamaz.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IUMSCompletionList`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrtrm.h

**Ad alanı:** eşzamanlılık

## <a name="iumscompletionlistgetunblocknotifications-method"></a><a name="getunblocknotifications"></a>IUMSCompletionList::GetUnblockBildirimler Yöntemi

İlişkili iş `IUMSUnblockNotification` parçacığı yakınlıkları bu yöntem çağrıldığından beri engelini kaldıran yürütme bağlamlarını temsil eden bir arabirim zincirini alır.

```cpp
virtual IUMSUnblockNotification *GetUnblockNotifications() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Arayüzler `IUMSUnblockNotification` zinciri.

### <a name="remarks"></a>Açıklamalar

Yürütme bağlamları yeniden zamanlandıktan sonra döndürülen bildirimler geçersiz olur.

## <a name="see-also"></a>Ayrıca bkz.

[concurrency Ad Alanı](concurrency-namespace.md)<br/>
[IUMSScheduler Yapısı](iumsscheduler-structure.md)<br/>
[IUMSUnblockNotification Yapısı](iumsunblocknotification-structure.md)
