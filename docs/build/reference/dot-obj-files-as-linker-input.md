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
ms.openlocfilehash: 304c9861b85be1925e48d47c6006fcbcdd41dc22
ms.sourcegitcommit: 5f276064779d90a4cfda758f89e0c0f1e4d1a188
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/09/2020
ms.locfileid: "75791603"
---
# <a name="obj-files-as-linker-input"></a>Bağlayıcı Girişi olarak .Obj Dosyaları

Bağlayıcı aracı (bağlantı. EXE) ortak nesne dosyası biçimi (COFF) içindeki. obj dosyalarını kabul eder.

## <a name="remarks"></a>Açıklamalar

Microsoft, ortak nesne dosyası biçiminin ayrıntılı bir açıklamasını sağlar. Daha fazla bilgi için bkz. [PE biçimi](/windows/win32/Debug/pe-format).

## <a name="unicode-support"></a>Unicode desteği

Visual Studio 2005 ' den itibaren, Microsoft MSVC derleyicisi ISO/ıEC C ve C++ standartları tarafından tanımlanan Tanımlayıcılardaki Unicode karakterleri destekler. Derleyicinin önceki sürümleri tanımlayıcılardaki yalnızca ASCII karakterleri destekliyordu. İşlevler, sınıflar ve statiklerdeki UNICODE 'U desteklemek için derleyici ve bağlayıcı,. obj dosyalarındaki COFF sembolleri için Unicode UTF-8 kodlamasını kullanır. UTF-8 kodlaması, Visual Studio 'nun önceki sürümleri tarafından kullanılan ASCII kodlamasıyla upwardly uyumludur.

Derleyici ve bağlayıcı hakkında daha fazla bilgi için bkz. [derleyicide ve bağlayıcıda Unicode desteği](unicode-support-in-the-compiler-and-linker.md). Unicode standardı hakkında daha fazla bilgi için bkz. [Unicode](https://home.unicode.org/) organizasyonu.

## <a name="see-also"></a>Ayrıca bkz.

[LINK Giriş Dosyaları](link-input-files.md)<br/>
[MSVC Bağlayıcı Seçenekleri](linker-options.md)<br/>
[Unicode Desteği](../../text/support-for-unicode.md)<br/>
[Derleyicide ve Bağlayıcıda Unicode Desteği](unicode-support-in-the-compiler-and-linker.md)<br/>
[Unicode standart](https://home.unicode.org/)<br/>
[PE biçimi](/windows/win32/Debug/pe-format)
