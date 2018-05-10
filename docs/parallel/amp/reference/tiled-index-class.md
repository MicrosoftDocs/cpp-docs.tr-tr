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
ms.openlocfilehash: fd28ab01d0d4180cc518cff230eb7df8261f4940
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="tiledindex-class"></a>tiled_index Sınıfı
Bir dizine sağlayan bir [tiled_extent](tiled-extent-class.md) nesnesi. Bu sınıf öğeleri yerel bölmesi kaynağa göreli ve genel kaynağa göreli erişmek için özellikler vardır. Döşeli alanları hakkında daha fazla bilgi için bkz: [kullanarak döşeme](../../../parallel/amp/using-tiles.md).  
  
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
 `_Dim0`  
 En önemli boyutun uzunluğu.  
  
 `_Dim1`  
 Sonraki en önemli boyutun uzunluğu.  
  
 `_Dim2`  
 En az önemli boyutun uzunluğu.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[tiled_index Oluşturucusu](#ctor)|Yeni bir örneğini başlatır `tile_index` sınıfı.|  

  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[get_tile_extent](#tiled_index__get_tile_extent)|Döndürür bir [ölçüde](extent-class.md) değerleri olan nesneyi `tiled_index` bağımsız şablon `_Dim0`, `_Dim1`, ve `_Dim2`.|  


  
### <a name="public-constants"></a>Genel sabitler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[engel sabiti](#tiled_index__barrier)|Depoları bir [tile_barrier](tile-barrier-class.md) iş parçacıklarının geçerli kutucuğunda bir engel temsil eden nesne.|  
|||  
|[Genel sabiti](#tiled_index__global)|Depoları bir [dizin](index-class.md) genel temsil eden derece 1, 2 veya 3 dizinde nesnesinin bir [kılavuz](http://msdn.microsoft.com/en-us/f7d1b6a6-586c-4345-b09a-bfc26c492cb0) nesnesi.|  
|[Yerel sabiti](#tiled_index__local)|Depoları bir `index` geçerli parçasına göreli temsil eden derece 1, 2 veya 3 dizinde nesnesinin bir [tiled_extent](tiled-extent-class.md) nesnesi.|  
|[sıra sabiti](#tiled_index__rank)|Derecesini depolar `tiled_index` nesnesi.|  
|[tile sabiti](#tiled_index__tile)|Depoları bir `index` derece 1, 2 veya geçerli parçasına koordinatlarını temsil eden 3 nesnesinin bir `tiled_extent` nesnesi.|  
|[tile_dim0 sabiti](#tiled_index__tile_dim0)|En önemli boyutun uzunluğu depolar.|  
|[tile_dim1 sabiti](#tiled_index__tile_dim1)|Sonraki en önemli boyutun uzunluğu depolar.|  
|[tile_dim2 sabiti](#tiled_index__tile_dim2)|En az önemli boyutun uzunluğu depolar.|  
|[tile_origin sabiti](#tiled_index__tile_origin)|Depoları bir `index` geçerli parçasında kökeni genel temsil eden derece 1, 2 veya 3 koordinatları nesnesinin bir `tiled_extent` nesnesi.|  

  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[tile_extent](#tile_extent)|Alır bir [ölçüde](extent-class.md) değerleri olan nesneyi `tiled_index` bağımsız şablon `tiled_index` bağımsız şablon `_Dim0`, `_Dim1`, ve `_Dim2`.|  

  
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
 `_Global`  
 Genel [dizin](index-class.md) oluşturulan, `tiled_index`.  
  
 `_Local`  
 Yerel [dizin](index-class.md) oluşturulan, `tiled_index`  
  
 `_Tile`  
 Döşeme [dizin](index-class.md) oluşturulan, `tiled_index`  
  
 `_Tile_origin`  
 Döşeme kaynak [dizin](index-class.md) oluşturulan, `tiled_index`  
  
 `_Barrier`  
 [Tile_barrier](tile-barrier-class.md) oluşturulan nesnesinin `tiled_index`.  
  
 `_Other`  
 `tile_index` Kopyalanacak nesne için oluşturulan `tiled_index`.  
  
## <a name="overloads"></a>Aşırı Yüklemeler  
  
|||  
|-|-|  
|Ad|Açıklama|  
|`tiled_index(const index<rank>& _Global, const index<rank>& _Local, const index<rank>& _Tile, const index<rank>& _Tile_origin, const tile_barrier& _Barrier restrict(amp,cpu);`|Yeni bir örneğini başlatır `tile_index` genel koordinatlarına parçasında ve yerel koordinatları parçasında göreli konumda dizinden sınıfı. `_Global` Ve `_Tile_origin` parametreleri hesaplanır.|  
|`tiled_index(    const tiled_index& _Other) restrict(amp,cpu);`|Yeni bir örneğini başlatır `tile_index` belirtilen kopyalayarak sınıfı `tiled_index` nesnesi.|  


## <a name="tiled_index__get_tile_extent"></a>  get_tile_extent
Döndürür bir [ölçüde](extent-class.md) değerleri olan nesneyi `tiled_index` bağımsız şablon `_Dim0`, `_Dim1`, ve `_Dim2`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
extent<rank> get_tile_extent()restrict(amp,cpu);  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bir `extent` değerleri olan nesneyi `tiled_index` bağımsız şablon `_Dim0`, `_Dim1`, ve `_Dim2`.  

## <a name="tiled_index__barrier"></a>  engelle   
Depoları bir [tile_barrier](tile-barrier-class.md) iş parçacıklarının geçerli kutucuğunda bir engel temsil eden nesne.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
const tile_barrier barrier;  
```  

## <a name="tiled_index__global"></a>  Genel   
Depoları bir [dizin](index-class.md) nesne bir nesne genel dizinini temsil eden derece 1, 2 veya 3.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
const index<rank> global;  
```  
  
## <a name="tiled_index__local"></a>  Yerel   
Depoları bir [dizin](index-class.md) geçerli parçasına göreli temsil eden derece 1, 2 veya 3 dizinde nesnesinin bir [tiled_extent](tiled-extent-class.md) nesnesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
const index<rank> local;  
```  
  
## <a name="tiled_index__rank"></a>  RANK   
Derecesini depolar `tiled_index` nesnesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
static const int rank = _Rank;  
```  

## <a name="tiled_index__tile"></a>  Döşeme   
Depoları bir [dizin](index-class.md) derece 1, 2 veya geçerli parçasına koordinatlarını temsil eden 3 nesnesinin bir [tiled_extent](tiled-extent-class.md) nesnesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
const index<rank> tile;  
```  
  
## <a name="tiled_index__tile_dim0"></a>  tile_dim0  
En önemli boyutun uzunluğu depolar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
static const int tile_dim0 = _Dim0;  
```  
   
## <a name="tiled_index__tile_dim1"></a>  tile_dim1   
Sonraki en önemli boyutun uzunluğu depolar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
static const int tile_dim1 = _Dim1;  
```  
## <a name="tiled_index__tile_dim2"></a>  tile_dim2   
En az önemli boyutun uzunluğu depolar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
static const int tile_dim2 = _Dim2;  
```  
## <a name="tiled_index__tile_origin"></a>  tile_origin   
Depoları bir [dizin](index-class.md) içinde geçerli döşeme kökeni genel temsil eden derece 1, 2 veya 3 koordinatları nesnesinin bir [tiled_extent](tiled-extent-class.md) nesnesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
const index<rank> tile_origin  
```  
## <a name="tile_extent"></a>  tile_extent
  Alır bir [ölçüde](extent-class.md) değerleri olan nesneyi `tiled_index` bağımsız şablon `tiled_index` bağımsız şablon `_Dim0`, `_Dim1`, ve `_Dim2`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
__declspec(property(get= get_tile_extent)) extent<rank> tile_extent;  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Ad Alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)
