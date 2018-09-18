---
title: tiled_index sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: reference
f1_keywords:
- tiled_index
- AMP/tiled_index
- AMP/Concurrency::tiled_index::tiled_index
- AMP/Concurrency::tiled_index::get_tile_extent
- AMP/Concurrency::tiled_index::barrier
- AMP/Concurrency::tiled_index::global
- AMP/Concurrency::tiled_index::local
- AMP/Concurrency::tiled_index::rank
- AMP/Concurrency::tiled_index::tile
- AMP/Concurrency::tiled_index::tile_dim0
- AMP/Concurrency::tiled_index::tile_dim1
- AMP/Concurrency::tiled_index::tile_dim2
- AMP/Concurrency::tiled_index::tile_origin
- AMP/Concurrency::tiled_index::tile_extent
dev_langs:
- C++
helpviewer_keywords:
- tiled_index class
ms.assetid: 0ce2ae26-f1bb-4436-b473-a9e1b619bb38
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 47cd4cc765459acc6270c64b6cc37fe328f36757
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46069423"
---
# <a name="tiledindex-class"></a>tiled_index Sınıfı
Bir dizin sağlar bir [tiled_extent](tiled-extent-class.md) nesne. Bu sınıf öğelere yerel döşeme kaynağına ve genel kaynağa göre erişmek için özelliklere sahiptir. Döşeli boşluklar hakkında daha fazla bilgi için bkz. [kullanarak kutucuk](../../../parallel/amp/using-tiles.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <
    int _Dim0,  
    int _Dim1 = 0,  
    int _Dim2 = 0  
>  
class tiled_index : public _Tiled_index_base<3>;  
 
template <
    int _Dim0,  
    int _Dim1  
>  
class tiled_index<_Dim0, _Dim1, 0> : public _Tiled_index_base<2>;  
 
template <
    int _Dim0  
>  
class tiled_index<_Dim0, 0, 0> : public _Tiled_index_base<1>;  
```  
  
#### <a name="parameters"></a>Parametreler  
*_Dim0*<br/>
En önemli boyutun uzunluğu.  
  
*_Dim1*<br/>
Sonraki en-önemli boyutun uzunluğu.  
  
*_Dim2*<br/>
En az önemli boyutun uzunluğu.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[tiled_index Oluşturucusu](#ctor)|Yeni bir örneğini başlatır `tile_index` sınıfı.|  

  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[get_tile_extent](#tiled_index__get_tile_extent)|Döndürür bir [uzantı](extent-class.md) değerlerine sahip nesne `tiled_index` şablon bağımsız değişkenleri `_Dim0`, `_Dim1`, ve `_Dim2`.|  


  
### <a name="public-constants"></a>Genel sabitler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[engel sabiti](#tiled_index__barrier)|Depoları bir [tile_barrier](tile-barrier-class.md) geçerli iş parçacığı döşemesindeki bir engeli temsil eden nesne.|  
|||  
|[Genel sabiti](#tiled_index__global)|Depoları bir [dizin](index-class.md) nesne büyüm genel bir kılavuz nesnesine dizinde temsil eden 1, 2 veya 3.|  
|[yerel sabit](#tiled_index__local)|Depoları bir `index` nesnesinin varolan döşeme dizine göreli temsil eden 1, 2 veya 3 dereceli bir [tiled_extent](tiled-extent-class.md) nesne.|  
|[sıra sabiti](#tiled_index__rank)|Boyut sayısını tutar `tiled_index` nesne.|  
|[tile sabiti](#tiled_index__tile)|Depoları bir `index` nesnesinin boyut sayısı 1, 2 veya 3 varolan döşeme koordinatlarını temsil eden bir `tiled_extent` nesne.|  
|[tile_dim0 sabiti](#tiled_index__tile_dim0)|En önemli boyutun uzunluğunu saklar.|  
|[tile_dim1 sabiti](#tiled_index__tile_dim1)|Sonraki en-önemli boyutun uzunluğunu saklar.|  
|[tile_dim2 sabiti](#tiled_index__tile_dim2)|En az önemli boyutun uzunluğunu saklar.|  
|[tile_origin sabiti](#tiled_index__tile_origin)|Depoları bir `index` döşeme genel temsil eden 1, 2 veya 3 dereceli koordinatlarını nesnesinin bir `tiled_extent` nesne.|  

  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[tile_extent](#tile_extent)|Alır bir [uzantı](extent-class.md) değerlerine sahip nesne `tiled_index` şablon bağımsız değişkenleri `tiled_index` şablon bağımsız değişkenleri `_Dim0`, `_Dim1`, ve `_Dim2`.|  

  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `_Tiled_index_base`  
  
 `tiled_index`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** amp.h  
  
 **Namespace:** eşzamanlılık  


## <a name="tiled_index__ctor"></a>  tiled_index Oluşturucusu  
Yeni bir örneğini başlatır `tiled_index` sınıfı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
tiled_index(  
    const index<rank>& _Global,  
    const index<rank>& _Local,  
    const index<rank>& _Tile,  
    const index<rank>& _Tile_origin,  
    const tile_barrier& _Barrier ) restrict(amp,cpu);  
  
tiled_index(  
    const tiled_index& _Other ) restrict(amp,cpu);  
```  
  
#### <a name="parameters"></a>Parametreler  
*Sadece _global*<br/>
Genel [dizin](index-class.md) oluşturulmuş `tiled_index`.  
  
*_Yerel*<br/>
Yerel [dizin](index-class.md) oluşturulmuş `tiled_index`  
  
*_Tile*<br/>
Kutucuk [dizin](index-class.md) oluşturulmuş `tiled_index`  
  
*_Tile_origin*<br/>
Döşeme kaynağı [dizin](index-class.md) oluşturulmuş `tiled_index`  
  
*_Barrier*<br/>
[Tile_barrier](tile-barrier-class.md) oluşturulmuş nesne `tiled_index`.  
  
*_Diğer*<br/>
`tile_index` Kopyalanacak nesne için oluşturulmuş `tiled_index`.  
  
## <a name="overloads"></a>Aşırı Yüklemeler  
  
|||  
|-|-|  
|Ad|Açıklama|  
|`tiled_index(const index<rank>& _Global, const index<rank>& _Local, const index<rank>& _Tile, const index<rank>& _Tile_origin, const tile_barrier& _Barrier restrict(amp,cpu);`|Yeni bir örneğini başlatır `tile_index` dizini bir sınıftan genel koordinatlardaki döşeme ve de yerel koordinatlardaki döşeme görece pozisyondan. `_Global` Ve `_Tile_origin` parametreleri hesaplanır.|  
|`tiled_index(    const tiled_index& _Other) restrict(amp,cpu);`|Yeni bir örneğini başlatır `tile_index` sınıfı belirtilen kopyalayarak `tiled_index` nesne.|  


## <a name="tiled_index__get_tile_extent"></a>  get_tile_extent
Döndürür bir [uzantı](extent-class.md) değerlerine sahip nesne `tiled_index` şablon bağımsız değişkenleri `_Dim0`, `_Dim1`, ve `_Dim2`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
extent<rank> get_tile_extent()restrict(amp,cpu);  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bir `extent` değerlerine sahip nesne `tiled_index` şablon bağımsız değişkenleri `_Dim0`, `_Dim1`, ve `_Dim2`.  

## <a name="tiled_index__barrier"></a>  Engel   
Depoları bir [tile_barrier](tile-barrier-class.md) geçerli iş parçacığı döşemesindeki bir engeli temsil eden nesne.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
const tile_barrier barrier;  
```  

## <a name="tiled_index__global"></a>  Genel   
Depoları bir [dizin](index-class.md) nesne büyüm bir nesnenin genel dizinini temsil eden 1, 2 veya 3.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
const index<rank> global;  
```  
  
## <a name="tiled_index__local"></a>  Yerel   
Depoları bir [dizin](index-class.md) nesnesinin varolan döşeme dizine göreli temsil eden 1, 2 veya 3 dereceli bir [tiled_extent](tiled-extent-class.md) nesne.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
const index<rank> local;  
```  
  
## <a name="tiled_index__rank"></a>  boyut sayısı   
Boyut sayısını tutar `tiled_index` nesne.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
static const int rank = _Rank;  
```  

## <a name="tiled_index__tile"></a>  kutucuğu   
Depoları bir [dizin](index-class.md) nesnesinin boyut sayısı 1, 2 veya 3 varolan döşeme koordinatlarını temsil eden bir [tiled_extent](tiled-extent-class.md) nesne.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
const index<rank> tile;  
```  
  
## <a name="tiled_index__tile_dim0"></a>  tile_dim0  
En önemli boyutun uzunluğunu saklar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
static const int tile_dim0 = _Dim0;  
```  
   
## <a name="tiled_index__tile_dim1"></a>  tile_dim1   
Sonraki en-önemli boyutun uzunluğunu saklar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
static const int tile_dim1 = _Dim1;  
```  
## <a name="tiled_index__tile_dim2"></a>  tile_dim2   
En az önemli boyutun uzunluğunu saklar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
static const int tile_dim2 = _Dim2;  
```  
## <a name="tiled_index__tile_origin"></a>  tile_origin   
Depoları bir [dizin](index-class.md) döşeme genel temsil eden 1, 2 veya 3 dereceli koordinatlarını nesnesinin bir [tiled_extent](tiled-extent-class.md) nesne.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
const index<rank> tile_origin  
```  
## <a name="tile_extent"></a>  tile_extent
  Alır bir [uzantı](extent-class.md) değerlerine sahip nesne `tiled_index` şablon bağımsız değişkenleri `tiled_index` şablon bağımsız değişkenleri `_Dim0`, `_Dim1`, ve `_Dim2`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
__declspec(property(get= get_tile_extent)) extent<rank> tile_extent;  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Ad Alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)
