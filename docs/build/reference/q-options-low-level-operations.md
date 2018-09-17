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
ms.openlocfilehash: 15854333a9f26f87d20f7819327e68050ab37bf6
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45717800"
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
