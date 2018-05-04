---
title: _bstr_t::operator += + | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _bstr_t::operator+
- _bstr_t::operator+=
dev_langs:
- C++
helpviewer_keywords:
- += operator [C++], appending strings
- + operator [C++], _bstr_t objects
ms.assetid: d28316ce-c2c8-4a38-bdb3-44fa4e582c44
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1e443b233e19f6cdc64d7d6021a9a9c078a4f327
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="bstrtoperator--"></a>_bstr_t::operator +=, +
**Microsoft özel**  
  
 Karakter sonuna ekler `_bstr_t` nesne veya iki dizeyi art arda ekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      _bstr_t& operator+=(  
   const _bstr_t& s1   
);  
_bstr_t operator+(  
   const _bstr_t& s1   
);  
friend _bstr_t operator+(  
   const char* s2,  
   const _bstr_t& s1   
);  
friend _bstr_t operator+(  
   const wchar_t* s3,  
   const _bstr_t& s1   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *S1*  
 A `_bstr_t` nesnesi.  
  
 *S2*  
 Birden çok baytlı bir dize.  
  
 `s3`  
 Bir UNICODE dizesi.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işleçlere dize birleştirme gerçekleştirin:  
  
-   **operator += (***s1***)** kapsüllenmiş karakterleri ekler `BSTR` , *s1* bu nesnenin kapsüllenmiş sonuna`BSTR`.      
  
-   **operator + (***s1***)** yeni döndürür `_bstr_t` bu nesnenin birleştirerek biçimlendirilmiş `BSTR` değeriyle *s1*.      
  
-   **operator + (***s2***&#124;***s1***)** yeni döndürür `_bstr_t` birleştirerek biçimlendirilmiş bir birden çok baytlı dize *s2*, Unicode dönüştürülebilir ile `BSTR` içinde kapsüllenmiş *s1*.          
  
-   **operator + (** `s3` **,***s1***)** yeni döndürür `_bstr_t` bir UNICODE dizesi birleştirerek biçimlendirilmiş `s3` ile `BSTR` içinde kapsüllenmiş *s1*.        
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_bstr_t Sınıfı](../cpp/bstr-t-class.md)