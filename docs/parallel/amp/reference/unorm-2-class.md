---
title: "unorm_2 sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp_short_vectors/Concurrency::graphics::unnorm_2::operator+=
- amp_short_vectors/Concurrency::graphics::unnorm_2::y
- amp_short_vectors/Concurrency::graphics::unnorm_2::set_y
- amp_short_vectors/Concurrency::graphics::unnorm_2::x
- amp_short_vectors/Concurrency::graphics::unnorm_2::get_yx
- amp_short_vectors/Concurrency::graphics::unnorm_2::operator--
- amp_short_vectors/Concurrency::graphics::unnorm_2::set_xy
- amp_short_vectors/Concurrency::graphics::unnorm_2::operator*=
- amp_short_vectors/Concurrency::graphics::unnorm_2::xy
- amp_short_vectors/Concurrency::graphics::unnorm_2::get_y
- amp_short_vectors/Concurrency::graphics::unnorm_2::operator=
- amp_short_vectors/Concurrency::graphics::unnorm_2::set_x
- amp_short_vectors/Concurrency::graphics::unnorm_2::rg
- amp_short_vectors/Concurrency::graphics::unorm_2
- amp_short_vectors/Concurrency::graphics::unnorm_2::operator-=
- amp_short_vectors/Concurrency::graphics::unnorm_2::operator/=
- amp_short_vectors/Concurrency::graphics::unnorm_2::get_xy
- amp_short_vectors/Concurrency::graphics::unnorm_2::set_yx
- amp_short_vectors/Concurrency::graphics::unnorm_2::yx
- amp_short_vectors/Concurrency::graphics::unnorm_2::gr
- amp_short_vectors/Concurrency::graphics::unnorm_2::r
- amp_short_vectors/Concurrency::graphics::unnorm_2::operator-
- amp_short_vectors/Concurrency::graphics::unnorm_2::get_x
- amp_short_vectors/Concurrency::graphics::unnorm_2::g
- amp_short_vectors/Concurrency::graphics::unnorm_2::operator++
dev_langs: C++
ms.assetid: 62e88ea7-e29f-4f62-95ce-61a1f39f5e34
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d050e819361175f1808a440671de684499ebfa3f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="unorm2-class"></a>unorm_2 Sınıfı
Kısa bir vektör iki imzasız normal sayıların temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class unorm_2;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel tür tanımları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`value_type`||  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[unorm_2 Oluşturucusu](#ctor)|Fazla Yüklendi. Varsayılan Oluşturucu, tüm öğeleri 0 ile başlatır.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|unorm_2::get_x||  
|unorm_2::get_xy||  
|unorm_2::get_y||  
|unorm_2::get_yx||  
|unorm_2::ref_g||  
|unorm_2::ref_r||  
|unorm_2::ref_x||  
|unorm_2::ref_y||  
|unorm_2::set_x||  
|unorm_2::set_xy||  
|unorm_2::set_y||  
|unorm_2::set_yx||  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|unorm_2::operator--||  
|unorm_2::operator * =||  
|unorm_2::operator ve =||  
|unorm_2::operator ++||  
|unorm_2::operator +=||  
|unorm_2::operator =||  
|unorm_2::operator-=||  
  
### <a name="public-constants"></a>Genel sabitler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|unorm_2::size Sabiti||  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|unorm_2::g||  
|unorm_2::Gr||  
|unorm_2::r||  
|unorm_2::rg||  
|unorm_2::x||  
|unorm_2::xy||  
|unorm_2::y||  
|unorm_2::yx||  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `unorm_2`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** amp_short_vectors.h  
  
 **Namespace:** Concurrency::graphics  
  
##  <a name="ctor"></a>unorm_2 

 Varsayılan Oluşturucu, tüm öğeleri 0 ile başlatır.  
  
```  
unorm_2() restrict(amp,
    cpu);

 
unorm_2(
    unorm _V0,  
    unorm _V1) restrict(amp,
    cpu);

 
unorm_2(
    float _V0,  
    float _V1) restrict(amp,
    cpu);

 
unorm_2(
    unorm _V) restrict(amp,
    cpu);

 
explicit unorm_2(
    float _V) restrict(amp,
    cpu);

 
unorm_2(
    const unorm_2& _Other) restrict(amp,
    cpu);

 
explicit inline unorm_2(
    const uint_2& _Other) restrict(amp,
    cpu);

 
explicit inline unorm_2(
    const int_2& _Other) restrict(amp,
    cpu);

 
explicit inline unorm_2(
    const float_2& _Other) restrict(amp,
    cpu);

 
explicit inline unorm_2(
    const norm_2& _Other) restrict(amp,
    cpu);

 
explicit inline unorm_2(
    const double_2& _Other) restrict(amp,
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
  
##  <a name="unorm_2__size"></a>boyutu 

```  
static const int size = 2;  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Concurrency::graphics Ad Alanı](concurrency-graphics-namespace.md)
