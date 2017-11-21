---
title: "tile_barrier sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- tile_barrier
- AMP/tile_barrier
- AMP/Concurrency::tile_barrier::tile_barrier::tile_barrier
- AMP/Concurrency::tile_barrier::tile_barrier::wait
- AMP/Concurrency::tile_barrier::tile_barrier::wait_with_all_memory_fence
- AMP/Concurrency::tile_barrier::tile_barrier::wait_with_global_memory_fence
- AMP/Concurrency::tile_barrier::tile_barrier::wait_with_tile_static_memory_fence
dev_langs: C++
helpviewer_keywords: tile_barrier class
ms.assetid: b4ccdccb-0032-4e11-b7bd-dc9d43445dee
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 3d6dff1e32f513007f9b99ced4000043ad27607f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="tilebarrier-class"></a>tile_barrier Sınıfı
İş parçacığı grubu (döşeme) kullanarak çalışan iş parçacıklarının yürütülmesine eşitler `wait` yöntemleri. Yalnızca çalışma zamanı bu sınıfın örneğini oluşturabilirsiniz.  
  
### <a name="syntax"></a>Sözdizimi 
  
```  
class tile_barrier;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[tile_barrier Oluşturucusu](#ctor)|Yeni bir örneğini başlatır `tile_barrier` sınıfı.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[bekleme](#wait)|Tüm iş parçacıklarının grubundaki tüm iş parçacıklarının döşemesinin bekleme bitinceye kadar yürütme durdurmak için iş parçacığı (döşeme) bildirir.|  
|[wait_with_all_memory_fence](#wait_with_all_memory_fence)|Tüm iş parçacıklarının tüm bellek erişimler tamamlanana kadar döşemesinin ve tüm iş parçacıklarının döşemesinin blokları yürütme bu çağrıyı ulaştı.|  
|[wait_with_global_memory_fence](#wait_with_global_memory_fence)|Tüm iş parçacıklarının tüm genel bellek erişen kadar döşemesinin blokları yürütülmesi tamamlandı ve tüm iş parçacıklarının bölümünden bu çağrıyı üst sınırına ulaştınız.|  
|[wait_with_tile_static_memory_fence](#wait_with_tile_static_memory_fence)|Engelleyen bir kutucukta tüm iş parçacıklarının yürütülmesine tüm kadar `tile_static` bellek erişimleri tamamlandı ve tüm iş parçacıklarının bölümünden bu çağrıyı üst sınırına ulaştınız.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `tile_barrier`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** amp.h  
  
 **Namespace:** eşzamanlılık  

## <a name="tile_barrier__ctor"></a>tile_barrier Oluşturucusu  
 Mevcut bir kopyalayarak sınıfının yeni bir örneğini başlatır.  
  
### <a name="syntax"></a>Sözdizimi 
  
```  
tile_barrier(  
    const tile_barrier& _Other ) restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>Parametreler  
 `_Other`  
 `tile_barrier` Kopyalamak için nesne.  

## <a name="wait"></a>bekleme 
Tüm iş parçacıklarının grubundaki tüm iş parçacıklarının döşemesinin bekleme bitinceye kadar yürütmeyi durdurmak için iş parçacığı (döşeme) bildirir.  
  
### <a name="syntax"></a>Sözdizimi 
  
```  
void wait() const restrict(amp);  
```    

## <a name="wait_with_all_memory_fence"></a>wait_with_all_memory_fence   
Tüm iş parçacıklarının tüm iş parçacıkları bir kutucuk, bu çağrıyı ulaştınız kadar döşemesinin yürütülmesini engeller. Bu, tüm bellek erişimler iş parçacığı döşemesinin başka bir iş parçacığı görünür ve program sırayla yürütülen sağlar.  
  
### <a name="syntax"></a>Sözdizimi 
  
```  
void wait_with_all_memory_fence() const restrict(amp);  
```  
  

## <a name="wait_with_global_memory_fence"></a>wait_with_global_memory_fence   
Tüm iş parçacıklarının tüm iş parçacıkları bir kutucuk, bu çağrıyı ulaştınız kadar döşemesinin yürütülmesini engeller. Bu, tüm genel bellek erişimler iş parçacığı döşemesinin başka bir iş parçacığı görünür ve program sırayla yürütülen sağlar.  
  
### <a name="syntax"></a>Sözdizimi 
  
```  
void wait_with_global_memory_fence() const  restrict(amp);  
```

## <a name="wait_with_tile_static_memory_fence"></a>wait_with_tile_static_memory_fence   
Tüm iş parçacıklarının tüm iş parçacıkları bir kutucuk, bu çağrıyı ulaştınız kadar döşemesinin yürütülmesini engeller. Bu sağlar `tile_static` erişir iş parçacığı döşemesinin başka bir iş parçacığı görünür ve program sırayla yürütülen bellek.  
  
### <a name="syntax"></a>Sözdizimi 
  
```  
void wait_with_tile_static_memory_fence() const restrict(amp);  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace (C++ AMP)](concurrency-namespace-cpp-amp.md)
