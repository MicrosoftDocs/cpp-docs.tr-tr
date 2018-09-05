---
title: . Bağlayıcı girişi olarak obj dosyaları | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- linker [C++], OBJ files as input
- object files, linker output
- OMF object files
- LINK tool [C++], .obj files
- COFF files
- OBJ files as linker input
- .obj files as linker input
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bd1fbd635b1d3d3a5f9963edaa9f22e22472dad1
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43691757"
---
# <a name="obj-files-as-linker-input"></a>Bağlayıcı Girişi olarak .Obj Dosyaları

Bağlayıcı Aracı (bağlantı. EXE) .obj dosyaları ortak nesne dosyası biçimi (COFF) olarak kabul eder.

## <a name="remarks"></a>Açıklamalar

Microsoft ortak nesne dosyası biçimi ilişkin kapsamlı bir açıklama sağlar. Daha fazla bilgi için [PE biçimi](/windows/desktop/Debug/pe-format).

## <a name="unicode-support"></a>Unicode desteği

Visual Studio 2005 ile başlayarak, Microsoft Visual C++ derleyicisi ISO/IEC C ve C++ standartları tarafından tanımlandığı şekilde tanımlayıcıları olarak Unicode karakterleri destekler. Önceki derleyici sürümleri tanımlayıcılar yalnızca ASCII karakterleri desteklenir. İşlevler, sınıflar ve statikler adlarındaki Unicode desteği için derleyici ve bağlayıcı .obj dosyaları COFF sembolleri Unicode UTF-8 kodlamasını kullanın. UTF-8 kodlamasını, ASCII Visual Studio'nun önceki sürümleri tarafından kullanılan kodlamayla upwardly uyumludur.

Derleyicide ve bağlayıcıda hakkında daha fazla bilgi için bkz: [derleyicide ve bağlayıcıda Unicode desteği](../../build/reference/unicode-support-in-the-compiler-and-linker.md). Unicode standardı hakkında daha fazla bilgi için bkz. [Unicode](http://www.unicode.org/) kuruluş.

## <a name="see-also"></a>Ayrıca bkz.

[LINK Giriş Dosyaları](../../build/reference/link-input-files.md)  
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)  
[Unicode Desteği](../../text/support-for-unicode.md)  
[Derleyicide ve Bağlayıcıda Unicode Desteği](../../build/reference/unicode-support-in-the-compiler-and-linker.md)  
[Unicode standardı](http://www.unicode.org/)  
[PE biçimi](/windows/desktop/Debug/pe-format)  
