---
description: 'Daha fazla bilgi edinin: derleyici seçenekleri'
title: MSVC derleyici seçenekleri
ms.date: 05/06/2019
helpviewer_keywords:
- cl.exe compiler
- x86 MSVC compiler
- ARM MSVC compiler
- compiler options, C++
- x64 MSVC compiler
ms.assetid: ed3376c8-bef4-4c9a-80e9-3b5da232644c
ms.openlocfilehash: a6b124fa5fce68844d53c1324da48c17ef5a9ccf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97197029"
---
# <a name="compiler-options"></a>Derleyici Seçenekleri

cl.exe, Microsoft C++ (MSVC) C ve C++ derleyicilerini ve bağlayıcıyı denetleyen bir araçtır. cl.exe, yalnızca Windows için Microsoft Visual Studio destekleyen işletim sistemlerinde çalıştırılabilir.

> [!NOTE]
> Bu aracı yalnızca bir Visual Studio Geliştirici komut isteminden başlatabilirsiniz. Bunu bir sistem komut isteminden veya dosya Gezgini 'nden başlatamazsınız. Daha fazla bilgi için, bkz. [MSVC araç takımını komut satırından kullanma](../building-on-the-command-line.md).

Derleyiciler ortak nesne dosyası biçimi (COFF) nesne (. obj) dosyaları oluşturur. Bağlayıcı yürütülebilir (. exe) dosyalar ya da dinamik bağlantı kitaplıkları (dll 'Ler) üretir.

Tüm derleyici seçeneklerinin büyük/küçük harfe duyarlı olduğunu unutmayın. `/` `-` Bir derleyici seçeneğini belirtmek için eğik çizgi () veya tire () kullanabilirsiniz.

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
