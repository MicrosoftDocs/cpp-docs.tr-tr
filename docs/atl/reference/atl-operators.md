---
title: "ATL işleçleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: 'index-page '
dev_langs: C++
helpviewer_keywords: operators [ATL]
ms.assetid: 58ccd252-2869-45ee-8a5c-3ca40ee7f8a2
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 46bc674a65e2ffc946a4806ce1440fec6e14c355
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="atl-operators"></a>ATL işleçleri
Bu bölüm için ATL genel işleçler başvuru konuları içerir.  
  
|İşleç|Açıklama|  
|--------------|-----------------|  
|[operator ==](#operator_eq_eq)|İki karşılaştırır `CSid` nesneleri veya `SID` yapıları eşitlik için.|  
|[operator! =](#operator_neq)|İki karşılaştırır `CSid` nesneleri veya `SID` eşitsizlik yapılarında.|  
|[operator <](#operator_lt)|Varsa testleri `CSid` nesne veya `SID` yapısı işlecinin sol tarafındaki küçük `CSid` nesne veya `SID` yapısı (C++ Standart Kitaplığı uyumluluk için) sağ taraftaki.|  
|[operator >](#operator_gt)|Varsa testleri `CSid` nesne veya `SID` işlecinin sol tarafındaki yapısıdır büyük `CSid` nesne veya `SID` yapısı (C++ Standart Kitaplığı uyumluluk için) sağ taraftaki.|  
|[operator < =](#operator_lt__eq)|Varsa testleri `CSid` nesne veya `SID` işlecinin sol tarafındaki yapısıdır küçük veya eşit `CSid` nesne veya `SID` yapısı (C++ Standart Kitaplığı uyumluluk için) sağ taraftaki.|  
|[operator > =](#operator_gt__eq)|Varsa testleri `CSid` nesne veya `SID` işlecinin sol tarafındaki yapısıdır değerinden büyük veya eşit `CSid` nesne veya `SID` yapısı (C++ Standart Kitaplığı uyumluluk için) sağ taraftaki.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlsecurity.h.  
  
##  <a name="operator_eq_eq"></a>operator ==  
 Karşılaştırır `CSid` nesneleri veya `SID` (güvenlik tanımlayıcısı) yapıları eşitlik için.  
  
```   
bool operator==(const CSid& lhs, const CSid& rhs) throw(); 
```  
  
### <a name="parameters"></a>Parametreler  
 `lhs`  
 İlk `CSid` nesne veya `SID` Karşılaştırılacak yapısı.  
  
 `rhs`  
 İkinci `CSid` nesne veya `SID` Karşılaştırılacak yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **true** nesneleri eşitse, **false** eşit değillerse.  
  
##  <a name="operator_neq"></a>operator! =  
 Karşılaştırır `CSid` nesneleri veya `SID` eşitsizlik yapılarında (güvenlik tanımlayıcısı).  
  
```   
bool operator==(const CSid& lhs, const CSid& rhs) throw(); 
```  
  
### <a name="parameters"></a>Parametreler  
 `lhs`  
 İlk `CSid` nesne veya `SID` Karşılaştırılacak yapısı.  
  
 `rhs`  
 İkinci `CSid` nesne veya `SID` Karşılaştırılacak yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **true** nesneleri eşit değilse **false** eşit olup olmadıkları.  
  
##  <a name="operator_lt"></a>operator <  
 Varsa testleri `CSid` nesne veya `SID` yapısı işlecinin sol tarafındaki küçük `CSid` nesne veya `SID` yapısı (C++ Standart Kitaplığı uyumluluk için) sağ taraftaki.  
  
```   
bool operator<(const CSid& lhs, const CSid& rhs) throw(); 
```  
  
### <a name="parameters"></a>Parametreler  
 `lhs`  
 İlk `CSid` nesne veya `SID` Karşılaştırılacak yapısı.  
  
 `rhs`  
 İkinci `CSid` nesne veya `SID` Karşılaştırılacak yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **true** varsa adresini `lhs` nesne adresini azdır `rhs` nesnesi **false** Aksi takdirde.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işleç adresini temel görevi gören `CSid` nesne veya `SID` yapısı ve C++ Standart Kitaplığı koleksiyon sınıfları uyum sağlamak için uygulanır.  
  
##  <a name="operator_gt"></a>operator >  
 Varsa testleri `CSid` nesne veya `SID` işlecinin sol tarafındaki yapısıdır büyük `CSid` nesne veya `SID` yapısı (C++ Standart Kitaplığı uyumluluk için) sağ taraftaki.  
  
```   
bool operator<(const CSid& lhs, const CSid& rhs) throw(); 
```  
  
### <a name="parameters"></a>Parametreler  
 `lhs`  
 İlk `CSid` nesne veya `SID` Karşılaştırılacak yapısı.  
  
 `rhs`  
 İkinci `CSid` nesne veya `SID` Karşılaştırılacak yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **true** varsa adresini `lhs` adresini büyük `rhs`, **false** Aksi takdirde.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işleç adresini temel görevi gören `CSid` nesne veya `SID` yapısı ve C++ Standart Kitaplığı koleksiyon sınıfları uyum sağlamak için uygulanır.  
  
##  <a name="operator_lt__eq"></a>operator < =  
 Varsa testleri `CSid` nesne veya `SID` işlecinin sol tarafındaki yapısıdır küçük veya eşit `CSid` nesne veya `SID` yapısı (C++ Standart Kitaplığı uyumluluk için) sağ taraftaki.  
  
```   
bool operator<(const CSid& lhs, const CSid& rhs) throw(); 
```  
  
### <a name="parameters"></a>Parametreler  
 `lhs`  
 İlk `CSid` nesne veya `SID` Karşılaştırılacak yapısı.  
  
 `rhs`  
 İkinci `CSid` nesne veya `SID` Karşılaştırılacak yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **true** varsa adresini `lhs` adresini küçük veya ona eşit `rhs`, **false** Aksi takdirde.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işleç adresini temel görevi gören `CSid` nesne veya `SID` yapısı ve C++ Standart Kitaplığı koleksiyon sınıfları uyum sağlamak için uygulanır.  
  
##  <a name="operator_gt__eq"></a>operator > =  
 Varsa testleri `CSid` nesne veya `SID` işlecinin sol tarafındaki yapısıdır değerinden büyük veya eşit `CSid` nesne veya `SID` yapısı (C++ Standart Kitaplığı uyumluluk için) sağ taraftaki.  
  
```   
bool operator<(const CSid& lhs, const CSid& rhs) throw(); 
```  
  
### <a name="parameters"></a>Parametreler  
 `lhs`  
 İlk `CSid` nesne veya `SID` Karşılaştırılacak yapısı.  
  
 `rhs`  
 İkinci `CSid` nesne veya `SID` Karşılaştırılacak yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **true** varsa adresini `lhs` büyük veya eşit adresine `rhs`, **false** Aksi takdirde.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işleç adresini temel görevi gören `CSid` nesne veya `SID` yapısı ve C++ Standart Kitaplığı koleksiyon sınıfları uyum sağlamak için uygulanır.



