---
title: Genel Visual C++ 64 Bit Geçiş Sorunları
ms.date: 05/06/2019
helpviewer_keywords:
- 64-bit programming [C++], migration
- 64-bit compiler [C++], migration
- porting 32-bit code to 64-bit code
- migration [C++], 64-bit code issues
- 32-bit code porting [C++]
- 64-bit applications [C++]
- 64-bit compiler [C++], porting 32-bit code
- Win64 [C++]
ms.assetid: d17fb838-7513-4e2d-8b27-a1666f17ad76
ms.openlocfilehash: b03ccc76163d79688a98ec89df241292e3eef112
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65220877"
---
# <a name="common-visual-c-64-bit-migration-issues"></a>Genel Visual C++ 64 Bit Geçiş Sorunları

Microsoft kullandığınızda C++ derleyicisi (64-bit Windows işletim sisteminde çalıştırılacak uygulamalar oluşturmak için MSVC) olmanız gerekir aşağıdaki sorunlarından haberdar:

- Bir `int` ve `long` 64 bit Windows işletim sistemlerinde 32-bit değerleri. 64 bit platformları için derlemek için plan programları için işaretçiler, 32-bit değişkenlere atamamayı dikkatli olmanız gerekir. İşaretçiler bir 32-bit değişkene atarsanız, 64-bit ve 64-bit platformlarda işaretçi değeri truncate.

- `size_t`, `time_t`, ve `ptrdiff_t` 64 bit Windows işletim sistemlerinde 64 bitlik değerler.

- `time_t` Visual Studio 2005 ve daha önce 32-bit Windows işletim sistemlerinde bir 32-bit değeri var. `time_t` Varsayılan olarak, 64 bitlik bir tamsayı olarak sunulmuştur. Daha fazla bilgi için [zaman Yönetimi](../c-runtime-library/time-management.md).

   Kodunuzu nereye aldığını ve bilmeniz gereken bir `int` olarak işler ve değeri bir `size_t` veya `time_t` değeri. Sayı 32 bit bir sayı büyük olacak şekilde büyüyebilir ve verileri geri iletildiğinde kesilir mümkündür `int` depolama.

%X (onaltılık `int` biçimi) `printf` değiştiricisi, bir 64 bit Windows işletim sisteminde beklendiği gibi çalışmaz. Yalnızca ilk 32 biti kendisine geçirilen değerin üzerinde çalışır.

- Onaltılık biçiminde bir 32 bit tamsayı türünü görüntülemek için % I32x'i kullanın.

- % I64x onaltılık biçiminde bir 64 bit tamsayı türünü görüntülemek için kullanın.

- %P (onaltılık biçimde bir işaretçi için), bir 64 bit Windows işletim sisteminde beklendiği gibi çalışır.

Daha fazla bilgi için bkz.:

- [MSVC Derleyicisi Seçenekleri](reference/compiler-options.md)

- [Geçiş ipuçları](/windows/desktop/WinProg64/migration-tips)

## <a name="see-also"></a>Ayrıca bkz.

[C++ projeleri için 64 bit x64 yapılandırma hedefleri](configuring-programs-for-64-bit-visual-cpp.md)<br/>
[Visual C++ Taşıma ve Yükseltme Kılavuzu](../porting/visual-cpp-porting-and-upgrading-guide.md)
