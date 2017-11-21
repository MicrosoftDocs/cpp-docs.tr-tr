---
title: "Norm sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- norm
- AMP_SHORT_VECTORS/norm
- AMP_SHORT_VECTORS/Concurrency::graphics::norm Constructor
dev_langs: C++
ms.assetid: 73002f3d-c25e-4119-bcd3-4c46c9b6abf1
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7d35bc7781b1a57fdc0b8b68c5d4f78046d19134
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="norm-class"></a>norm Sınıfı
Norm numarasını temsil eder. Her bir kayan bir öğedir nokta sayısı aralığında [-1.0f, 1.0f].  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class norm;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Norm Oluşturucusu](#ctor)|Fazla Yüklendi. Varsayılan Oluşturucu. İçin 0.0f başlatır.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|Norm::operator-||  
|Norm::operator--||  
|Norm::operator float|Dönüşüm işleci. Kayan norm sayıya dönüştürme noktası değeri.|  
|Norm::operator * =||  
|Norm::operator ve =||  
|Norm::operator ++||  
|Norm::operator +=||  
|Norm::operator =||  
|Norm::operator-=||  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `norm`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** amp_short_vectors.h  
  
 **Namespace:** Concurrency::graphics  
  
##  <a name="ctor"></a>Norm 

 Varsayılan Oluşturucu. İçin 0.0f başlatır.  
  
```  
norm(
    void) restrict(amp,
    cpu);

 
explicit norm(
    float _V) restrict(amp,
    cpu);

 
explicit norm(
    unsigned int _V) restrict(amp,
    cpu);

 
explicit norm(
    int _V) restrict(amp,
    cpu);

 
explicit norm(
    double _V) restrict(amp,
    cpu);

 
norm(
    const norm& _Other) restrict(amp,
    cpu);

 
norm(
    const unorm& _Other) restrict(amp,
    cpu);
```  
  
### <a name="parameters"></a>Parametreler  
 `_V`  
 Başlatmak için kullanılan değer.  
  
 `_Other`  
 Başlatmak için kullanılan nesne.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CONCURRENCY::Graphics Namespace](concurrency-graphics-namespace.md)
