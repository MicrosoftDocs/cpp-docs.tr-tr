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
ms.openlocfilehash: ffbc1d7fc7f74121c37c9e80a538ec60f2265701
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43219568"
---
# <a name="obj-files-as-linker-input"></a>Bağlayıcı Girişi olarak .Obj Dosyaları

Bağlayıcı Aracı (bağlantı. EXE) .obj dosyaları ortak nesne dosyası biçimi (COFF) olarak kabul eder.

## <a name="remarks"></a>Açıklamalar

Microsoft ortak nesne dosyası biçimi ilişkin kapsamlı bir açıklama sağlar. Daha fazla bilgi için [PE biçimi](/windows/desktop/Debug/pe-format).

## <a name="unicode-support"></a>Unicode desteği

Visual Studio 2005 ile başlayarak, Microsoft Visual C++ derleyicisi ISO/IEC C ve C++ standartları tarafından tanımlandığı şekilde tanımlayıcıları olarak Unicode karakterleri destekler. Önceki derleyici sürümleri tanımlayıcılar yalnızca ASCII karakterleri desteklenir. İşlevler, sınıflar ve statikler adlarındaki Unicode desteği için derleyici ve bağlayıcı .obj dosyaları COFF sembolleri Unicode UTF-8 kodlamasını kullanın. UTF-8 kodlamasını, ASCII Visual Studio'nun önceki sürümleri tarafından kullanılan kodlamayla upwardly uyumludur.

Derleyicide ve bağlayıcıda hakkında daha fazla bilgi için bkz: [derleyicide ve bağlayıcıda Unicode desteği](../../build/reference/unicode-support-in-the-compiler-and-linker.md). Unicode standardı hakkında daha fazla bilgi için bkz. [Unicode](http://go.microsoft.com/fwlink/p/?linkid=37123) kuruluş.

## <a name="see-also"></a>Ayrıca bkz.

[LINK Giriş Dosyaları](../../build/reference/link-input-files.md)  
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)  
[Unicode Desteği](../../text/support-for-unicode.md)  
[Derleyicide ve Bağlayıcıda Unicode Desteği](../../build/reference/unicode-support-in-the-compiler-and-linker.md)  
[Unicode standardı](http://go.microsoft.com/fwlink/p/?linkid=37123)  
[PE biçimi](/windows/desktop/Debug/pe-format)  
