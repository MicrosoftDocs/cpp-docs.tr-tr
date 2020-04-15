---
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
ms.openlocfilehash: 2e748b1da02394e1f70afd8b92947e1291957c62
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368078"
---
# <a name="iumsthreadproxy-structure"></a>IUMSThreadProxy Yapısı

Yürütme iş parçacığı için bir soyutlama. Zamanlayıcınıza kullanıcı modu zamanlanabilir (UMS) iş parçacıkları verilmesini istiyorsanız, zamanlayıcı ilkesi `SchedulerKind` öğesinin `UmsThreadDefault`değerini ayarlayın ve arabirimi uygulayın. `IUMSScheduler` UMS iş parçacıkları yalnızca Windows 7 ve üzeri sürümlere sahip 64 bit işletim sistemlerinde desteklenir.

## <a name="syntax"></a>Sözdizimi

```cpp
struct IUMSThreadProxy : public IThreadProxy;
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[IUMSThreadProxy::EnterCriticalRegion](#entercriticalregion)|Kritik bir bölgeye girmek için çağrıldı. Kritik bir bölge içindeyken, zamanlayıcı bölge sırasında meydana gelen eşzamanlı engelleme işlemlerini gözlemlemez. Bu, zamanlayıcının sayfa hataları, iş parçacığı süspansiyonları, çekirdek asynchronöz yordam çağrıları (AAP'ler) ve benzeri için bir UMS iş parçacığı için yeniden girilmeyeceğini anlamına gelir.|
|[IUMSThreadProxy::EnterHyperCriticalRegion](#enterhypercriticalregion)|Hiper kritik bölgeye girmek için çağrıldı. Hiper kritik bir bölgenin içindeyken, zamanlayıcı bölge boyunca meydana gelen engelleme işlemlerini gözlemlemez. Bu, zamanlayıcının işlev çağrılarını engellemek, blok oluşturan kilit alma girişimleri, sayfa hataları, iş parçacığı süspansiyonları, çekirdek asynchronous yordam çağrıları (AAP' ler) ve benzeri, bir UMS iş parçacığı için yeniden girilmeyeceğini zedeleme anlamına gelir.|
|[IUMSThreadProxy::ExitCriticalRegion](#exitcriticalregion)|Kritik bir bölgeden çıkmak için çağrıldı.|
|[IUMSThreadProxy::ExitHyperCriticalRegion](#exithypercriticalregion)|Hiper kritik bölgeden çıkmak için çağrıldı.|
|[IUMSThreadProxy::GetCriticalRegionType](#getcriticalregiontype)|İş parçacığı proxy'sinin içinde ne tür kritik bir bölge olduğunu verir. Hiper kritik bölgeler kritik bölgelerin bir üst kümesi olduğundan, kod kritik bir bölgeye girdiyse ve sonra hiper kritik bir bölge `InsideHyperCriticalRegion` döndürülürse.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[IThreadProxy](ithreadproxy-structure.md)

`IUMSThreadProxy`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrtrm.h

**Ad alanı:** eşzamanlılık

## <a name="iumsthreadproxyentercriticalregion-method"></a><a name="entercriticalregion"></a>IUMSThreadProxy::EnterCriticalRegion Yöntemi

Kritik bir bölgeye girmek için çağrıldı. Kritik bir bölge içindeyken, zamanlayıcı bölge sırasında meydana gelen eşzamanlı engelleme işlemlerini gözlemlemez. Bu, zamanlayıcının sayfa hataları, iş parçacığı süspansiyonları, çekirdek asynchronöz yordam çağrıları (AAP'ler) ve benzeri için bir UMS iş parçacığı için yeniden girilmeyeceğini anlamına gelir.

```cpp
virtual int EnterCriticalRegion() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Kritik bölgenin yeni derinliği. Kritik bölgeler yeniden canlandırmadır.

## <a name="iumsthreadproxyenterhypercriticalregion-method"></a><a name="enterhypercriticalregion"></a>IUMSThreadProxy::EnterHyperCriticalRegion Yöntemi

Hiper kritik bölgeye girmek için çağrıldı. Hiper kritik bir bölgenin içindeyken, zamanlayıcı bölge boyunca meydana gelen engelleme işlemlerini gözlemlemez. Bu, zamanlayıcının işlev çağrılarını engellemek, blok oluşturan kilit alma girişimleri, sayfa hataları, iş parçacığı süspansiyonları, çekirdek asynchronous yordam çağrıları (AAP' ler) ve benzeri, bir UMS iş parçacığı için yeniden girilmeyeceğini zedeleme anlamına gelir.

```cpp
virtual int EnterHyperCriticalRegion() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Hiper kritik bölgenin yeni derinliği. Hiper kritik bölgeler yeniden canlandırmadır.

### <a name="remarks"></a>Açıklamalar

Zamanlayıcı, hangi yöntemleri aradığı ve bu bölgelerde hangi kilitleri elde etmesi konusunda olağanüstü dikkatli olmalıdır. Böyle bir bölgedeki kod, zamanlayıcının zamanlamadan sorumlu olduğu bir kilit üzerinde engellerse, kilitlenme oluşabilir.

## <a name="iumsthreadproxyexitcriticalregion-method"></a><a name="exitcriticalregion"></a>IUMSThreadProxy::ExitCriticalRegion Yöntemi

Kritik bir bölgeden çıkmak için çağrıldı.

```cpp
virtual int ExitCriticalRegion() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Kritik bölgenin yeni derinliği. Kritik bölgeler yeniden canlandırmadır.

## <a name="iumsthreadproxyexithypercriticalregion-method"></a><a name="exithypercriticalregion"></a>IUMSThreadProxy::ExitHyperCriticalRegion Yöntemi

Hiper kritik bölgeden çıkmak için çağrıldı.

```cpp
virtual int ExitHyperCriticalRegion() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Hiper kritik bölgenin yeni derinliği. Hiper kritik bölgeler yeniden canlandırmadır.

## <a name="iumsthreadproxygetcriticalregiontype-method"></a><a name="getcriticalregiontype"></a>IUMSThreadProxy::GetCriticalRegionType Yöntemi

İş parçacığı proxy'sinin içinde ne tür kritik bir bölge olduğunu verir. Hiper kritik bölgeler kritik bölgelerin bir üst kümesi olduğundan, kod kritik bir bölgeye girdiyse ve sonra hiper kritik bir bölge `InsideHyperCriticalRegion` döndürülürse.

```cpp
virtual CriticalRegionType GetCriticalRegionType() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

İş parçacığı proxy içinde kritik bölge türü.

## <a name="see-also"></a>Ayrıca bkz.

[concurrency Ad Alanı](concurrency-namespace.md)<br/>
[IUMSScheduler Yapısı](iumsscheduler-structure.md)
