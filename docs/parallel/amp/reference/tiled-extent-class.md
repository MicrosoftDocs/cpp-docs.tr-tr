---
title: "tiled_extent sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- tiled_extent
- AMP/tiled_extent
- AMP/Concurrency::tiled_extent::tiled_extent
- AMP/Concurrency::tiled_extent::get_tile_extent
- AMP/Concurrency::tiled_extent::pad
- AMP/Concurrency::tiled_extent::truncate
- AMP/Concurrency::tiled_extent::tile_dim0
- AMP/Concurrency::tiled_extent::tile_dim1
- AMP/Concurrency::tiled_extent::tile_dim2
- AMP/Concurrency::tiled_extent::tile_extent
dev_langs: C++
ms.assetid: 671ecaf8-c7b0-4ac8-bbdc-e30bd92da7c0
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a73a29a7cdcd20c969680e1dbb69b6a6ede4dbb6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="tiledextent-class"></a>tiled_extent Sınıfı
A `tiled_extent` nesne bir `extent` kapsamı alan bir, iki veya üç boyutlu döşeme subdivides nesne bir ile üç boyut.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
template <
    int _Dim0,  
    int _Dim1,  
    int _Dim2  
>  
class tiled_extent : public Concurrency::extent<3>;  
 
template <
    int _Dim0,  
    int _Dim1  
>  
class tiled_extent<_Dim0, _Dim1, 0> : public Concurrency::extent<2>;  
 
template <
    int _Dim0  
>  
class tiled_extent<_Dim0, 0, 0> : public Concurrency::extent<1>;  
```  
  
### <a name="parameters"></a>Parametreler  
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
|[tiled_extent Oluşturucusu](#ctor)|Yeni bir örneğini başlatır `tiled_extent` sınıfı.|  

  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[get_tile_extent](#get_tile_extent)|Döndürür bir `extent` değerlerini yakalar nesne `tiled_extent` bağımsız şablon `_Dim0`, `_Dim1`, ve `_Dim2`.|  
|[paneli](#pad)|Yeni bir döndürür `tiled_extent` kapsam nesnesiyle göre ayarlanmış yukarı döşeme boyutlara göre tam bölünebilir olmalıdır.|  
|[kesme](#truncate)|Yeni bir döndürür `tiled_extent` kapsam nesnesiyle göre ayarlanmış aşağı döşeme boyutlara göre tam bölünebilir olmalıdır.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[işleç =](#operator_eq)|Belirtilen içeriğini kopyalar `tiled_index` bunu nesnesine.|  

  
### <a name="public-constants"></a>Genel sabitler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[tile_dim0 sabiti](#tile_dim0)|En önemli boyutun uzunluğu depolar.|  
|[tile_dim1 sabiti](#tile_dim1)|Sonraki en önemli boyutun uzunluğu depolar.|  
|[tile_dim2 sabiti](#tile_dim2)|En az önemli boyutun uzunluğu depolar.|  

  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[tile_extent](#tile_extent)|Alır bir `extent` değerlerini yakalar nesne `tiled_extent` bağımsız şablon `_Dim0`, `_Dim1`, ve `_Dim2`.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `extent`  
  
 `tiled_extent`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** amp.h  
  
 **Namespace:** eşzamanlılık  

## <a name="ctor"></a> tiled_extent Oluşturucusu  
Yeni bir örneğini başlatır `tiled_extent` sınıfı.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
tiled_extent();  
  
tiled_extent(  
    const Concurrency::extent<rank>& _Other );  
  
tiled_extent(  
    const tiled_extent& _Other );  
```  
  
### <a name="parameters"></a>Parametreler  
 `_Other`  
 `extent` Veya `tiled_extent` kopyalamak için nesne.  
  

  

## <a name="get_tile_extent"></a> get_tile_extent   
Döndürür bir `extent` değerlerini yakalar nesne `tiled_extent` bağımsız şablon `_Dim0`, `_Dim1`, ve `_Dim2`.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
Concurrency::extent<rank> get_tile_extent() const restrict(amp,cpu);  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir `extent` bu boyutlarını yakalar nesne `tiled_extent` örneği.  
  

## <a name="pad"></a> paneli   
Yeni bir döndürür `tiled_extent` kapsam nesnesiyle göre ayarlanmış yukarı döşeme boyutlara göre tam bölünebilir olmalıdır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
tiled_extent pad() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeni `tiled_extent` nesnesiyle değeri. 
## <a name="truncate"></a> kesme   
Yeni bir döndürür `tiled_extent` kapsam nesnesiyle göre ayarlanmış aşağı döşeme boyutlara göre tam bölünebilir olmalıdır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
tiled_extent truncate() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeni bir döndürür `tiled_extent` kapsam nesnesiyle göre ayarlanmış aşağı döşeme boyutlara göre tam bölünebilir olmalıdır.  

## <a name="operator_eq"></a> işleç =   
Belirtilen içeriğini kopyalar `tiled_index` bunu nesnesine.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
tiled_extent&  operator= (  
    const tiled_extent& _Other ) restrict (amp, cpu);  
```  
  
### <a name="parameters"></a>Parametreler  
 `_Other`  
 `tiled_index` Kopyalanacak nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu başvuru `tiled_index` örneği.  

## <a name="tile_dim0"></a> tile_dim0   
En önemli boyutun uzunluğu depolar.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
static const int tile_dim0 = _Dim0;  
```  
  
## <a name="tile_dim1"></a> tile_dim1   
Sonraki en önemli boyutun uzunluğu depolar.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
static const int tile_dim1 = _Dim1;  
```  
## <a name="tile_dim2"></a> tile_dim2   
En az önemli boyutun uzunluğu depolar.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
static const int tile_dim2 = _Dim2;  
```  
## <a name="tile_extent"></a> tile_extent   
  Alır bir `extent` değerlerini yakalar nesne `tiled_extent` bağımsız şablon `_Dim0`, `_Dim1`, ve `_Dim2`.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
__declspec(property(get= get_tile_extent)) Concurrency::extent<rank> tile_extent;  
```  
  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace (C++ AMP)](concurrency-namespace-cpp-amp.md)
