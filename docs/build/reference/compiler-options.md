---
description: 'Daha fazla bilgi edinin: derleyici seçenekleri'
title: MSVC derleyici seçenekleri
ms.date: 12/14/2020
helpviewer_keywords:
- cl.exe compiler
- x86 MSVC compiler
- ARM MSVC compiler
- compiler options, C++
- x64 MSVC compiler
ms.openlocfilehash: f89695b00be4ed67a00f947c6b76943bfa5eaf59
ms.sourcegitcommit: 48b897797b3132ae934b1d191e3870c3c2466335
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/15/2020
ms.locfileid: "97514582"
---
# <a name="compiler-options"></a>Derleyici Seçenekleri

cl.exe, Microsoft C++ (MSVC) C ve C++ derleyicilerini ve bağlayıcıyı denetleyen bir araçtır. cl.exe, yalnızca Windows için Microsoft Visual Studio destekleyen işletim sistemlerinde çalıştırılabilir.

> [!NOTE]
> Bu aracı yalnızca bir Visual Studio Geliştirici komut isteminden başlatabilirsiniz. Bunu bir sistem komut isteminden veya dosya Gezgini 'nden başlatamazsınız. Daha fazla bilgi için, bkz. [MSVC araç takımını komut satırından kullanma](../building-on-the-command-line.md).

Derleyiciler ortak nesne dosyası biçimi (COFF) nesne (. obj) dosyaları oluşturur. Bağlayıcı yürütülebilir (. exe) dosyalar ya da dinamik bağlantı kitaplıkları (dll 'Ler) üretir.

Tüm derleyici seçenekleri büyük/küçük harfe duyarlıdır. `/` `-` Bir derleyici seçeneğini belirtmek için eğik çizgi () veya tire () kullanabilirsiniz.

Bağlama olmadan derlemek için [/c](c-compile-without-linking.md) seçeneğini kullanın.

## <a name="find-a-compiler-option"></a>Derleyici seçeneği bulma

Belirli bir derleyici seçeneğini bulmak için aşağıdaki listelerden birine bakın:

- [Alfabetik Listelenmiş Derleyici Seçenekleri](compiler-options-listed-alphabetically.md)

- [Kategoriye göre listelenen derleyici seçenekleri](compiler-options-listed-by-category.md)

## <a name="specify-compiler-options"></a>Derleyici seçeneklerini belirtin

Her derleyici seçeneğinin konusu, geliştirme ortamında nasıl ayarlayabileceğinizi anlatmaktadır. Geliştirme ortamı dışında seçenekleri belirtme hakkında bilgi için bkz.:

- [MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)

- [CL komut dosyaları](cl-command-files.md)

- [CL ortam değişkenleri](cl-environment-variables.md)

## <a name="related-build-tools"></a>İlgili derleme araçları

[MSVC bağlayıcı seçenekleri](linker-options.md) , programınızın nasıl oluşturulduğunu da etkiler.

## <a name="see-also"></a>Ayrıca bkz.

[C/C++ Oluşturma Başvurusu](c-cpp-building-reference.md)<br/>
[CL, bağlayıcıyı çağırır](cl-invokes-the-linker.md)
