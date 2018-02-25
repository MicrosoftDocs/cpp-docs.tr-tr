---
title: "max_unbounded sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- allocators/stdext::max_unbounded
- allocators/stdext::max_unbounded::allocated
- allocators/stdext::max_unbounded::deallocated
- allocators/stdext::max_unbounded::full
- allocators/stdext::max_unbounded::released
- allocators/stdext::max_unbounded::saved
dev_langs:
- C++
helpviewer_keywords:
- stdext::max_unbounded
- stdext::max_unbounded [C++], allocated
- stdext::max_unbounded [C++], deallocated
- stdext::max_unbounded [C++], full
- stdext::max_unbounded [C++], released
- stdext::max_unbounded [C++], saved
ms.assetid: e34627a9-c231-4031-a483-cbb0514fff46
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 96a4d8a295353f56f2c6b027f72e6353698afdf2
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="maxunbounded-class"></a>max_unbounded Sınıfı
Açıklayan bir [max sınıfı](../standard-library/allocators-header.md) en büyük uzunluğu sınırlamaz nesne bir [freelist](../standard-library/freelist-class.md) nesne.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class max_unbounded
```  
  
### <a name="member-functions"></a>Üye İşlevleri  
  
|||  
|-|-|  
|[Ayrılmış](#allocated)|Ayrılmış bellek blokları sayısını artırır.|  
|[Serbest bırakıldı](#deallocated)|Azaltır sayısı bellek blokları ayrılmış.|  
|[tam](#full)|Daha fazla bellek blokları ücretsiz listesine eklenmesi gerekip gerekmediğini belirten bir değer döndürür.|  
|[released](#released)|Boş listede bellek sayısı engeller azaltır.|  
|[kaydedildi](#saved)|Bellek blokları ücretsiz listesinde sayısını artırır.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<allocators >  
  
 **Namespace:** stdext  
  
##  <a name="allocated"></a>  max_unbounded::allocated  
 Ayrılmış bellek blokları sayısını artırır.  
  
```
void allocated(std::size_t _Nx = 1);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`_Nx`|Artış değeri.|  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi hiçbir şey yapmaz. Her başarılı çağrısı tarafından sonra adlı `cache_freelist::allocate` işleci `new`. Bağımsız değişken `_Nx` operatör tarafından ayrılan Öbek bellek bloğu sayısıdır `new`.  
  
##  <a name="deallocated"></a>  max_unbounded::deallocated  
 Azaltır sayısı bellek blokları ayrılmış.  
  
```
void deallocated(std::size_t _Nx = 1);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`_Nx`|Artış değeri.|  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini hiçbir şey yapmaz. Her çağırdıktan sonra bu üye işlev çağrılır `cache_freelist::deallocate` işleci `delete`. Bağımsız değişken `_Nx` işleciyle serbest Öbek bellek bloğu sayısıdır `delete`.  
  
##  <a name="full"></a>  max_unbounded::full  
 Daha fazla bellek blokları ücretsiz listesine eklenmesi gerekip gerekmediğini belirten bir değer döndürür.  
  
```
bool full();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Üye işlev her zaman döndürür `false`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye fonksiyonu tarafından çağrılır `cache_freelist::deallocate`. Çağrı döndürmesi durumunda `true`, `deallocate` false değerini döndürürse, bellek bloğu boş liste; koyar `deallocate` çağrıları işleci `delete` ayırması için blok.  
  
##  <a name="released"></a>  max_unbounded::released  
 Boş listede bellek sayısı engeller azaltır.  
  
```
void released();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi hiçbir şey yapmaz. `released` Geçerli max sınıfının üye işlevi tarafından çağrılır `cache_freelist::allocate` olduğunda, bir bellek bloğu boş listeden kaldırır.  
  
##  <a name="saved"></a>  max_unbounded::saved  
 Bellek blokları ücretsiz listesinde sayısını artırır.  
  
```
void saved();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi hiçbir şey yapmaz. Çağrılır `cache_freelist::deallocate` zaman onu koyar bir bellek bloğu boş liste.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<allocators >](../standard-library/allocators-header.md)



