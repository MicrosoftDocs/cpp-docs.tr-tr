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
ms.workload: cplusplus
ms.openlocfilehash: 797d4bf4274a92ca4f265d01579698c0f9c6a4a3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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