---
title: _bstr_t::operator += + | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _bstr_t::operator+
- _bstr_t::operator+=
dev_langs: C++
helpviewer_keywords:
- += operator [C++], appending strings
- + operator [C++], _bstr_t objects
ms.assetid: d28316ce-c2c8-4a38-bdb3-44fa4e582c44
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 503f021a9ef0f798af8d82f33dac84d3eb0ccc51
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
  
-   **operator + (***s2***&#124;** *s1***)** yeni döndürür `_bstr_t` birden çok baytlı dize birleştirerek biçimlendirilmiş *s2*, Unicode dönüştürülebilir ile `BSTR` içinde kapsüllenmiş *s1*.          
  
-   **operator + (** `s3` **,***s1***)** yeni döndürür `_bstr_t` bir UNICODE dizesi birleştirerek biçimlendirilmiş `s3` ile `BSTR` içinde kapsüllenmiş *s1*.        
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_bstr_t sınıfı](../cpp/bstr-t-class.md)