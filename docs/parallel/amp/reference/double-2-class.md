---
title: "double_2 sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp_short_vectors/Concurrency::graphics::double_2::set_x
- amp_short_vectors/Concurrency::graphics::double_2::operator+=
- amp_short_vectors/Concurrency::graphics::double_2::operator=
- amp_short_vectors/Concurrency::graphics::double_2::operator/=
- amp_short_vectors/Concurrency::graphics::double_2::operator*=
- amp_short_vectors/Concurrency::graphics::double_2::yx
- amp_short_vectors/Concurrency::graphics::double_2::y
- amp_short_vectors/Concurrency::graphics::double_2::xy
- amp_short_vectors/Concurrency::graphics::double_2::set_xy
- amp_short_vectors/Concurrency::graphics::double_2::get_yx
- amp_short_vectors/Concurrency::graphics::double_2::set_yx
- amp_short_vectors/Concurrency::graphics::double_2::get_xy
- amp_short_vectors/Concurrency::graphics::double_2::operator++
- amp_short_vectors/Concurrency::graphics::double_2::get_x
- amp_short_vectors/Concurrency::graphics::double_2::operator-=
- amp_short_vectors/Concurrency::graphics::double_2::rg
- amp_short_vectors/Concurrency::graphics::double_2::gr
- amp_short_vectors/Concurrency::graphics::double_2::get_y
- amp_short_vectors/Concurrency::graphics::double_2::x
- amp_short_vectors/Concurrency::graphics::double_2::r
- amp_short_vectors/Concurrency::graphics::double_2::operator--
- amp_short_vectors/Concurrency::graphics::double_2
- amp_short_vectors/Concurrency::graphics::double_2::operator-
- amp_short_vectors/Concurrency::graphics::double_2::g
- amp_short_vectors/Concurrency::graphics::double_2::set_y
dev_langs: C++
ms.assetid: c19c2d21-3cbf-4ce5-b460-3b8253688f82
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c476812eb9ecbcd10286fb6a074d9909a581de64
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="double2-class"></a>double_2 Sınıfı
Kısa bir vektör 2 çift 's değerini temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class double_2;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel tür tanımları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`value_type`||  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[double_2 Oluşturucusu](#ctor)|Fazla Yüklendi. Varsayılan Oluşturucu, tüm öğeleri 0 ile başlatır.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|double_2::get_x||  
|double_2::get_xy||  
|double_2::get_y||  
|double_2::get_yx||  
|double_2::ref_g||  
|double_2::ref_r||  
|double_2::ref_x||  
|double_2::ref_y||  
|double_2::set_x||  
|double_2::set_xy||  
|double_2::set_y||  
|double_2::set_yx||  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|double_2::operator-||  
|double_2::operator--||  
|double_2::operator * =||  
|double_2::operator ve =||  
|double_2::operator ++||  
|double_2::operator +=||  
|double_2::operator =||  
|double_2::operator-=||  
  
### <a name="public-constants"></a>Genel sabitler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|double_2::size Sabiti||  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|double_2::g||  
|double_2::Gr||  
|double_2::r||  
|double_2::rg||  
|double_2::x||  
|double_2::xy||  
|double_2::y||  
|double_2::yx||  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `double_2`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** amp_short_vectors.h  
  
 **Namespace:** Concurrency::graphics  
  
##  <a name="ctor"></a>double_2 

 Varsayılan Oluşturucu, tüm öğeleri 0 ile başlatır.  
  
```  
double_2() restrict(amp,
    cpu);

 
double_2(
    double _V0,  
    double _V1) restrict(amp,
    cpu);

 
double_2(
    double _V) restrict(amp,
    cpu);

 
double_2(
    const double_2& _Other) restrict(amp,
    cpu);

 
explicit inline double_2(
    const uint_2& _Other) restrict(amp,
    cpu);

 
explicit inline double_2(
    const int_2& _Other) restrict(amp,
    cpu);

 
explicit inline double_2(
    const float_2& _Other) restrict(amp,
    cpu);

 
explicit inline double_2(
    const unorm_2& _Other) restrict(amp,
    cpu);

 
explicit inline double_2(
    const norm_2& _Other) restrict(amp,
    cpu);
```  
  
### <a name="parameters"></a>Parametreler  
 `_V0`  
 Öğeyi 0 başlatmak için değer.  
  
 `_V1`  
 1 öğesi başlatmak için değeri.  
  
 `_V`  
 Başlatma için değer.  
  
 `_Other`  
 Başlatmak için kullanılan nesne.  
  
##  <a name="double_2__size"></a>boyutu 

```  
static const int size = 2;  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CONCURRENCY::Graphics Namespace](concurrency-graphics-namespace.md)
