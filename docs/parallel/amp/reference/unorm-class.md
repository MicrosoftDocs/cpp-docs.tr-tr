---
title: unorm sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: reference
f1_keywords:
- unorm
- AMP_SHORT_VECTORS/unorm
- AMP_SHORT_VECTORS/Concurrency::graphics::unorm Constructor
dev_langs:
- C++
ms.assetid: bc30bd20-6452-4d5f-9158-3b11c4c16ed2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e235930b73c4e9c2bc110d142ad734669f9c6ccc
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33695687"
---
# <a name="unorm-class"></a>unorm Sınıfı
Unorm numarasını temsil eder. Her bir kayan bir öğedir [0.0f, 1.0f] aralığında nokta sayısı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class unorm;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[unorm Oluşturucusu](#ctor)|Fazla Yüklendi. Varsayılan Oluşturucu. İçin 0.0f başlatır.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|unorm::operator--||  
|unorm::operator float|Dönüşüm işleci. Kayan unorm sayıya dönüştürme noktası değeri.|  
|unorm::operator * =||  
|unorm::operator ve =||  
|unorm::operator ++||  
|unorm::operator +=||  
|unorm::operator=||  
|unorm::operator-=||  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `unorm`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** amp_short_vectors.h  
  
 **Namespace:** Concurrency::graphics  
  
##  <a name="ctor"></a> unorm 

 Varsayılan Oluşturucu. İçin 0.0f başlatır.  
  
```  
unorm(
    void) restrict(amp,
    cpu);

 
explicit unorm(
    float _V) restrict(amp,
    cpu);

 
explicit unorm(
    unsigned int _V) restrict(amp,
    cpu);

 
explicit unorm(
    int _V) restrict(amp,
    cpu);

 
explicit unorm(
    double _V) restrict(amp,
    cpu);

 
unorm(
    const unorm& _Other) restrict(amp,
    cpu);

 
inline explicit unorm(
    const norm& _Other) restrict(amp,
    cpu);
```  
  
### <a name="parameters"></a>Parametreler  
 `_V`  
 Başlatmak için kullanılan değer.  
  
 `_Other`  
 Norm başlatmak için kullanılan nesne.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Concurrency::graphics Ad Alanı](concurrency-graphics-namespace.md)
