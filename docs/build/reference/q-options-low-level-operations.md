---
title: /Q Seçenekler (Düşük Düzey İşlemler)
ms.date: 01/08/2020
f1_keywords:
- /q
helpviewer_keywords:
- Q compiler option [C++]
- -Q compiler option [C++]
- /Q compiler option [C++]
ms.openlocfilehash: f5342071cef76bcc736f128c344279898a61c462
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87231500"
---
# <a name="q-options-low-level-operations"></a>/Q Seçenekler (Düşük Düzey İşlemler)

Aşağıdaki alt düzey derleyici işlemlerini gerçekleştirmek için **/q** derleyici seçeneklerini kullanabilirsiniz:

- [/Qfast_transcendentals (hızlı bir şekilde zorla zorla)](qfast-transcendentals-force-fast-transcendentals.md): hızlı bir şekilde, daha fazla işlem oluşturur.

- [/Qifist (_Ftol bastır)](qifist-suppress-ftol.md): bir `_ftol` kayan nokta türünden bir tamsayı türüne dönüştürme yapılması gerektiğinde bastırır (yalnızca x86).

- [/Qimprecise_fwaits (TRY blokları içinde fwait 'Yi Kaldır)](qimprecise-fwaits-remove-fwaits-inside-try-blocks.md): `fwait` bloklar içindeki komutları kaldırır **`try`** .

- [/Qıntel-JCC-errat](qintel-jcc-erratum.md): Intel atlaymcode (JCC) ermıtum mikro kod güncelleştirmesinden kaynaklanan performans etkisini azaltır.

- [/Qpar (otomatik paralelleştirme)](qpar-auto-parallelizer.md): [#pragma loop ()](../../preprocessor/loop.md) yönergesiyle işaretlenen döngülerin otomatik paralelleştirilmesini mümkün hale getirme.

- [/Qpar-report (otomatik paralel hale getirici raporlama düzeyi)](qpar-report-auto-parallelizer-reporting-level.md): otomatik paralelleştirme için raporlama düzeylerine izin vermez.

- [/Qsafe_fp_loads](qsafe-fp-loads.md): kayan nokta kayıt yükleri ve bellek ile MMX kayıtları arasında taşınan iyileştirmeleri gizler.

- [/Qspectre](qspectre.md): belirli Spectre güvenlik açıklarını azaltmak için yönergeler oluşturur.

- [/Qspectre-Load](qspectre-load.md): yüklere göre Spectre güvenlik açıklarını azaltmak için yönergeler oluşturur.

- [/Qspectre-Load-CF](qspectre-load-cf.md): Spectre güvenlik açıklarını, yükü olan denetim akışı yönergelerine göre azaltmak için yönergeler oluşturur.

- [/Qvec-report (otomatik Vektörleştirici raporlama düzeyi)](qvec-report-auto-vectorizer-reporting-level.md): otomatik vektörleştirme için raporlama düzeylerine izin vermez.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici komut satırı sözdizimi](compiler-command-line-syntax.md)
