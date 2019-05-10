---
title: MSVC derleyici seçenekleri
ms.date: 05/06/2019
helpviewer_keywords:
- cl.exe compiler
- x86 MSVC compiler
- ARM MSVC compiler
- compiler options, C++
- x64 MSVC compiler
ms.assetid: ed3376c8-bef4-4c9a-80e9-3b5da232644c
ms.openlocfilehash: ab41a5de027f28b361937e58fb179fd72db54e4e
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65221743"
---
# <a name="compiler-options"></a>Derleyici Seçenekleri

cl.exe Microsoft denetleyen bir araçtır C++ (MSVC) C ve C++ derleyicileri ve bağlayıcı. cl.exe yalnızca Microsoft Visual Studio için Windows destekleyen işletim sistemleri üzerinde çalıştırılabilir.

> [!NOTE]
> Bu araç yalnızca Visual Studio Geliştirici komut isteminden başlatabilirsiniz. Bir sistem komut satırından veya dosya Gezgini'nden başlatılamıyor. Daha fazla bilgi için [komut satırından MSVC araç takımı kullanın](../building-on-the-command-line.md).

Derleyiciler, ortak nesne dosyası biçimi (COFF) nesne (.obj) dosyaları oluşturur. Bağlayıcı yürütülebilir (.exe) dosya veya dinamik bağlantı kitaplıklarını (DLL'ler) üretir.

Tüm derleyici seçeneklerinin büyük küçük harfe duyarlı olduğunu unutmayın. Her iki eğik çizgi kullanabilir (`/`) veya tire (`-`) bir derleyici seçeneğini belirtmek için.

Bağlamadan derlemek için kullanın [/c](c-compile-without-linking.md) seçeneği.

## <a name="find-a-compiler-option"></a>Derleyici seçeneği bulun

Belirli bir derleyici seçeneği bulmak için aşağıdaki listelerden birine bakın:

- [Alfabetik Listelenmiş Derleyici Seçenekleri](compiler-options-listed-alphabetically.md)

- [Kategorilere Göre Listelenen Derleyici Seçenekleri](compiler-options-listed-by-category.md)

## <a name="specify-compiler-options"></a>Derleyici seçeneklerini belirtin

Her derleyici seçeneğinin konuda geliştirme ortamında nasıl ayarlanabilir açıklanır. Geliştirme ortamı dışında seçenekleri belirtme hakkında daha fazla bilgi için bkz:

- [MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)

- [CL Komut Dosyaları](cl-command-files.md)

- [CL Ortam Değişkenleri](cl-environment-variables.md)

## <a name="related-build-tools"></a>İlgili yapı araçları

[MSVC bağlayıcı seçenekleri](linker-options.md) programınızın nasıl oluşturulduğunu da etkiler.

## <a name="see-also"></a>Ayrıca bkz.

[C/C++ Derleme Başvurusu](c-cpp-building-reference.md)<br/>
[CL Bağlayıcı Çağırır](cl-invokes-the-linker.md)
