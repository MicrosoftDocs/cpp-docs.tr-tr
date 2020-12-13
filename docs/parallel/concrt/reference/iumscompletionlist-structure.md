---
description: 'Daha fazla bilgi edinin: IUMSCompletionList Yapısı'
title: IUMSCompletionList Yapısı
ms.date: 11/04/2016
f1_keywords:
- IUMSCompletionList
- CONCRTRM/concurrency::IUMSCompletionList
- CONCRTRM/concurrency::IUMSCompletionList::IUMSCompletionList::GetUnblockNotifications
helpviewer_keywords:
- IUMSCompletionList structure
ms.assetid: 81b5250e-3065-492c-b20d-2cdabf12271a
ms.openlocfilehash: b54766e8b1c6f2e7c0afbb5e4e9a8efc0c455b4d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334348"
---
# <a name="iumscompletionlist-structure"></a>IUMSCompletionList Yapısı

UMS tamamlama listesini temsil eder. Bir UMS iş parçacığı engellediğinde, başlangıçtaki iş parçacığı engellenirken temeldeki sanal işlemci kökünde zamanlanmak üzere bir karar vermek üzere Scheduler 'ın belirlenen zamanlama bağlamı gönderilir. Orijinal iş parçacığı kaldırılıyorsa, işletim sistemi bu arabirim aracılığıyla erişilebilen tamamlanma listesine sıraya alır. Zamanlayıcı, belirlenen zamanlama bağlamındaki veya iş için arama yaptığı başka bir yerde tamamlama listesini sorgulayabilir.

## <a name="syntax"></a>Syntax

```cpp
struct IUMSCompletionList;
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[IUMSCompletionList:: GetUnblockNotifications](#getunblocknotifications)|`IUMSUnblockNotification`Bu yöntemin en son çağrılmasından bu yana ilişkili iş parçacığı ara sunucuları engeli kaldırılmış olan yürütme bağlamlarını temsil eden bir arabirim zinciri alır.|

## <a name="remarks"></a>Açıklamalar

Bir zamanlayıcı, tamamlanma listesinden öğeleri yeniden ayıklamanız için bu arabirimden kullandıktan sonra hangi eylemlerin gerçekleştirildiği konusunda dikkatli bir şekilde dikkat etmeniz gerekir. Öğeler Scheduler 'ın çalıştırılabilir içerik listesine yerleştirilmelidir ve genellikle mümkün olan en kısa sürede erişilebilir olmalıdır. Sıradan çıkarılan öğelerden birinin rastgele bir kilidin sahipliği verilmesinden tamamen mümkün değildir. Zamanlayıcı, öğeleri sıradan çıkarma ve bu öğelerin genellikle Zamanlayıcı içinden erişilebilen bir liste üzerinde yerleşimi arasında engelleyebilen rastgele bir işlev çağrısı yapabilir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IUMSCompletionList`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrtrm. h

**Ad alanı:** eşzamanlılık

## <a name="iumscompletionlistgetunblocknotifications-method"></a><a name="getunblocknotifications"></a> IUMSCompletionList:: GetUnblockNotifications yöntemi

`IUMSUnblockNotification`Bu yöntemin en son çağrılmasından bu yana ilişkili iş parçacığı ara sunucuları engeli kaldırılmış olan yürütme bağlamlarını temsil eden bir arabirim zinciri alır.

```cpp
virtual IUMSUnblockNotification *GetUnblockNotifications() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

`IUMSUnblockNotification`Arabirim zinciri.

### <a name="remarks"></a>Açıklamalar

Yürütme bağlamları yeniden zamanlandıktan sonra döndürülen bildirimler geçersizdir.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)<br/>
[IUMSScheduler Yapısı](iumsscheduler-structure.md)<br/>
[IUMSUnblockNotification Yapısı](iumsunblocknotification-structure.md)
