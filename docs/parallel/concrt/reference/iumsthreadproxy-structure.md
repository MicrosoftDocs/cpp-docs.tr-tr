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
ms.openlocfilehash: f4fb43a4223cad8cc63049d2a0f8345e48b90f17
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77139968"
---
# <a name="iumsthreadproxy-structure"></a>IUMSThreadProxy Yapısı

Yürütmenin iş parçacığı için bir soyutlama. Scheduler 'a Kullanıcı modu zamanlanabilen (UMS) iş parçacıkları verilmesini istiyorsanız Zamanlayıcı İlkesi öğesi `SchedulerKind` değerini `UmsThreadDefault`olarak ayarlayın ve `IUMSScheduler` arabirimini uygulayın. UMS iş parçacıkları yalnızca Windows 7 ve üzeri sürümü olan 64 bitlik işletim sistemlerinde desteklenir.

## <a name="syntax"></a>Sözdizimi

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
|[IUMSThreadProxy:: Getcriticalhandle Regiontype](#getcriticalregiontype)|İş parçacığı proxy 'sinin içinde ne tür kritik bölge olduğunu döndürür. Hyper-kritik bölgeleri kritik bölgelerin bir üst kümesi olduğundan, kod bir kritik bölge ve daha sonra bir Hyper-kritik bölge girdiyseniz `InsideHyperCriticalRegion` döndürülür.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[IThreadProxy](ithreadproxy-structure.md)

`IUMSThreadProxy`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** concrtrm. h

**Ad alanı:** eşzamanlılık

## <a name="entercriticalregion"></a>IUMSThreadProxy:: Enterkritikregion yöntemi

Kritik bir bölge girmek için çağırılır. Kritik bir bölgenin içindeyken Zamanlayıcı, bölge sırasında gerçekleşen zaman uyumsuz engelleyici işlemleri gözlemetmez. Bu, bir UMS iş parçacığı için, Zamanlayıcı sayfa hataları, iş parçacığı getirilmesi, çekirdek zaman uyumsuz yordam çağrıları (APCs) vb. için yeniden girilemeyeceği anlamına gelir.

```cpp
virtual int EnterCriticalRegion() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Kritik bölgenin yeni derinliği. Kritik bölgeler yer alınır.

## <a name="enterhypercriticalregion"></a>IUMSThreadProxy:: Enterhyperkritikregion yöntemi

Hiper öneme sahip bir bölge girmek için çağırılır. Hiper kritik bir bölgenin içindeyken Zamanlayıcı, bölge sırasında gerçekleşen engelleyici işlemleri gözlemleyecektir. Bu, bir UMS iş parçacığı için Zamanlayıcı, blok, sayfa hatası, iş parçacığı getirilmesi, çekirdek zaman uyumsuz yordam çağrıları (APCs) vb.

```cpp
virtual int EnterHyperCriticalRegion() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Hyper-kritik bölgesinin yeni derinliği. Hiper kritik bölgeler yer alınır.

### <a name="remarks"></a>Açıklamalar

Zamanlayıcı çağrı yaptığı Yöntemler ve bu tür bölgelerde ne kadar kilit aldığı hakkında bilgi almalıdır. Bu tür bir bölgede, Scheduler 'ın zamanlama açısından sorumlu olduğu bir kilit üzerindeki kodu engelliyorsa, kilitlenme olabilir.

## <a name="exitcriticalregion"></a>IUMSThreadProxy:: Exitkritikregion yöntemi

Kritik bir bölgeden çıkmak için çağırılır.

```cpp
virtual int ExitCriticalRegion() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Kritik bölgenin yeni derinliği. Kritik bölgeler yer alınır.

## <a name="exithypercriticalregion"></a>IUMSThreadProxy:: Exithyperkritikregion yöntemi

Hiper kritik bir bölgeden çıkmak için çağırılır.

```cpp
virtual int ExitHyperCriticalRegion() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Hyper-kritik bölgesinin yeni derinliği. Hiper kritik bölgeler yer alınır.

## <a name="getcriticalregiontype"></a>IUMSThreadProxy:: Getcriticalhandle Regiontype yöntemi

İş parçacığı proxy 'sinin içinde ne tür kritik bölge olduğunu döndürür. Hyper-kritik bölgeleri kritik bölgelerin bir üst kümesi olduğundan, kod bir kritik bölge ve daha sonra bir Hyper-kritik bölge girdiyseniz `InsideHyperCriticalRegion` döndürülür.

```cpp
virtual CriticalRegionType GetCriticalRegionType() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

İş parçacığı proxy 'sinin içinde olduğu kritik bölge türü.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[IUMSScheduler Yapısı](iumsscheduler-structure.md)
