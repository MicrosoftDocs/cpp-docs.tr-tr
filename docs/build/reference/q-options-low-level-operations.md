---
title: /Q Seçenekler (Düşük Düzey İşlemler)
ms.date: 01/08/2020
f1_keywords:
- /q
helpviewer_keywords:
- Q compiler option [C++]
- -Q compiler option [C++]
- /Q compiler option [C++]
ms.openlocfilehash: 9dd3675f200be4f0ec66620bcf3cf05706991b66
ms.sourcegitcommit: a930a9b47bd95599265d6ba83bb87e46ae748949
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2020
ms.locfileid: "76518185"
---
# <a name="q-options-low-level-operations"></a>/Q Seçenekler (Düşük Düzey İşlemler)

Aşağıdaki alt düzey derleyici işlemlerini gerçekleştirmek için **/q** derleyici seçeneklerini kullanabilirsiniz:

- [/Qfast_transcendentals (hızlı bir şekilde zorla zorla)](qfast-transcendentals-force-fast-transcendentals.md): hızlı bir şekilde, daha fazla işlem oluşturur.

- [/Qifist (_Ftol bastır)](qifist-suppress-ftol.md): kayan nokta türünden bir tamsayı türüne dönüştürme yapılması gerektiğinde `_ftol` bastırır (yalnızca x86).

- [/Qimprecise_fwaits (TRY blokları içinde fwait 'Yi Kaldır)](qimprecise-fwaits-remove-fwaits-inside-try-blocks.md): `try` blokları içindeki `fwait` komutları kaldırır.

- [/Qıntel-JCC-errat](qintel-jcc-erratum.md): Intel atlaymcode (JCC) ermıtum mikro kod güncelleştirmesinden kaynaklanan performans etkisini azaltır.

- [/Qpar (otomatik paralelleştirme)](qpar-auto-parallelizer.md): [#pragma loop ()](../../preprocessor/loop.md) yönergesiyle işaretlenen döngülerin otomatik paralelleştirilmesini mümkün hale getirme.

- [/Qpar-report (otomatik paralel hale getirici raporlama düzeyi)](qpar-report-auto-parallelizer-reporting-level.md): otomatik paralelleştirme için raporlama düzeylerine izin vermez.

- [/Qsafe_fp_loads](qsafe-fp-loads.md): kayan nokta kayıt yükleri ve bellek ile MMX kayıtları arasında taşınan iyileştirmeleri gizler.

- [/Qspectre](qspectre.md): belirli Spectre güvenlik açıklarını azaltmak için yönergeler oluşturur.

- [/Qvec-report (otomatik Vektörleştirici raporlama düzeyi)](qvec-report-auto-vectorizer-reporting-level.md): otomatik vektörleştirme için raporlama düzeylerine izin vermez.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)
