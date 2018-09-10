---
title: ATL işleçler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- operators [ATL]
ms.assetid: 58ccd252-2869-45ee-8a5c-3ca40ee7f8a2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8f5027fa4b84d84bf07766c7ac4e75f140706f0c
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44103716"
---
# <a name="atl-operators"></a>ATL işleçleri

Bu bölümde, ATL genel işleçler için başvuru konuları içerir.

|İşleç|Açıklama|
|--------------|-----------------|
|[işleç ==](#operator_eq_eq)|İki karşılaştırır `CSid` nesneleri veya `SID` yapıları eşitlik için.|
|[işleç! =](#operator_neq)|İki karşılaştırır `CSid` nesneleri veya `SID` yapıları eşitsizlik için.|
|[işleç <](#operator_lt)|Olmadığını test eder `CSid` nesne veya `SID` yapısı işlecinin sol tarafındaki küçüktür `CSid` nesne veya `SID` yapısı (Standart C++ Kitaplığı uyumluluğu için) sağ taraftaki.|
|[operator >](#operator_gt)|Olmadığını test eder `CSid` nesne veya `SID` yapısı işlecinin sol tarafındaki büyük `CSid` nesne veya `SID` yapısı işlecin sağ tarafındaki (C++ Standart Kitaplığı uyumluluk için).|
|[operator < =](#operator_lt__eq)|Olmadığını test eder `CSid` nesne veya `SID` işlecinin sol tarafındaki yapısı, küçük veya buna eşit `CSid` nesne veya `SID` yapısı (Standart C++ Kitaplığı uyumluluğu için) sağ taraftaki.|
|[operator > =](#operator_gt__eq)|Olmadığını test eder `CSid` nesne veya `SID` işlecinin sol tarafındaki yapısı büyüktür veya eşittir `CSid` nesne veya `SID` yapısı işlecin sağ tarafındaki (C++ Standart Kitaplığı uyumluluk için).|

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlsecurity.h.

##  <a name="operator_eq_eq"></a>  işleç ==

Karşılaştırır `CSid` nesneleri veya `SID` eşitlik için yapılar (güvenlik tanımlayıcısı).

```   
bool operator==(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>Parametreler

*lhs*  
İlk `CSid` nesne veya `SID` Karşılaştırılacak yapısı.

*Sol*  
İkinci `CSid` nesne veya `SID` Karşılaştırılacak yapısı.

### <a name="return-value"></a>Dönüş Değeri

DOĞRU eşit değilse, nesneleri yanlış eşit olup olmadığını döndürür.

##  <a name="operator_neq"></a>  işleç! =

Karşılaştırır `CSid` nesneleri veya `SID` eşitsizlik için yapılar (güvenlik tanımlayıcısı).

```   
bool operator==(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>Parametreler

*lhs*  
İlk `CSid` nesne veya `SID` Karşılaştırılacak yapısı.

*Sol*  
İkinci `CSid` nesne veya `SID` Karşılaştırılacak yapısı.

### <a name="return-value"></a>Dönüş Değeri

DOĞRU nesneleri değil, eşittir, eşitlerse FALSE döndürür.

##  <a name="operator_lt"></a>  işleç <

Olmadığını test eder `CSid` nesne veya `SID` yapısı işlecinin sol tarafındaki küçüktür `CSid` nesne veya `SID` yapısı (Standart C++ Kitaplığı uyumluluğu için) sağ taraftaki.

```   
bool operator<(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>Parametreler

*lhs*  
İlk `CSid` nesne veya `SID` Karşılaştırılacak yapısı.

*Sol*  
İkinci `CSid` nesne veya `SID` Karşılaştırılacak yapısı.

### <a name="return-value"></a>Dönüş Değeri

Gerekirse TRUE döndürür adresini *lhs* nesnenin adresini azdır *sol* , yanlış aksi nesne.

### <a name="remarks"></a>Açıklamalar

Bu işlecin adresini davranır `CSid` nesne veya `SID` yapısı ve C++ Standart Kitaplığı koleksiyon sınıfları ile uyumluluk sağlamak için kullanılır.

##  <a name="operator_gt"></a>  operator >

Olmadığını test eder `CSid` nesne veya `SID` yapısı işlecinin sol tarafındaki büyük `CSid` nesne veya `SID` yapısı işlecin sağ tarafındaki (C++ Standart Kitaplığı uyumluluk için).

```   
bool operator<(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>Parametreler

*lhs*  
İlk `CSid` nesne veya `SID` Karşılaştırılacak yapısı.

*Sol*  
İkinci `CSid` nesne veya `SID` Karşılaştırılacak yapısı.

### <a name="return-value"></a>Dönüş Değeri

Gerekirse TRUE döndürür adresini *lhs* adresini büyükse *sol*false Aksi takdirde.

### <a name="remarks"></a>Açıklamalar

Bu işlecin adresini davranır `CSid` nesne veya `SID` yapısı ve C++ Standart Kitaplığı koleksiyon sınıfları ile uyumluluk sağlamak için kullanılır.

##  <a name="operator_lt__eq"></a>  operator < =

Olmadığını test eder `CSid` nesne veya `SID` işlecinin sol tarafındaki yapısı, küçük veya buna eşit `CSid` nesne veya `SID` yapısı (Standart C++ Kitaplığı uyumluluğu için) sağ taraftaki.

```   
bool operator<(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>Parametreler

*lhs*  
İlk `CSid` nesne veya `SID` Karşılaştırılacak yapısı.

*Sol*  
İkinci `CSid` nesne veya `SID` Karşılaştırılacak yapısı.

### <a name="return-value"></a>Dönüş Değeri

Gerekirse TRUE döndürür adresini *lhs* adresini küçük veya ona eşit *sol*FALSE, aksi takdirde.

### <a name="remarks"></a>Açıklamalar

Bu işlecin adresini davranır `CSid` nesne veya `SID` yapısı ve C++ Standart Kitaplığı koleksiyon sınıfları ile uyumluluk sağlamak için kullanılır.

##  <a name="operator_gt__eq"></a>  operator > =

Olmadığını test eder `CSid` nesne veya `SID` işlecinin sol tarafındaki yapısı büyüktür veya eşittir `CSid` nesne veya `SID` yapısı işlecin sağ tarafındaki (C++ Standart Kitaplığı uyumluluk için).

```   
bool operator<(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>Parametreler

*lhs*  
İlk `CSid` nesne veya `SID` Karşılaştırılacak yapısı.

*Sol*  
İkinci `CSid` nesne veya `SID` Karşılaştırılacak yapısı.

### <a name="return-value"></a>Dönüş Değeri

Gerekirse TRUE döndürür adresini *lhs* büyüktür veya eşittir adresini *sol*false Aksi takdirde.

### <a name="remarks"></a>Açıklamalar

Bu işlecin adresini davranır `CSid` nesne veya `SID` yapısı ve C++ Standart Kitaplığı koleksiyon sınıfları ile uyumluluk sağlamak için kullanılır.

