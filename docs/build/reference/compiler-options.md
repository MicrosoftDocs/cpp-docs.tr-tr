---
title: Derleyici Seçenekleri | Microsoft Docs
ms.custom: ''
ms.date: 01/29/2018
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- cl.exe compiler
- x86 Visual C++ compiler
- ARM Visual C++ compiler
- compiler options, C++
- x64 Visual C++ compiler
ms.assetid: ed3376c8-bef4-4c9a-80e9-3b5da232644c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 76ab322dc4573863a30092b296e87e90c41619ab
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45716221"
---
# <a name="compiler-options"></a>Derleyici Seçenekleri

cl.exe Microsoft Visual C++ (MSVC) C ve C++ Derleyicileri ve bağlayıcı denetleyen bir araçtır. cl.exe yalnızca Microsoft Visual Studio için Windows destekleyen işletim sistemleri üzerinde çalıştırılabilir.

> [!NOTE]
> Bu araç yalnızca Visual Studio Geliştirici komut isteminden başlatabilirsiniz. Bir sistem komut satırından veya dosya Gezgini'nden başlatılamıyor. Daha fazla bilgi için [komut satırında C/C++ derleme kodu](../building-on-the-command-line.md).

Derleyiciler, ortak nesne dosyası biçimi (COFF) nesne (.obj) dosyaları oluşturur. Bağlayıcı yürütülebilir (.exe) dosya veya dinamik bağlantı kitaplıklarını (DLL'ler) üretir.

Tüm derleyici seçeneklerinin büyük küçük harfe duyarlı olduğunu unutmayın. Her iki eğik çizgi kullanabilir (`/`) veya tire (`-`) bir derleyici seçeneğini belirtmek için.

Bağlamadan derlemek için kullanın [/c](../../build/reference/c-compile-without-linking.md) seçeneği.

## <a name="find-a-compiler-option"></a>Derleyici seçeneği bulun

Belirli bir derleyici seçeneği bulmak için aşağıdaki listelerden birine bakın:

- [Alfabetik Listelenmiş Derleyici Seçenekleri](../../build/reference/compiler-options-listed-alphabetically.md)

- [Kategorilere Göre Listelenen Derleyici Seçenekleri](../../build/reference/compiler-options-listed-by-category.md)

## <a name="specify-compiler-options"></a>Derleyici seçeneklerini belirtin

Her derleyici seçeneğinin konuda geliştirme ortamında nasıl ayarlanabilir açıklanır. Geliştirme ortamı dışında seçenekleri belirtme hakkında daha fazla bilgi için bkz:

- [Derleyici Komut Satırı Sözdizimi](../../build/reference/compiler-command-line-syntax.md)

- [CL Komut Dosyaları](../../build/reference/cl-command-files.md)

- [CL Ortam Değişkenleri](../../build/reference/cl-environment-variables.md)

## <a name="related-build-tools"></a>İlgili yapı araçları

[Bağlayıcı seçenekleri](../../build/reference/linker-options.md) programınızın nasıl oluşturulduğunu da etkiler.

## <a name="see-also"></a>Ayrıca bkz.

[C/C++ Derleme Başvurusu](../../build/reference/c-cpp-building-reference.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)<br/>
[Hızlı Derleme](../../build/reference/fast-compilation.md)<br/>
[CL Bağlayıcı Çağırır](../../build/reference/cl-invokes-the-linker.md)
