---
description: 'Daha fazla bilgi edinin: IUMSThreadProxy yapısı'
title: IUMSThreadProxy Yapısı
ms.date: 11/04/2016
f1_keywords:
- IUMSThreadProxy
- CONCRTRM/concurrency::IUMSThreadProxy
- CONCRTRM/concurrency::IUMSThreadProxy::IUMSThreadProxy::EnterCriticalRegion
- CONCRTRM/concurrency::IUMSThreadProxy::IUMSThreadProxy::EnterHyperCriticalRegion
- CONCRTRM/concurrency::IUMSThreadProxy::IUMSThreadProxy::ExitCriticalRegion
- CONCRTRM/concurrency::IUMSThreadProxy::IUMSThreadProxy::ExitHyperCriticalRegion
- CONCRTRM/concurrency::IUMSThreadProxy::IUMSThreadProxy::GetCriticalRegionType
helpviewer_keywords:
- IUMSThreadProxy structure
ms.assetid: 61c69b7e-5c37-4048-bcb4-e75c536afd86
ms.openlocfilehash: 02eb999b35143e4fc9e0416e02abb60c3c64768d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334326"
---
# <a name="iumsthreadproxy-structure"></a>IUMSThreadProxy Yapısı

Yürütmenin iş parçacığı için bir soyutlama. Scheduler 'a Kullanıcı modu zamanlanabilen (UMS) iş parçacıkları verilmesini istiyorsanız, Zamanlayıcı İlkesi öğesi için değeri `SchedulerKind` olarak ayarlayın `UmsThreadDefault` ve `IUMSScheduler` arabirimini uygulayın. UMS iş parçacıkları yalnızca Windows 7 ve üzeri sürümü olan 64 bitlik işletim sistemlerinde desteklenir.

## <a name="syntax"></a>Syntax

```cpp
struct IUMSThreadProxy : public IThreadProxy;
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[IUMSThreadProxy:: Entercriticalhandle bölgesi](#entercriticalregion)|Kritik bir bölge girmek için çağırılır. Kritik bir bölgenin içindeyken Zamanlayıcı, bölge sırasında gerçekleşen zaman uyumsuz engelleyici işlemleri gözlemetmez. Bu, bir UMS iş parçacığı için, Zamanlayıcı sayfa hataları, iş parçacığı getirilmesi, çekirdek zaman uyumsuz yordam çağrıları (APCs) vb. için yeniden girilemeyeceği anlamına gelir.|
|[IUMSThreadProxy:: Enterhyperkritikregion](#enterhypercriticalregion)|Hiper öneme sahip bir bölge girmek için çağırılır. Hiper kritik bir bölgenin içindeyken Zamanlayıcı, bölge sırasında gerçekleşen engelleyici işlemleri gözlemleyecektir. Bu, bir UMS iş parçacığı için Zamanlayıcı, blok, sayfa hatası, iş parçacığı getirilmesi, çekirdek zaman uyumsuz yordam çağrıları (APCs) vb.|
|[IUMSThreadProxy:: Exitcriticalhandle bölgesi](#exitcriticalregion)|Kritik bir bölgeden çıkmak için çağırılır.|
|[IUMSThreadProxy:: Exithyperkritikregion](#exithypercriticalregion)|Hiper kritik bir bölgeden çıkmak için çağırılır.|
|[IUMSThreadProxy:: Getcriticalhandle Regiontype](#getcriticalregiontype)|İş parçacığı proxy 'sinin içinde ne tür kritik bölge olduğunu döndürür. Hyper-kritik bölgeleri kritik bölgelerin bir üst kümesi olduğundan, kod bir kritik bölge girdikten sonra bir Hyper-kritik bölgesi `InsideHyperCriticalRegion` döndürülür.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[IThreadProxy](ithreadproxy-structure.md)

`IUMSThreadProxy`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrtrm. h

**Ad alanı:** eşzamanlılık

## <a name="iumsthreadproxyentercriticalregion-method"></a><a name="entercriticalregion"></a> IUMSThreadProxy:: Enterkritikregion yöntemi

Kritik bir bölge girmek için çağırılır. Kritik bir bölgenin içindeyken Zamanlayıcı, bölge sırasında gerçekleşen zaman uyumsuz engelleyici işlemleri gözlemetmez. Bu, bir UMS iş parçacığı için, Zamanlayıcı sayfa hataları, iş parçacığı getirilmesi, çekirdek zaman uyumsuz yordam çağrıları (APCs) vb. için yeniden girilemeyeceği anlamına gelir.

```cpp
virtual int EnterCriticalRegion() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Kritik bölgenin yeni derinliği. Kritik bölgeler yer alınır.

## <a name="iumsthreadproxyenterhypercriticalregion-method"></a><a name="enterhypercriticalregion"></a> IUMSThreadProxy:: Enterhyperkritikregion yöntemi

Hiper öneme sahip bir bölge girmek için çağırılır. Hiper kritik bir bölgenin içindeyken Zamanlayıcı, bölge sırasında gerçekleşen engelleyici işlemleri gözlemleyecektir. Bu, bir UMS iş parçacığı için Zamanlayıcı, blok, sayfa hatası, iş parçacığı getirilmesi, çekirdek zaman uyumsuz yordam çağrıları (APCs) vb.

```cpp
virtual int EnterHyperCriticalRegion() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Hyper-kritik bölgesinin yeni derinliği. Hiper kritik bölgeler yer alınır.

### <a name="remarks"></a>Açıklamalar

Zamanlayıcı çağrı yaptığı Yöntemler ve bu tür bölgelerde ne kadar kilit aldığı hakkında bilgi almalıdır. Bu tür bir bölgede, Scheduler 'ın zamanlama açısından sorumlu olduğu bir kilit üzerindeki kodu engelliyorsa, kilitlenme olabilir.

## <a name="iumsthreadproxyexitcriticalregion-method"></a><a name="exitcriticalregion"></a> IUMSThreadProxy:: Exitkritikregion yöntemi

Kritik bir bölgeden çıkmak için çağırılır.

```cpp
virtual int ExitCriticalRegion() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Kritik bölgenin yeni derinliği. Kritik bölgeler yer alınır.

## <a name="iumsthreadproxyexithypercriticalregion-method"></a><a name="exithypercriticalregion"></a> IUMSThreadProxy:: Exithyperkritikregion yöntemi

Hiper kritik bir bölgeden çıkmak için çağırılır.

```cpp
virtual int ExitHyperCriticalRegion() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Hyper-kritik bölgesinin yeni derinliği. Hiper kritik bölgeler yer alınır.

## <a name="iumsthreadproxygetcriticalregiontype-method"></a><a name="getcriticalregiontype"></a> IUMSThreadProxy:: Getcriticalhandle Regiontype yöntemi

İş parçacığı proxy 'sinin içinde ne tür kritik bölge olduğunu döndürür. Hyper-kritik bölgeleri kritik bölgelerin bir üst kümesi olduğundan, kod bir kritik bölge girdikten sonra bir Hyper-kritik bölgesi `InsideHyperCriticalRegion` döndürülür.

```cpp
virtual CriticalRegionType GetCriticalRegionType() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

İş parçacığı proxy 'sinin içinde olduğu kritik bölge türü.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı](concurrency-namespace.md)<br/>
[IUMSScheduler Yapısı](iumsscheduler-structure.md)
