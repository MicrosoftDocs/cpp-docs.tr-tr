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
ms.openlocfilehash: 258f249aa178b73da2080cca888409dc07f63dbb
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57263045"
---
# <a name="iumsthreadproxy-structure"></a>IUMSThreadProxy Yapısı

Bir iş parçacığı için bir soyutlamayı yürütme. Kullanıcı modunda zamanlanabilen (UMS) iş parçacıklarını verilebilmesi için scheduler istiyorsanız Zamanlayıcı ilkesini öğesinin değeri ayarlamak `SchedulerKind` için `UmsThreadDefault`ve uygulama `IUMSScheduler` arabirimi. UMS iş parçacıkları, yalnızca desteklenen 64 bit işletim sistemlerinde, sürümü Windows 7 ve üzeri.

## <a name="syntax"></a>Sözdizimi

```
struct IUMSThreadProxy : public IThreadProxy;
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Iumsthreadproxy::entercriticalregion](#entercriticalregion)|Kritik bir bölge girin için çağrılır. Bir kritik bölgesindeki olduğunda Zamanlayıcı bölge sırasında gerçekleşen zaman uyumsuz engelleme işlemleri gözlemleyeceksiniz değil. Bu zamanlayıcı için sayfa hataları, iş parçacığını askıya alma, çekirdek zaman uyumsuz yordam çağrılarını (APCs) ve UMS iş parçacığı benzeri reentered değil, anlamına gelir.|
|[Iumsthreadproxy::enterhypercriticalregion](#enterhypercriticalregion)|Hyper-kritik bir bölge girin için çağrılır. Bir hyper-kritik bölgesindeki olduğunda Zamanlayıcı bölge sırasında gerçekleşen engelleme işlemleri gözlemleyeceksiniz değil. Başka bir deyişle, Zamanlayıcı işlev çağrıları, blok, sayfa hataları, askıya alma, çekirdek zaman uyumsuz yordam çağrılarını (APCs) iş parçacığı ve benzeri, bir UMS için iş parçacığı kilit edinme girişimlerini engellemek için reentered değil.|
|[Iumsthreadproxy::exitcriticalregion](#exitcriticalregion)|Kritik bir bölge çıkmak için çağrılır.|
|[Iumsthreadproxy::exithypercriticalregion](#exithypercriticalregion)|Hyper-kritik bir bölge çıkmak için çağrılır.|
|[Iumsthreadproxy::getcriticalregiontype](#getcriticalregiontype)|Ne tür bir iş parçacığı proxy'sini içinde kritik bölgedir döndürür. Kritik bir bölge ve hyper-kritik bir bölge kodu girmesinden, kritik hyper bölgeleri kritik bölgeler, bir alt kümesi olduğundan `InsideHyperCriticalRegion` döndürülür.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Ithreadproxy](ithreadproxy-structure.md)

`IUMSThreadProxy`

## <a name="requirements"></a>Gereksinimler

**Başlık:** concrtrm.h

**Namespace:** eşzamanlılık

##  <a name="entercriticalregion"></a>  Iumsthreadproxy::entercriticalregion yöntemi

Kritik bir bölge girin için çağrılır. Bir kritik bölgesindeki olduğunda Zamanlayıcı bölge sırasında gerçekleşen zaman uyumsuz engelleme işlemleri gözlemleyeceksiniz değil. Bu zamanlayıcı için sayfa hataları, iş parçacığını askıya alma, çekirdek zaman uyumsuz yordam çağrılarını (APCs) ve UMS iş parçacığı benzeri reentered değil, anlamına gelir.

```
virtual int EnterCriticalRegion() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Kritik bölge yeni derinliği. Kritik desteklemeyeceğini bölgelerdir.

##  <a name="enterhypercriticalregion"></a>  Iumsthreadproxy::enterhypercriticalregion yöntemi

Hyper-kritik bir bölge girin için çağrılır. Bir hyper-kritik bölgesindeki olduğunda Zamanlayıcı bölge sırasında gerçekleşen engelleme işlemleri gözlemleyeceksiniz değil. Başka bir deyişle, Zamanlayıcı işlev çağrıları, blok, sayfa hataları, askıya alma, çekirdek zaman uyumsuz yordam çağrılarını (APCs) iş parçacığı ve benzeri, bir UMS için iş parçacığı kilit edinme girişimlerini engellemek için reentered değil.

```
virtual int EnterHyperCriticalRegion() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Hyper-kritik bölge yeni derinliği. Hyper-kritik desteklemeyeceğini bölgelerdir.

### <a name="remarks"></a>Açıklamalar

Zamanlayıcı hakkında ne çağırdığı yöntemleri ve hangi kilitler alması gibi bölgelerde son derece dikkatli olmanız gerekir. Bu tür bir bölgedeki kod Zamanlayıcı zamanlama için sorumlu olduğu bir şey tarafından tutulan bir kilit engelliyorsa, kilitlenme beklenebilir.

##  <a name="exitcriticalregion"></a>  Iumsthreadproxy::exitcriticalregion yöntemi

Kritik bir bölge çıkmak için çağrılır.

```
virtual int ExitCriticalRegion() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Kritik bölge yeni derinliği. Kritik desteklemeyeceğini bölgelerdir.

##  <a name="exithypercriticalregion"></a>  Iumsthreadproxy::exithypercriticalregion yöntemi

Hyper-kritik bir bölge çıkmak için çağrılır.

```
virtual int ExitHyperCriticalRegion() = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Hyper-kritik bölge yeni derinliği. Hyper-kritik desteklemeyeceğini bölgelerdir.

##  <a name="getcriticalregiontype"></a>  Iumsthreadproxy::getcriticalregiontype metodu

Ne tür bir iş parçacığı proxy'sini içinde kritik bölgedir döndürür. Kritik bir bölge ve hyper-kritik bir bölge kodu girmesinden, kritik hyper bölgeleri kritik bölgeler, bir alt kümesi olduğundan `InsideHyperCriticalRegion` döndürülür.

```
virtual CriticalRegionType GetCriticalRegionType() const = 0;
```

### <a name="return-value"></a>Dönüş Değeri

İş parçacığı proxy'sini kritik bölge içinde türüdür.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)<br/>
[IUMSScheduler Yapısı](iumsscheduler-structure.md)
