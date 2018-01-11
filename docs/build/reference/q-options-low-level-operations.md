---
title: "-Q Seçenekler (düşük düzey işlemler) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /q
dev_langs: C++
helpviewer_keywords:
- Q compiler option [C++]
- -Q compiler option [C++]
- /Q compiler option [C++]
ms.assetid: 9fa738b9-630a-4bde-bc87-bdfa30552be4
caps.latest.revision: "24"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d970c2de5e34840ab2ed77f229c329db3c6f72fd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="q-options-low-level-operations"></a>/Q Seçenekler (Düşük Düzey İşlemler)
Kullanabileceğiniz **/Q** derleyici seçenekleri aşağıdaki alt düzey derleyici işlemleri gerçekleştirmek için:  
  
-   [/ Qfast_transcendentals (hızlı Soyutları zorla)](../../build/reference/qfast-transcendentals-force-fast-transcendentals.md): hızlı soyutları oluşturur.  
  
-   [/ Qıfist (bastır _ftol)](../../build/reference/qifist-suppress-ftol.md): bastırır `_ftol` kayan nokta türünden bir tamsayı türüne dönüştürme, gerekli (yalnızca x86) olduğunda.  
  
-   [/ Qimprecise_fwaits (Try blokları içindeki fwaits'i Kaldır)](../../build/reference/qimprecise-fwaits-remove-fwaits-inside-try-blocks.md): kaldırır `fwait` içindeki komutları `try` engeller.  
  
-   [/ Qpar (otomatik paralel hale getirici)](../../build/reference/qpar-auto-parallelizer.md): etkinleştirir işaretlenir döngüsü otomatik paralelleştirme [#pragma loop()](../../preprocessor/loop.md) yönergesi.  
  
-   [/ Qpar-rapor (otomatik paralel hale getirici raporlama düzeyi)](../../build/reference/qpar-report-auto-parallelizer-reporting-level.md): otomatik paralelleştirme düzeylerini raporlama etkinleştirir.  
  
-   [/ Qsafe_fp_loads](../../build/reference/qsafe-fp-loads.md): kayan nokta kaydı yükler ve bellek ve MMX arasındaki taşımalar için kaydeder için en iyi duruma getirme gizler.  
  
-   [/ Qvec-report (otomatik vektör hale getirici raporlama düzeyi)](../../build/reference/qvec-report-auto-vectorizer-reporting-level.md): otomatik vectorization düzeylerini raporlama etkinleştirir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)