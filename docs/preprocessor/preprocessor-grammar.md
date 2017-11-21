---
title: "Ön İşlemci dil bilgisi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- preprocessor
- grammar, preprocessor
- preprocessor, grammar
ms.assetid: 6cd33fad-0b08-4592-9be8-7359c43e24e9
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 3c64c5a1855d80d5abc60d959bd68b33a380583b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="preprocessor-grammar"></a>Ön işlemci Dil Bilgisi
**#define***tanımlayıcısı* *belirteci dize*iptal et    
  
 *#***tanımlamak***tanımlayıcısı*[**(** *tanımlayıcısı*kabul**,** *...*  **,** *tanımlayıcısı*kabul **)**] *belirteci dize*iptal et    
  
 **tanımlı (***tanımlayıcısı* **)**   
  
 **tanımlanan***tanımlayıcısı*   
  
 `#include`**"***yolu spec***"**  
  
 `#include` **\<**  *yol belirtimi***>**  
  
 **#line***basamak dizisi***"** *filename* **"**iptal et      
  
 *#***undef***tanımlayıcısı*   
  
 **#error***belirteci dize*   
  
 **#pragma***belirteci dize*   
  
 *Koşullu* :  
 *IF-bölümü elif parçaları*kabul*else bölümünü*kabul*endif satır*  
  
 *IF-bölümü* :  
 *IF-linetext*  
  
 *IF-line* :  
 **#if***sabit ifadesi*   
  
 **#ifdef***tanımlayıcısı*   
  
 **#ifndef***tanımlayıcısı*   
  
 *elif bölümleri* :  
 *elif satırlı metin*  
  
 *elif bölümleri elif satırlı metin*  
  
 *elif satır* :  
 **#elif***sabit ifadesi*   
  
 *else bölümünü* :  
 *linetext başka*  
  
 *satırı başka* :  
 `#else`  
  
 *Satır içi endif* :  
 `#endif`  
  
 *basamak dizisi* :  
 *basamak*  
  
 *basamak dizisi basamak*  
  
 *basamak* : biri  
 **0 1 2 3 4 5 6 7 8 9**  
  
 *belirteç dizesini* :  
 Belirteçleri dizesi  
  
 *belirteç* :  
 *anahtar sözcüğü*  
  
 *tanımlayıcı*  
  
 *sabiti*  
  
 *işleci*  
  
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
 [Dilbilgisi özeti (C/C++)](../preprocessor/grammar-summary-c-cpp.md)