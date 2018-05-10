---
title: Ön İşlemci dil bilgisi | Microsoft Docs
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
ms.openlocfilehash: d14a3e00e18a2d3ac69dd472ac4056a379ada224
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="preprocessor-grammar"></a>Ön işlemci Dil Bilgisi
**#define***tanımlayıcısı* *belirteci dize*iptal et  
  
 *#* **tanımlamak***tanımlayıcısı*[**(** *tanımlayıcısı*kabul **,** *...*  **,** *tanımlayıcısı*kabul **)**] *belirteci dize*iptal et  
  
 **tanımlı (***tanımlayıcısı* **)**  
  
 **tanımlanan***tanımlayıcısı*  
  
 `#include` **"***yolu spec***"**  
  
 `#include` **\<***yol belirtimi***>**  
  
 **#line***basamak dizisi***"** *filename* **"** iptal et      
  
 *#* **undef***tanımlayıcısı*  
  
 **#error***belirteci dize*  
  
 **#pragma***belirteci dize*   
  
 *Koşullu* :  
 *IF-bölümü elif parçaları*kabul*else bölümünü*kabul*endif satır*  
  
 *IF-bölümü* :  
 *IF-linetext*  
  
 *IF-line* :  
 **#if**  *constant-expression*  
  
 **#ifdef***tanımlayıcısı*   
  
 **#ifndef***tanımlayıcısı*   
  
 *elif bölümleri* :  
 *elif satırlı metin*  
  
 *elif bölümleri elif satırlı metin*  
  
 *elif satır* :  
 **#elif**  *constant-expression*  
  
 *else bölümünü* :  
 *linetext başka*  
  
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
 *Anahtar sözcüğü*  
  
 *Tanımlayıcı*  
  
 *sabiti*  
  
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