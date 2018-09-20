---
title: Iumscompletionlist yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- IUMSCompletionList
- CONCRTRM/concurrency::IUMSCompletionList
- CONCRTRM/concurrency::IUMSCompletionList::IUMSCompletionList::GetUnblockNotifications
dev_langs:
- C++
helpviewer_keywords:
- IUMSCompletionList structure
ms.assetid: 81b5250e-3065-492c-b20d-2cdabf12271a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: aabab7a127fdc072b8d3863a53c02e20139afc5a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46433701"
---
# <a name="iumscompletionlist-structure"></a>IUMSCompletionList Yapısı

UMS tamamlanma listesini temsil eder. UMS iş parçacığı blokları, scheduler'ın zamanlama atanan olduğunda bağlamı ne özgün iş parçacığı engellenir sırada temel alınan sanal işlemci kökünde zamanlamak bir karar vermek için gönderilir. Özgün iş parçacığı engellemesinin kaldırıldığı, işletim sistemi, bu arabirimle erişilebilen, tamamlanma listesini sıralar. Zamanlayıcı belirtilen zamanlama bağlamı veya iş için arar herhangi bir yerde tamamlanma listesi sorgulayabilirsiniz.

## <a name="syntax"></a>Sözdizimi

```
struct IUMSCompletionList;
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Iumscompletionlist::getunblocknotifications](#getunblocknotifications)|Zinciri alır `IUMSUnblockNotification` , ilişkili iş parçacığı proxy Engellemesi en son çalıştırılışından itibaren bu yöntem çağrıldığı yürütme bağlamları temsil eden arabirim.|

## <a name="remarks"></a>Açıklamalar

Bir zamanlayıcı hangi eylemleri tamamlanma listesi öğelerinden sıradan çıkarma için bu arabirimi kullanan sonra gerçekleştirilen hakkında çok dikkatli olmanız gerekir. Öğeler, scheduler'ın çalıştırılabilir bağlamları listesinde yerleştirilmelidir ve olabildiğince çabuk genel olarak erişilebilir. Dequeued öğeleri bir rastgele kilidi sahipliğini verildi tamamen mümkündür. Zamanlayıcı öğeleri kuyruktan çağrı ve genel olarak Zamanlayıcı içindeki erişilebilir bir listedeki öğelerin yerleşimini arasında engelleyebilir hiçbir rastgele işlev çağrıları yapabilir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IUMSCompletionList`

## <a name="requirements"></a>Gereksinimler

**Başlık:** concrtrm.h

**Namespace:** eşzamanlılık

##  <a name="getunblocknotifications"></a>  Iumscompletionlist::getunblocknotifications metodu

Zinciri alır `IUMSUnblockNotification` , ilişkili iş parçacığı proxy Engellemesi en son çalıştırılışından itibaren bu yöntem çağrıldığı yürütme bağlamları temsil eden arabirim.

```
virtual IUMSUnblockNotification *GetUnblockNotifications() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Zinciri `IUMSUnblockNotification` arabirimleri.

### <a name="remarks"></a>Açıklamalar

Döndürülen bildirimleri yürütme bağlamları filtrelerden geçersiz olur.

## <a name="see-also"></a>Ayrıca Bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[IUMSScheduler Yapısı](iumsscheduler-structure.md)<br/>
[IUMSUnblockNotification Yapısı](iumsunblocknotification-structure.md)
