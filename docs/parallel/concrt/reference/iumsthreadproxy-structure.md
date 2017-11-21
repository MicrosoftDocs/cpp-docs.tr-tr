---
title: "Iumsthreadproxy yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IUMSThreadProxy
- CONCRTRM/concurrency::IUMSThreadProxy
- CONCRTRM/concurrency::IUMSThreadProxy::IUMSThreadProxy::EnterCriticalRegion
- CONCRTRM/concurrency::IUMSThreadProxy::IUMSThreadProxy::EnterHyperCriticalRegion
- CONCRTRM/concurrency::IUMSThreadProxy::IUMSThreadProxy::ExitCriticalRegion
- CONCRTRM/concurrency::IUMSThreadProxy::IUMSThreadProxy::ExitHyperCriticalRegion
- CONCRTRM/concurrency::IUMSThreadProxy::IUMSThreadProxy::GetCriticalRegionType
dev_langs: C++
helpviewer_keywords: IUMSThreadProxy structure
ms.assetid: 61c69b7e-5c37-4048-bcb4-e75c536afd86
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 87ac2a36c83e6b05e671c0110b054325d53fc887
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="iumsthreadproxy-structure"></a>IUMSThreadProxy Yapısı
Bir iş parçacığı için bir Özet yürütme. Kullanıcı modu zamanlanabilir (UMS) iş parçacıklarının verilebilmesi için Zamanlayıcı istiyorsanız, Zamanlayıcı İlkesi öğesinin değeri ayarlayın `SchedulerKind` için `UmsThreadDefault`ve uygulamanıza `IUMSScheduler` arabirimi. UMS iş parçacıkları yalnızca desteklenen 64-bit işletim sistemi sürümü Windows 7 ve üzeri.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
struct IUMSThreadProxy : public IThreadProxy;
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Iumsthreadproxy::entercriticalregion](#entercriticalregion)|Kritik bir bölge girmek için çağrılır. Bir kritik bölge Zaman içindeki Zamanlayıcı bölge sırasında gerçekleşen zaman uyumsuz engelleme işlemleri Gözlemleme. Bu zamanlayıcı sayfa hataları, iş parçacığı suspensions, çekirdek zaman uyumsuz yordam çağrılarını (APCs) ve UMS iş parçacığı için belirli bir benzeri girilmesi değil, anlamına gelir.|  
|[Iumsthreadproxy::enterhypercriticalregion](#enterhypercriticalregion)|Bir kritik hyper bölge girmek için çağrılır. Bir kritik hyper bölge Zaman içindeki Zamanlayıcı bölge sırasında gerçekleşecek herhangi bir engelleyici işlem Gözlemleme. Bu zamanlayıcı işlev çağrıları, sayfa hataları, hangi blok suspensions, çekirdek zaman uyumsuz yordam çağrılarını (APCs), iş parçacığı ve benzeri, UMS için iş parçacığı kilit edinme girişimlerini engellemek için girilmesi değil anlamına gelir.|  
|[Iumsthreadproxy::exitcriticalregion](#exitcriticalregion)|Kritik bir bölge çıkmak için çağrılır.|  
|[Iumsthreadproxy::exithypercriticalregion](#exithypercriticalregion)|Bir kritik hyper bölge çıkmak için çağrılır.|  
|[Iumsthreadproxy::getcriticalregiontype](#getcriticalregiontype)|Ne tür bir iş parçacığı proxy içinde kritik bölgedir döndürür. Kritik bir bölge ve kritik hyper bölge kodu girmesinden varsa kritik hyper bölgeler kritik bölgeler, bir alt kümesi olduğundan `InsideHyperCriticalRegion` döndürülür.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [Ithreadproxy](ithreadproxy-structure.md)  
  
 `IUMSThreadProxy`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** concrtrm.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="entercriticalregion"></a>Iumsthreadproxy::entercriticalregion yöntemi  
 Kritik bir bölge girmek için çağrılır. Bir kritik bölge Zaman içindeki Zamanlayıcı bölge sırasında gerçekleşen zaman uyumsuz engelleme işlemleri Gözlemleme. Bu zamanlayıcı sayfa hataları, iş parçacığı suspensions, çekirdek zaman uyumsuz yordam çağrılarını (APCs) ve UMS iş parçacığı için belirli bir benzeri girilmesi değil, anlamına gelir.  
  
```
virtual int EnterCriticalRegion() = 0;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kritik bölge yeni derinliği. Kritik bölgeler desteklemeyeceğini.  
  
##  <a name="enterhypercriticalregion"></a>Iumsthreadproxy::enterhypercriticalregion yöntemi  
 Bir kritik hyper bölge girmek için çağrılır. Bir kritik hyper bölge Zaman içindeki Zamanlayıcı bölge sırasında gerçekleşecek herhangi bir engelleyici işlem Gözlemleme. Bu zamanlayıcı işlev çağrıları, sayfa hataları, hangi blok suspensions, çekirdek zaman uyumsuz yordam çağrılarını (APCs), iş parçacığı ve benzeri, UMS için iş parçacığı kilit edinme girişimlerini engellemek için girilmesi değil anlamına gelir.  
  
```
virtual int EnterHyperCriticalRegion() = 0;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kritik hyper bölge yeni derinliği. Hyper-kritik bölgeler desteklemeyeceğini.  
  
### <a name="remarks"></a>Açıklamalar  
 Zamanlayıcı ne yöntemleri çağırır ve ne kilitler alması gibi bölgelerde hakkında çok dikkatli olmanız gerekir. Bu tür bir bölgede kod tarafından bir şey Zamanlayıcı zamanlama için sorumludur tutulur bir kilit engelliyorsa kilitlenme oluşması beklenebilir.  
  
##  <a name="exitcriticalregion"></a>Iumsthreadproxy::exitcriticalregion yöntemi  
 Kritik bir bölge çıkmak için çağrılır.  
  
```
virtual int ExitCriticalRegion() = 0;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kritik bölge yeni derinliği. Kritik bölgeler desteklemeyeceğini.  
  
##  <a name="exithypercriticalregion"></a>Iumsthreadproxy::exithypercriticalregion yöntemi  
 Bir kritik hyper bölge çıkmak için çağrılır.  
  
```
virtual int ExitHyperCriticalRegion() = 0;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kritik hyper bölge yeni derinliği. Hyper-kritik bölgeler desteklemeyeceğini.  
  
##  <a name="getcriticalregiontype"></a>Iumsthreadproxy::getcriticalregiontype yöntemi  
 Ne tür bir iş parçacığı proxy içinde kritik bölgedir döndürür. Kritik bir bölge ve kritik hyper bölge kodu girmesinden varsa kritik hyper bölgeler kritik bölgeler, bir alt kümesi olduğundan `InsideHyperCriticalRegion` döndürülür.  
  
```
virtual CriticalRegionType GetCriticalRegionType() const = 0;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İş parçacığı proxy içinde kritik bölgedir türü.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)   
 [Iumsscheduler yapısı](iumsscheduler-structure.md)
