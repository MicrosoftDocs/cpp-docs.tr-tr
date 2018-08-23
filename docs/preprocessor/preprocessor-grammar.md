---
title: Ön İşlemci dilbilgisi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- preprocessor
- grammar, preprocessor
- preprocessor, grammar
ms.assetid: 6cd33fad-0b08-4592-9be8-7359c43e24e9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1871d1b8281f4dd74733133ede70ed80430246b3
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2018
ms.locfileid: "42464471"
---
# <a name="preprocessor-grammar"></a>Ön işlemci Dil Bilgisi
**#define***tanımlayıcı* *belirteç dizesinde*iyileştirilmiş    
  
*#* **tanımlama***tanımlayıcı*[**(** *tanımlayıcı*iyileştirilmiş **,** *...*  **,** *tanımlayıcı*iyileştirilmiş **)**] *belirteç dizesinde*iyileştirilmiş    
  
**tanımlanan (***tanımlayıcı* **)**   
  
**tanımlanan***tanımlayıcısı*   
  
`#include` **"***path-spec***"**  
  
`#include` **\<***PATH-spec***>**  
  
**#line***basamak dizisi***"** *filename* **"** iyileştirilmiş      
  
*#* **undef***tanımlayıcısı*   
  
**#error***belirteci dizesi*   
  
**#pragma***belirteci dizesi*   
  
*Koşullu* :  
*Eğer bölümü elif-parts*iyileştirilmiş*else bölümünü*iyileştirilmiş*endif satır*  
  
*Eğer bölümü* :  
*Eğer linetext*  
  
*Eğer satır içi* :  
**#if**  *constant-expression*  
  
**#ifdef***tanımlayıcısı*   
  
**#ifndef***tanımlayıcısı*   
  
*elif-parts* :  
*elif-line metni*  
  
*elif-parts elif-line metni*  
  
*elif-satırı* :  
**#elif**  *constant-expression*  
  
*else bölümünü* :  
*linetext else*  
  
*başka satır* :  
`#else`  
  
*Satır içi endif* :  
`#endif`  
  
*basamak dizisi* :  
*basamak*  
  
*basamak dizisi basamak*  
  
*basamak* : biri  
**0 1 2 3 4 5 6 7 8 9**  
  
*belirteç dizesinde* :  
Dize belirteçleri  
  
*belirteç* :  
*Anahtar sözcüğü*  
  
*tanımlayıcı*  
  
*Sabit*  
  
*operator*  
  
`punctuator`  
  
*filename* :  
Geçerli işletim sistemi dosya adı  
  
*PATH-spec* :  
Geçerli dosya yolu  
  
*metin* :  
Metin dizisi  
  
> [!NOTE]
> İçinde aşağıdaki Terminal olmayanları Genişletilmiş [sözcük kuralları](../cpp/lexical-conventions.md) bölümünü *C++ dil başvurusu*: `constant`, `constant` - *ifadesi* , *tanımlayıcı*, *anahtar sözcüğü*, `operator`, ve `punctuator`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 
[Dilbilgisi Özeti (C/C++)](../preprocessor/grammar-summary-c-cpp.md)