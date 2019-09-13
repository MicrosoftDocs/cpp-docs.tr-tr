---
title: /Q Seçenekler (Düşük Düzey İşlemler)
ms.date: 01/23/2018
f1_keywords:
- /q
helpviewer_keywords:
- Q compiler option [C++]
- -Q compiler option [C++]
- /Q compiler option [C++]
ms.openlocfilehash: 6348226aa38d1f2eefdf9e19e27c4c87bd2f0812
ms.sourcegitcommit: effb516760c0f956c6308eeded48851accc96b92
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70927666"
---
# <a name="q-options-low-level-operations"></a>/Q Seçenekler (Düşük Düzey İşlemler)

Aşağıdaki alt düzey derleyici işlemlerini gerçekleştirmek için **/q** derleyici seçeneklerini kullanabilirsiniz:

- [/Qfast_tranaldentals (hızlı](qfast-transcendentals-force-fast-transcendentals.md)bir şekilde geçiş zorla): Hızlı bir şekilde daha fazla işlem oluşturur.

- [/Qifist (_ftol bastır)](qifist-suppress-ftol.md): Bir `_ftol` kayan nokta türünden bir tamsayı türüne dönüştürme yapılması gerektiğinde (yalnızca x86) bastırır.

- [/Qımprecı_fwait (TRY blokları içinde fwait 'Yi Kaldır)](qimprecise-fwaits-remove-fwaits-inside-try-blocks.md): Bloklar `fwait` içindeki`try` komutları kaldırır.

- [/Qpar (otomatik paralelleştirme)](qpar-auto-parallelizer.md): [#Pragma loop ()](../../preprocessor/loop.md) yönergesiyle işaretlenen döngülerin otomatik paralelleştirilmesini mümkün hale getirme.

- [/Qpar-report (otomatik paralel hale getirici raporlama düzeyi)](qpar-report-auto-parallelizer-reporting-level.md): Otomatik paralelleştirme için raporlama düzeylerini mümkün hale getirme.

- [/Qsafe_fp_yükleri](qsafe-fp-loads.md): Kayan nokta kayıt yükleri ve bellek ile MMX kayıtları arasında taşınan iyileştirmeleri gizler.

- [/Qspectre](qspectre.md): Bazı Spectre güvenlik açıklarını hafifletmek için yönergeler üretir.

- [/Qvec-report (otomatik Vektörleştirici raporlama düzeyi)](qvec-report-auto-vectorizer-reporting-level.md): Otomatik vektörleştirme için raporlama düzeylerine izin vermez.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)
