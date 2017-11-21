---
title: "max_variable_size sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- allocators/stdext::max_variable_size
- allocators/stdext::max_variable_size::allocated
- allocators/stdext::max_variable_size::deallocated
- allocators/stdext::max_variable_size::full
- allocators/stdext::max_variable_size::released
- allocators/stdext::max_variable_size::saved
dev_langs: C++
helpviewer_keywords:
- stdext::max_variable_size
- stdext::max_variable_size [C++], allocated
- stdext::max_variable_size [C++], deallocated
- stdext::max_variable_size [C++], full
- stdext::max_variable_size [C++], released
- stdext::max_variable_size [C++], saved
ms.assetid: 9f2e9df0-4148-4b37-bc30-f8eca0ef86ae
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 425a93ff12aad138ff2c539765f9afeeb2f22756
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="maxvariablesize-class"></a>max_variable_size Sınıfı
Açıklayan bir [max sınıfı](../standard-library/allocators-header.md) sınırlar nesnesi bir [freelist](../standard-library/freelist-class.md) nesne sayısı için kabaca orantılıdır bir maksimum uzunluğu için ayrılan bellek blokları.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class max_variable_size
```  
  
### <a name="constructors"></a>Oluşturucular  
  
|||  
|-|-|  
|[max_variable_size](#max_variable_size)|Türünde bir nesne oluşturur `max_variable_size`.|  
  
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
  
##  <a name="allocated"></a>max_variable_size::allocated  
 Ayrılmış bellek blokları sayısını artırır.  
  
```
void allocated(std::size_t _Nx = 1);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`_Nx`|Artış değeri.|  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye fonksiyonu ekler `_Nx` için depolanan değere `_Nallocs`. Bu üye işlev her başarılı çağrısı tarafından sonra çağrılır `cache_freelist::allocate` işleci `new`. Bağımsız değişken `_Nx` operatör tarafından ayrılan Öbek bellek bloğu sayısıdır `new`.  
  
##  <a name="deallocated"></a>max_variable_size::deallocated  
 Azaltır sayısı bellek blokları ayrılmış.  
  
```
void deallocated(std::size_t _Nx = 1);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`_Nx`|Artış değeri.|  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini çıkarır `_Nx` saklı değerinden `_Nallocs`. Her çağırdıktan sonra bu üye işlev çağrılır `cache_freelist::deallocate` işleci `delete`. Bağımsız değişken `_Nx` işleciyle serbest Öbek bellek bloğu sayısıdır `delete`.  
  
##  <a name="full"></a>max_variable_size::Full  
 Daha fazla bellek blokları ücretsiz listesine eklenmesi gerekip gerekmediğini belirten bir değer döndürür.  
  
```
bool full();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`varsa `_Nallocs / 16 + 16 <= _Nblocks`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye fonksiyonu tarafından çağrılır `cache_freelist::deallocate`. Çağrı döndürmesi durumunda `true`, `deallocate` false değerini döndürürse, bellek bloğu boş liste; koyar `deallocate` çağrıları işleci `delete` ayırması için blok.  
  
##  <a name="max_variable_size"></a>max_variable_size::max_variable_size  
 Türünde bir nesne oluşturur `max_variable_size`.  
  
```
max_variable_size();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturucu depolanan değerlerin başlatır `_Nblocks` ve `_Nallocs` sıfır.  
  
##  <a name="released"></a>max_variable_size::RELEASED  
 Boş listede bellek sayısı engeller azaltır.  
  
```
void released();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlev azaltır depolanan değer `_Nblocks`. `released` Geçerli max sınıfının üye işlevi tarafından çağrılır `cache_freelist::allocate` olduğunda, bir bellek bloğu boş listeden kaldırır.  
  
##  <a name="saved"></a>max_variable_size::Saved  
 Bellek blokları ücretsiz listesinde sayısını artırır.  
  
```
void saved();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi depolanan değer artırır `_Nblocks`. Bu üye fonksiyonu tarafından çağrılır `cache_freelist::deallocate` zaman onu koyar bir bellek bloğu boş liste.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<allocators >](../standard-library/allocators-header.md)



