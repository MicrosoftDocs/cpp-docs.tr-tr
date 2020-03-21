---
title: MSVC C/C++ derleyici başvurusu-Visual Studio
description: MSVC derleyici araç takımı seçenekleri.
ms.date: 12/10/2018
helpviewer_keywords:
- cl.exe compiler
- cl.exe compiler, setting options
ms.assetid: f3eef5ab-d0be-4fb2-90f9-927e6ed58736
ms.openlocfilehash: c75176b139895d7b00d88aca1c58604b47386894
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80077371"
---
# <a name="compiling-a-cc-project"></a>C/C++ proje derleme

C ve C++ derleyici seçenekleri, VISUAL Studio IDE içinde ya da komut satırında ayarlanabilir.

## <a name="in-visual-studio"></a>Visual Studio’da

Visual Studio **Özellik sayfaları** iletişim kutusunda her bir proje için derleyici seçeneklerini ayarlayabilirsiniz. Sol bölmede, **yapılandırma özellikleri**, **C/C++**  öğesini seçin ve ardından derleyici seçenek kategorisini seçin. Her derleyici seçeneğinin başlığı, geliştirme ortamında nasıl ayarlanabileceği ve nerede bulunabileceğini tanımlar. Tüm liste için bkz. [MSVC derleyicisi seçenekleri](compiler-options.md) .

## <a name="from-the-command-line"></a>Komut satırından

Derleyici (CL.exe) seçeneklerini ayarlayabilirsiniz:

- [Komut satırında](compiler-command-line-syntax.md)

- [Komut dosyalarında](cl-command-files.md)

- [CL ortam değişkeninde](cl-environment-variables.md)

CL ortam değişkeninde belirtilen seçenekler, CL her çağrıldığında kullanılır. Bir komut dosyası CL ortam değişkeninde veya komut satırında adlandırılmışsa, komut dosyasında belirtilen seçenekler kullanılır. Komut satırında veya CL ortam değişkeninde olanın aksine, komut dosyası birden fazla satırı seçeneği ve dosya adı kullanmanıza izin verir.

Derleyici seçenekleri "soldan sağa" işlenir ve bir çakışma ile karşılaşıldığında son (en sağ) seçenek tercih edilir. CL ortam değişkeni komut satırından önce işlenir, bu nedenle CL ve komut satırı arasındaki çakışma durumlarında komut satırı önceliklidir.

## <a name="additional-compiler-topics"></a>Ek Derleyici Başlıkları

- [MSVC Derleyicisi Seçenekleri](compiler-options.md)

- [Önceden Derlenmiş Üst Bilgi Dosyaları](../creating-precompiled-header-files.md)

- [CL Bağlayıcı Çağırır](cl-invokes-the-linker.md)

Derleyici Konağı ve hedef mimarisini seçme hakkında daha fazla bilgi için bkz [. C++ 64-bit, x64 hedefleri için projeleri yapılandırma](../configuring-programs-for-64-bit-visual-cpp.md).

## <a name="see-also"></a>Ayrıca bkz.

[C/C++ Derleme Başvurusu](c-cpp-building-reference.md)
