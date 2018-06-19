---
title: -Q Seçenekler (düşük düzey işlemler) | Microsoft Docs
ms.custom: ''
ms.date: 1/23/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /q
dev_langs:
- C++
helpviewer_keywords:
- Q compiler option [C++]
- -Q compiler option [C++]
- /Q compiler option [C++]
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c8a18c5d790cf21e8eb130a2b2baa152e20d79a1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32375041"
---
# <a name="q-options-low-level-operations"></a>/Q Seçenekler (Düşük Düzey İşlemler)

Kullanabileceğiniz **/Q** derleyici seçenekleri aşağıdaki alt düzey derleyici işlemleri gerçekleştirmek için:

- [/ Qfast_transcendentals (hızlı Soyutları zorla)](../../build/reference/qfast-transcendentals-force-fast-transcendentals.md): hızlı soyutları oluşturur.

- [/ Qıfist (bastır _ftol)](../../build/reference/qifist-suppress-ftol.md): bastırır `_ftol` kayan nokta türünden bir tamsayı türüne dönüştürme, gerekli (yalnızca x86) olduğunda.

- [/ Qimprecise_fwaits (Try blokları içindeki fwaits'i Kaldır)](../../build/reference/qimprecise-fwaits-remove-fwaits-inside-try-blocks.md): kaldırır `fwait` içindeki komutları `try` engeller.

- [/ Qpar (otomatik paralel hale getirici)](../../build/reference/qpar-auto-parallelizer.md): etkinleştirir işaretlenir döngüsü otomatik paralelleştirme [#pragma loop()](../../preprocessor/loop.md) yönergesi.

- [/ Qpar-rapor (otomatik paralel hale getirici raporlama düzeyi)](../../build/reference/qpar-report-auto-parallelizer-reporting-level.md): otomatik paralelleştirme düzeylerini raporlama etkinleştirir.

- [/ Qsafe_fp_loads](../../build/reference/qsafe-fp-loads.md): kayan nokta kaydı yükler ve bellek ve MMX arasındaki taşımalar için kaydeder için en iyi duruma getirme gizler.

- [/ Qspectre](../../build/reference/qspectre.md): belirli Spectre güvenlik açıklarını azaltmak için yönergeler oluşturur.

- [/ Qvec-report (otomatik vektör hale getirici raporlama düzeyi)](../../build/reference/qvec-report-auto-vectorizer-reporting-level.md): otomatik vectorization düzeylerini raporlama etkinleştirir.

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)  
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)  
