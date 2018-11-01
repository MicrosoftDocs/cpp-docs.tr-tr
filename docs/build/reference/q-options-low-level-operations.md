---
title: /Q Seçenekler (Düşük Düzey İşlemler)
ms.date: 1/23/2018
f1_keywords:
- /q
helpviewer_keywords:
- Q compiler option [C++]
- -Q compiler option [C++]
- /Q compiler option [C++]
ms.openlocfilehash: a6dcbd256fa3510955884d3adba4855b23cdbfab
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50514263"
---
# <a name="q-options-low-level-operations"></a>/Q Seçenekler (Düşük Düzey İşlemler)

Kullanabileceğiniz **/Q** aşağıdaki alt düzey derleme işlemlerini gerçekleştirmek için derleyici seçenekleri:

- [/ Qfast_transcendentals (hızlı Soyutları zorla)](../../build/reference/qfast-transcendentals-force-fast-transcendentals.md): hızlı transcendentals üretir.

- [/ Qıfist (bastır _ftol)](../../build/reference/qifist-suppress-ftol.md): bastırır `_ftol` gerekli (yalnızca x86) olduğunda bir kayan nokta türünden bir tamsayı türüne dönüştürme.

- [/ Qimprecise_fwaits (Try blokları içindeki fwaits'i Kaldır)](../../build/reference/qimprecise-fwaits-remove-fwaits-inside-try-blocks.md): kaldırır `fwait` içindeki komutları `try` engeller.

- [/ Qpar (otomatik paralel hale getirici)](../../build/reference/qpar-auto-parallelizer.md): sağlayan otomatik paralelleştirilmesini ile işaretlenmiş [#pragma loop()](../../preprocessor/loop.md) yönergesi.

- [/ Qpar-report (otomatik paralel hale getirici raporlama düzeyi)](../../build/reference/qpar-report-auto-parallelizer-reporting-level.md): otomatik paralelleştirme için raporlama seviyelerini etkinleştirir.

- [/ Qsafe_fp_loads](../../build/reference/qsafe-fp-loads.md): kayan nokta kaydı yükler ve kaydeder bellek ve MMX arasındaki taşımalar için en iyi duruma getirme bastırır.

- [/ Qspectre](../../build/reference/qspectre.md): belirli Spectre güvenlik açıklarını gidermek için yönergeler oluşturur.

- [/ Qvec-report (otomatik vektör hale getirici raporlama düzeyi)](../../build/reference/qvec-report-auto-vectorizer-reporting-level.md): otomatik vektörleştirme için raporlama seviyelerini etkinleştirir.

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)
