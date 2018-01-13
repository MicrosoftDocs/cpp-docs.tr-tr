---
title: "max_none sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- allocators/stdext::max_none
- allocators/stdext::max_none::allocated
- allocators/stdext::max_none::deallocated
- allocators/stdext::max_none::full
- allocators/stdext::max_none::released
- allocators/stdext::max_none::saved
dev_langs: C++
helpviewer_keywords:
- stdext::max_none
- stdext::max_none [C++], allocated
- stdext::max_none [C++], deallocated
- stdext::max_none [C++], full
- stdext::max_none [C++], released
- stdext::max_none [C++], saved
ms.assetid: 12ab5376-412e-479c-86dc-2c3d6a3559b6
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f7db35adf828d66ecf9b6474e45960d22466b444
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="maxnone-class"></a>max_none Sınıfı
Açıklayan bir [max sınıfı](../standard-library/allocators-header.md) sınırlar nesne bir [freelist](../standard-library/freelist-class.md) sıfır en fazla nesneye.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <std::size_t Max>  
class max_none
```  
  
#### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`Max`|Depolamak öğelerinin üst limiti belirler max sınıfı `freelist`.|  
  
### <a name="member-functions"></a>Üye İşlevleri  
  
|||  
|-|-|  
|[ayrılmış](#allocated)|Ayrılmış bellek blokları sayısını artırır.|  
|[Serbest bırakıldı](#deallocated)|Azaltır sayısı bellek blokları ayrılmış.|  
|[tam](#full)|Daha fazla bellek blokları ücretsiz listesine eklenmesi gerekip gerekmediğini belirten bir değer döndürür.|  
|[yayımlanma tarihi](#released)|Boş listede bellek sayısı engeller azaltır.|  
|[kaydedildi](#saved)|Bellek blokları ücretsiz listesinde sayısını artırır.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<allocators >  
  
 **Namespace:** stdext  
  
##  <a name="allocated"></a>max_none::allocated  
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
  
##  <a name="deallocated"></a>max_none::deallocated  
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
  
##  <a name="full"></a>max_none::Full  
 Daha fazla bellek blokları ücretsiz listesine eklenmesi gerekip gerekmediğini belirten bir değer döndürür.  
  
```
bool full();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu üye işlevi her zaman döndürür `true`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye fonksiyonu tarafından çağrılır `cache_freelist::deallocate`. Çağrı döndürmesi durumunda `true`, `deallocate` false değerini döndürürse, bellek bloğu boş liste; koyar `deallocate` çağrıları işleci `delete` ayırması için blok.  
  
##  <a name="released"></a>max_none::RELEASED  
 Boş listede bellek sayısı engeller azaltır.  
  
```
void released();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi hiçbir şey yapmaz. `released` Geçerli max sınıfının üye işlevi tarafından çağrılır `cache_freelist::allocate` olduğunda, bir bellek bloğu boş listeden kaldırır.  
  
##  <a name="saved"></a>max_none::Saved  
 Bellek blokları ücretsiz listesinde sayısını artırır.  
  
```
void saved();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi hiçbir şey yapmaz. Çağrılır `cache_freelist::deallocate` zaman onu koyar bir bellek bloğu boş liste.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<allocators >](../standard-library/allocators-header.md)



