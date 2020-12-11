---
description: 'Hakkında daha fazla bilgi edinin: ortak Visual C++ 64-bit geçiş sorunları'
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
ms.openlocfilehash: 86c4618423353a3a7ac217432ce9dfcb0c19061b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97156898"
---
# <a name="common-visual-c-64-bit-migration-issues"></a>Genel Visual C++ 64 Bit Geçiş Sorunları

64 bitlik bir Windows işletim sisteminde çalıştırılacak uygulamalar oluşturmak için Microsoft C++ derleyicisini (MSVC) kullandığınızda, aşağıdaki sorunlardan haberdar olmanız gerekir:

- **`int`** **`long`** , 64 bit Windows işletim sistemlerinde 32 bitlik değerlerdir. 64 bitlik platformlar için derlemeyi planladığınız programlar için, 32 bit değişkenlere işaretçiler atamamaya dikkat etmeniz gerekir. İşaretçiler 64 bit platformlarda 64 bittir ve bunu bir 32-bit değişkenine atarsanız işaretçi değerini kesecektir.

- `size_t`, `time_t` ve `ptrdiff_t` 64 bit Windows işletim sistemlerinde 64 bitlik değerlerdir.

- `time_t` , Visual Studio 2005 ve önceki sürümlerde 32 bit Windows işletim sistemlerinde 32 bitlik bir değerdir. `time_t` artık varsayılan olarak 64 bitlik bir tamsayıdır. Daha fazla bilgi için bkz. [süre yönetimi](../c-runtime-library/time-management.md).

   Kodunuzun bir **`int`** değeri aldığını ve bir veya değeri olarak işlem yaparken dikkat etmeniz gerekir `size_t` `time_t` . Sayının 32 bitlik bir sayıdan daha büyük olması ve verilerin depoya geri geçirildiğinde kesilecek olması mümkündür **`int`** .

% X (onaltılı **`int`** Biçim) `printf` değiştiricisi, 64 bitlik bir Windows işletim sisteminde beklendiği gibi çalışmaz. Yalnızca kendisine geçirilen değerin ilk 32 biti üzerinde çalışır.

- Onaltılık biçimde 32 bitlik bir integral türü göstermek için% I32x kullanın.

- Onaltılık biçimde 64 bitlik bir integral türü göstermek için% I64x kullanın.

- % P (işaretçinin onaltılık biçimi), 64 bitlik bir Windows işletim sisteminde beklendiği gibi çalışacaktır.

Daha fazla bilgi için bkz:

- [MSVC derleyici seçenekleri](reference/compiler-options.md)

- [Geçiş Ipuçları](/windows/win32/WinProg64/migration-tips)

## <a name="see-also"></a>Ayrıca bkz.

[64 bit, x64 hedefleri için C++ projelerini yapılandırma](configuring-programs-for-64-bit-visual-cpp.md)<br/>
[Visual C++ Taşıma ve Yükseltme Kılavuzu](../porting/visual-cpp-porting-and-upgrading-guide.md)
