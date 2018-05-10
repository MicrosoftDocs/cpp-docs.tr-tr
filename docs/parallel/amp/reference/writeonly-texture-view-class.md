---
title: writeonly_texture_view sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: reference
f1_keywords:
- writeonly_texture_view
- AMP_GRAPHICS/writeonly_texture_view
- AMP_GRAPHICS/Concurrency::graphics::writeonly_texture_view
- AMP_GRAPHICS/Concurrency::graphics::writeonly_texture_view::set
- AMP_GRAPHICS/Concurrency::graphics::rank Constant
dev_langs:
- C++
ms.assetid: 8d117ad3-0a1c-41ae-b29c-7c95fdd4d04d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a6b1bc5c90fd837f56dbd98eddb37f624e78080b
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="writeonlytextureview-class"></a>writeonly_texture_view Sınıfı
Bir doku WriteOnly erişim sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <
    typename value_type,  
    int _Rank  
>  
class writeonly_texture_view;  
 
template <
    typename value_type,  
    int _Rank  
>  
class writeonly_texture_view<value_type, _Rank> : public details::_Texture_base<value_type, _Rank>;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `value_type`  
 Dokudaki öğelerin türü.  
  
 `_Rank`  
 Doku derecesini.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel tür tanımları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`scalar_type`||  
|`value_type`|Dokudaki öğelerin türü.|  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[writeonly_texture_view Oluşturucusu](#ctor)|Yeni bir örneğini başlatır `writeonly_texture_view` sınıfı.|  
|[~ writeonly_texture_view yok Edicisi](#ctor)|Bozar `writeonly_texture_view` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[set](#set)|Öğesinin değeri belirtilen dizindeki ayarlar.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[operator=](#operator_eq)|Belirtilen kopyalar `writeonly_texture_view` bu bir nesne.|  
  
### <a name="public-constants"></a>Genel sabitler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[sıra sabiti](#rank)|Derecesini alır `writeonly_texture_view` nesnesi.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `_Texture_base`  
  
 `writeonly_texture_view`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** amp_graphics.h  
  
 **Namespace:** Concurrency::graphics  
  
##  <a name="dtor"></a> ~ writeonly_texture_view 

 Bozar `writeonly_texture_view` nesnesi.  
  
```  
~writeonly_texture_view() restrict(amp,cpu);
```  
  
##  <a name="operator_eq"></a> işleç = 

 Belirtilen kopyalar `writeonly_texture_view` bu bir nesne.  
  
```  
writeonly_texture_view<value_type, _Rank>& operator= (
    const writeonly_texture_view<value_type, _Rank>& _Other) restrict(amp,cpu);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Other`  
 `writeonly_texture_view` Kopyalanacak nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu başvuru `writeonly_texture_view` nesnesi.  
  
##  <a name="rank"></a> RANK 

 Derecesini alır `writeonly_texture_view` nesnesi.  
  
```  
static const int rank = _Rank;  
```  
  
##  <a name="set"></a> ayarlama 

 Öğesinin değeri belirtilen dizindeki ayarlar.  
  
```  
void set(
    const index<_Rank>& _Index,  
    const value_type& value) const restrict(amp);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Index`  
 Öğenin dizini.  
  
 `value`  
 Öğesinin yeni değeri.  
  
##  <a name="ctor"></a> writeonly_texture_view 

 Yeni bir örneğini başlatır `writeonly_texture_view` sınıfı.  
  
```  
writeonly_texture_view(
    texture<value_type, 
    _Rank>& _Src) restrict(amp);

 
writeonly_texture_view(
    const writeonly_texture_view<value_type,  
    _Rank>& _Src) restrict(amp,cpu);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Rank`  
 Doku derecesini.  
  
 `value_type`  
 Dokudaki öğelerin türü.  
  
 `_Src`  
 Oluşturmak için kullanılan doku `writeonly_texture_view`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Concurrency::graphics Ad Alanı](concurrency-graphics-namespace.md)
