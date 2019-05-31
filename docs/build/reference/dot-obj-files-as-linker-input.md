---
title: Bağlayıcı Girişi olarak .Obj Dosyaları
ms.date: 12/29/2017
helpviewer_keywords:
- linker [C++], OBJ files as input
- object files, linker output
- OMF object files
- LINK tool [C++], .obj files
- COFF files
- OBJ files as linker input
- .obj files as linker input
ms.openlocfilehash: 36f41077fcba6b093865625d426b8009f6185e7b
ms.sourcegitcommit: 28eae422049ac3381c6b1206664455dbb56cbfb6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/31/2019
ms.locfileid: "66450584"
---
# <a name="obj-files-as-linker-input"></a>Bağlayıcı Girişi olarak .Obj Dosyaları

Bağlayıcı Aracı (bağlantı. EXE) .obj dosyaları ortak nesne dosyası biçimi (COFF) olarak kabul eder.

## <a name="remarks"></a>Açıklamalar

Microsoft ortak nesne dosyası biçimi ilişkin kapsamlı bir açıklama sağlar. Daha fazla bilgi için [PE biçimi](/windows/desktop/Debug/pe-format).

## <a name="unicode-support"></a>Unicode desteği

Visual Studio 2005 ile başlayarak, Microsoft MSVC derleyicisi ISO/IEC C ve C++ standartları tarafından tanımlandığı şekilde tanımlayıcıları, Unicode karakterleri destekler. Önceki derleyici sürümleri tanımlayıcılar yalnızca ASCII karakterleri desteklenir. İşlevler, sınıflar ve statikler adlarındaki Unicode desteği için derleyici ve bağlayıcı .obj dosyaları COFF sembolleri Unicode UTF-8 kodlamasını kullanın. UTF-8 kodlamasını, ASCII Visual Studio'nun önceki sürümleri tarafından kullanılan kodlamayla upwardly uyumludur.

Derleyicide ve bağlayıcıda hakkında daha fazla bilgi için bkz: [derleyicide ve bağlayıcıda Unicode desteği](unicode-support-in-the-compiler-and-linker.md). Unicode standardı hakkında daha fazla bilgi için bkz. [Unicode](https://www.unicode.org/) kuruluş.

## <a name="see-also"></a>Ayrıca bkz.

[LINK Giriş Dosyaları](link-input-files.md)<br/>
[MSVC Bağlayıcı Seçenekleri](linker-options.md)<br/>
[Unicode Desteği](../../text/support-for-unicode.md)<br/>
[Derleyicide ve Bağlayıcıda Unicode Desteği](unicode-support-in-the-compiler-and-linker.md)<br/>
[Unicode standardı](https://www.unicode.org/)<br/>
[PE biçimi](/windows/desktop/Debug/pe-format)
