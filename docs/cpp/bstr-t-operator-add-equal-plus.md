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
ms.openlocfilehash: aad73939b8fd011fd6e1c9bf16f8dfe6eb303ff3
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39405749"
---
# <a name="bstrtoperator--"></a>_bstr_t::operator +=, +
**Microsoft'a özgü**  
  
 Sonuna karakterler ekler `_bstr_t` nesne veya iki dizeyi art arda ekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
_bstr_t& operator+=( const _bstr_t& s1 );  
_bstr_t operator+( const _bstr_t& s1 );  
friend _bstr_t operator+( const char* s2, const _bstr_t& s1);  
friend _bstr_t operator+( const wchar_t* s3, const _bstr_t& s1);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *S1*  
 A `_bstr_t` nesne.  
  
 *S2*  
 Çok baytlı bir dize.  
  
 *S3*  
 Bir Unicode dize.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işleçler, dize birleştirme gerçekleştirin:  
  
-   **operator += (***s1***)** kapsüllenmiş karakterler ekler `BSTR` , *s1* sonuna kadar bu nesnenin kapsüllenmiş `BSTR`.  
  
-   **operator + (***s1***)** yeni döndürür `_bstr_t` bu nesnenin birleştirerek biçimlendirilmiş `BSTR` değeriyle *s1*.  
  
-   **operator + (***s2***&#124;***s1***)** yeni bir `_bstr_t` birleştirerek biçimlendirilmiş bir çok baytlı bir dize *s2*türüne dönüştürülmüş olarak Unicode ile `BSTR` içinde kapsüllenir *s1*.          
  
-   **operator + (***s3* **,***s1***)** yeni bir `_bstr_t` bir Unicode dize birleştirerek biçimlendirilmiş *s3* ile `BSTR` içinde kapsüllenir *s1*.        
  
 **END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [_bstr_t Sınıfı](../cpp/bstr-t-class.md)