---
title: "Ön İşlemci dil bilgisi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- preprocessor
- grammar, preprocessor
- preprocessor, grammar
ms.assetid: 6cd33fad-0b08-4592-9be8-7359c43e24e9
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 02b3597b035e3ea4bfa1670aa405109f4c01a077
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="preprocessor-grammar"></a>Ön işlemci Dil Bilgisi
**#define***tanımlayıcısı* *belirteci dize*iptal et    
  
 *#* **tanımlamak***tanımlayıcısı*[**(** *tanımlayıcısı*kabul**,** *...*  **,** *tanımlayıcısı*kabul **)**] *belirteci dize*iptal et    
  
 **tanımlı (***tanımlayıcısı* **)**   
  
 **tanımlanan***tanımlayıcısı*   
  
 `#include` **"***yolu spec***"**  
  
 `#include` **\<***yol belirtimi***>**  
  
 **#line**  *digit-sequence*  **"** *filename* **"**opt  
  
 *#* **undef***tanımlayıcısı*   
  
 **#error***belirteci dize*   
  
 **#pragma**  *token-string*  
  
 *Koşullu* :  
 *IF-bölümü elif parçaları*kabul*else bölümünü*kabul*endif satır*  
  
 *IF-bölümü* :  
 *if-linetext*  
  
 *IF-line* :  
 **#if**  *constant-expression*  
  
 **#ifdef**  *identifier*  
  
 **#ifndef**  *identifier*  
  
 *elif bölümleri* :  
 *elif satırlı metin*  
  
 *elif bölümleri elif satırlı metin*  
  
 *elif satır* :  
 **#elif**  *constant-expression*  
  
 *else-part* :  
 *else-linetext*  
  
 *satırı başka* :  
 `#else`  
  
 *Satır içi endif* :  
 `#endif`  
  
 *basamak dizisi* :  
 *Basamak*  
  
 *basamak dizisi basamak*  
  
 *basamak* : biri  
 **0 1 2 3 4 5 6 7 8 9**  
  
 *belirteç dizesini* :  
 Belirteçleri dizesi  
  
 *belirteç* :  
 *keyword*  
  
 *identifier*  
  
 *constant*  
  
 *operator*  
  
 `punctuator`  
  
 *Dosya adı* :  
 Geçerli işletim sistemi dosya adı  
  
 *yol spec* :  
 Yasal dosya yolu  
  
 *metin* :  
 Herhangi bir dizi metin  
  
> [!NOTE]
>  İçinde aşağıdaki Terminal dışı Genişletilmiş [sözcük kuralları](../cpp/lexical-conventions.md) bölümünü *C++ dil başvurusu*: `constant`, `constant` - *ifadesi* , *tanımlayıcısı*, *anahtar sözcüğü*, `operator`, ve `punctuator`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dilbilgisi Özeti (C/C++)](../preprocessor/grammar-summary-c-cpp.md)