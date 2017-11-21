---
title: "unorm_3 sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp_short_vectors/Concurrency::graphics::unorm_3::set_zy
- amp_short_vectors/Concurrency::graphics::unorm_3::zxy
- amp_short_vectors/Concurrency::graphics::unorm_3::set_zyx
- amp_short_vectors/Concurrency::graphics::unorm_3::operator-=
- amp_short_vectors/Concurrency::graphics::unorm_3::xzy
- amp_short_vectors/Concurrency::graphics::unorm_3::get_xzy
- amp_short_vectors/Concurrency::graphics::unorm_3::zyx
- amp_short_vectors/Concurrency::graphics::unorm_3::rgb
- amp_short_vectors/Concurrency::graphics::unorm_3::set_xz
- amp_short_vectors/Concurrency::graphics::unorm_3::set_yxz
- amp_short_vectors/Concurrency::graphics::unorm_3::set_yx
- amp_short_vectors/Concurrency::graphics::unorm_3::br
- amp_short_vectors/Concurrency::graphics::unorm_3::get_zy
- amp_short_vectors/Concurrency::graphics::unorm_3::set_zx
- amp_short_vectors/Concurrency::graphics::unorm_3::get_xyz
- amp_short_vectors/Concurrency::graphics::unorm_3::b
- amp_short_vectors/Concurrency::graphics::unorm_3::set_xyz
- amp_short_vectors/Concurrency::graphics::unorm_3
- amp_short_vectors/Concurrency::graphics::unorm_3::set_z
- amp_short_vectors/Concurrency::graphics::unorm_3::set_xy
- amp_short_vectors/Concurrency::graphics::unorm_3::get_zyx
- amp_short_vectors/Concurrency::graphics::unorm_3::get_xy
- amp_short_vectors/Concurrency::graphics::unorm_3::x
- amp_short_vectors/Concurrency::graphics::unorm_3::get_zxy
- amp_short_vectors/Concurrency::graphics::unorm_3::z
- amp_short_vectors/Concurrency::graphics::unorm_3::get_x
- amp_short_vectors/Concurrency::graphics::unorm_3::operator=
- amp_short_vectors/Concurrency::graphics::unorm_3::yxz
- amp_short_vectors/Concurrency::graphics::unorm_3::get_yx
- amp_short_vectors/Concurrency::graphics::unorm_3::gbr
- amp_short_vectors/Concurrency::graphics::unorm_3::get_yxz
- amp_short_vectors/Concurrency::graphics::unorm_3::operator--
- amp_short_vectors/Concurrency::graphics::unorm_3::operator/=
- amp_short_vectors/Concurrency::graphics::unorm_3::brg
- amp_short_vectors/Concurrency::graphics::unorm_3::gb
- amp_short_vectors/Concurrency::graphics::unorm_3::zy
- amp_short_vectors/Concurrency::graphics::unorm_3::set_xzy
- amp_short_vectors/Concurrency::graphics::unorm_3::get_yzx
- amp_short_vectors/Concurrency::graphics::unorm_3::rb
- amp_short_vectors/Concurrency::graphics::unorm_3::gr
- amp_short_vectors/Concurrency::graphics::unorm_3::zx
- amp_short_vectors/Concurrency::graphics::unorm_3::r
- amp_short_vectors/Concurrency::graphics::unorm_3::xyz
- amp_short_vectors/Concurrency::graphics::unorm_3::grb
- amp_short_vectors/Concurrency::graphics::unorm_3::bg
- amp_short_vectors/Concurrency::graphics::unorm_3::get_y
- amp_short_vectors/Concurrency::graphics::unorm_3::g
- amp_short_vectors/Concurrency::graphics::unorm_3::yz
- amp_short_vectors/Concurrency::graphics::unorm_3::yx
- amp_short_vectors/Concurrency::graphics::unorm_3::get_xz
- amp_short_vectors/Concurrency::graphics::unorm_3::set_zxy
- amp_short_vectors/Concurrency::graphics::unorm_3::get_z
- amp_short_vectors/Concurrency::graphics::unorm_3::bgr
- amp_short_vectors/Concurrency::graphics::unorm_3::set_x
- amp_short_vectors/Concurrency::graphics::unorm_3::operator-
- amp_short_vectors/Concurrency::graphics::unorm_3::y
- amp_short_vectors/Concurrency::graphics::unorm_3::set_yzx
- amp_short_vectors/Concurrency::graphics::unorm_3::get_zx
- amp_short_vectors/Concurrency::graphics::unorm_3::yzx
- amp_short_vectors/Concurrency::graphics::unorm_3::operator++
- amp_short_vectors/Concurrency::graphics::unorm_3::set_yz
- amp_short_vectors/Concurrency::graphics::unorm_3::operator+=
- amp_short_vectors/Concurrency::graphics::unorm_3::xz
- amp_short_vectors/Concurrency::graphics::unorm_3::rg
- amp_short_vectors/Concurrency::graphics::unorm_3::xy
- amp_short_vectors/Concurrency::graphics::unorm_3::operator*=
- amp_short_vectors/Concurrency::graphics::unorm_3::set_y
- amp_short_vectors/Concurrency::graphics::unorm_3::get_yz
- amp_short_vectors/Concurrency::graphics::unorm_3::rbg
dev_langs: C++
ms.assetid: ea4e7a17-5256-464c-af28-8b01962564c0
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 73f8b08fce39103936215292c3368f0e77a76017
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="unorm3-class"></a>unorm_3 Sınıfı
Kısa bir vektör üç imzasız normal sayıların temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class unorm_3;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel tür tanımları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`value_type`||  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[unorm_3 Oluşturucusu](#ctor)|Fazla Yüklendi. Varsayılan Oluşturucu, tüm öğeleri 0 ile başlatır.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|unorm_3::get_x||  
|unorm_3::get_xy||  
|unorm_3::get_xyz||  
|unorm_3::get_xz||  
|unorm_3::get_xzy||  
|unorm_3::get_y||  
|unorm_3::get_yx||  
|unorm_3::get_yxz||  
|unorm_3::get_yz||  
|unorm_3::get_yzx||  
|unorm_3::get_z||  
|unorm_3::get_zx||  
|unorm_3::get_zxy||  
|unorm_3::get_zy||  
|unorm_3::get_zyx||  
|Unorm_3::ref_b||  
|Unorm_3::ref_g||  
|Unorm_3::ref_r||  
|Unorm_3::ref_x||  
|Unorm_3::ref_y||  
|Unorm_3::ref_z||  
|unorm_3::set_x||  
|unorm_3::set_xy||  
|unorm_3::set_xyz||  
|unorm_3::set_xz||  
|unorm_3::set_xzy||  
|unorm_3::set_y||  
|unorm_3::set_yx||  
|unorm_3::set_yxz||  
|unorm_3::set_yz||  
|unorm_3::set_yzx||  
|unorm_3::set_z||  
|unorm_3::set_zx||  
|unorm_3::set_zxy||  
|unorm_3::set_zy||  
|unorm_3::set_zyx||  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|unorm_3::operator--||  
|unorm_3::operator * =||  
|unorm_3::operator ve =||  
|unorm_3::operator ++||  
|unorm_3::operator +=||  
|unorm_3::operator =||  
|unorm_3::operator-=||  
  
### <a name="public-constants"></a>Genel sabitler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[boyutu sabiti](#unorm_3__size)||  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|unorm_3::b||  
|unorm_3::BG||  
|unorm_3::BGR||  
|unorm_3::br||  
|unorm_3::brg||  
|unorm_3::g||  
|unorm_3::GB||  
|unorm_3::GBR||  
|unorm_3::Gr||  
|unorm_3::Grb||  
|unorm_3::r||  
|unorm_3::RB||  
|unorm_3::rbg||  
|unorm_3::rg||  
|unorm_3::RGB||  
|unorm_3::x||  
|unorm_3::xy||  
|unorm_3::xyz||  
|unorm_3::xz||  
|unorm_3::xzy||  
|unorm_3::y||  
|unorm_3::yx||  
|unorm_3::yxz||  
|unorm_3::YZ||  
|unorm_3::yzx||  
|unorm_3::z||  
|unorm_3::ZX||  
|unorm_3::zxy||  
|unorm_3::ZY||  
|unorm_3::zyx||  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `unorm_3`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** amp_short_vectors.h  
  
 **Namespace:** Concurrency::graphics  
  
##  <a name="ctor"></a>unorm_3 

 Varsayılan Oluşturucu, tüm öğeleri 0 ile başlatır.  
  
```  
unorm_3() restrict(amp,
    cpu);

 
unorm_3(
    unorm _V0,  
    unorm _V1,  
    unorm _V2) restrict(amp,
    cpu);

 
unorm_3(
    float _V0,  
    float _V1,  
    float _V2) restrict(amp,
    cpu);

 
unorm_3(
    unorm _V) restrict(amp,
    cpu);

 
explicit unorm_3(
    float _V) restrict(amp,
    cpu);

 
unorm_3(
    const unorm_3& _Other) restrict(amp,
    cpu);

 
explicit inline unorm_3(
    const uint_3& _Other) restrict(amp,
    cpu);

 
explicit inline unorm_3(
    const int_3& _Other) restrict(amp,
    cpu);

 
explicit inline unorm_3(
    const float_3& _Other) restrict(amp,
    cpu);

 
explicit inline unorm_3(
    const norm_3& _Other) restrict(amp,
    cpu);

 
explicit inline unorm_3(
    const double_3& _Other) restrict(amp,
    cpu);
```  
  
### <a name="parameters"></a>Parametreler  
 `_V0`  
 Öğeyi 0 başlatmak için değer.  
  
 `_V1`  
 1 öğesi başlatmak için değeri.  
  
 `_V2`  
 Öğe 2 başlatmak için değeri.  
  
 `_V`  
 Başlatma için değer.  
  
 `_Other`  
 Başlatmak için kullanılan nesne.  
  
##  <a name="unorm_3__size"></a>boyutu 

```  
static const int size = 3;  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CONCURRENCY::Graphics Namespace](concurrency-graphics-namespace.md)
