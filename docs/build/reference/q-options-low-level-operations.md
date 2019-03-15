---
title: /Q Seçenekler (Düşük Düzey İşlemler)
ms.date: 1/23/2018
f1_keywords:
- /q
helpviewer_keywords:
- Q compiler option [C++]
- -Q compiler option [C++]
- /Q compiler option [C++]
ms.openlocfilehash: 5bbb63b4f437f8aefd5c84c1c1c4bd20bdb965cb
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57819915"
---
# <a name="q-options-low-level-operations"></a>/Q Seçenekler (Düşük Düzey İşlemler)

Kullanabileceğiniz **/Q** aşağıdaki alt düzey derleme işlemlerini gerçekleştirmek için derleyici seçenekleri:

- [/ Qfast_transcendentals (hızlı Soyutları zorla)](qfast-transcendentals-force-fast-transcendentals.md): Hızlı transcendentals üretir.

- [/ Qıfist (_ftol gösterme)](qifist-suppress-ftol.md): Bastırır `_ftol` gerekli (yalnızca x86) olduğunda bir kayan nokta türünden bir tamsayı türüne dönüştürme.

- [/ Qimprecise_fwaits (Try blokları içindeki fwaits'i Kaldır)](qimprecise-fwaits-remove-fwaits-inside-try-blocks.md): Kaldırır `fwait` içindeki komutları `try` engeller.

- [/ Qpar (otomatik paralel hale getirici)](qpar-auto-parallelizer.md): Otomatik paralelleştirilmesini ile işaretlenmiş etkinleştirir [#pragma loop()](../../preprocessor/loop.md) yönergesi.

- [/ Qpar (otomatik paralel hale getirici düzeyi raporlama) raporu](qpar-report-auto-parallelizer-reporting-level.md): Otomatik paralelleştirme için raporlama seviyelerini etkinleştirir.

- [/ Qsafe_fp_loads](qsafe-fp-loads.md): Kayan nokta kaydı yükler ve bellek ile MMX kayıtları arasında taşıma iyileştirmeleri bastırır.

- [/ Qspectre](qspectre.md): Belirli Spectre güvenlik açıklarını gidermek için yönergeler oluşturur.

- [/ Qvec-(otomatik vektör hale getirici report raporlama düzeyi)](qvec-report-auto-vectorizer-reporting-level.md): Otomatik vektörleştirme için raporlama seviyelerini etkinleştirir.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici komut satırı sözdizimi](compiler-command-line-syntax.md)
