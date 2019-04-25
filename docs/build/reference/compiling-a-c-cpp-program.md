---
title: MSVC C/C++ Derleyici başvurusu - Visual Studio
description: MSVC derleyici araç takımı seçenekleri.
ms.date: 12/10/2018
helpviewer_keywords:
- cl.exe compiler
- cl.exe compiler, setting options
ms.assetid: f3eef5ab-d0be-4fb2-90f9-927e6ed58736
ms.openlocfilehash: 2269ba69cea2702ff190c791eb6753acb3619f7d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62294154"
---
# <a name="compiling-a-cc-project"></a>C/C++ projesi derleme

C ve C++ derleyici seçenekleri, Visual Studio IDE veya komut satırında ayarlanabilir. 

## <a name="in-visual-studio"></a>Visual Studio'da

Visual Studio her proje için derleyici seçeneklerini ayarlayabilirsiniz **özellik sayfaları** iletişim kutusu. Sol bölmede seçin **yapılandırma özellikleri**, **C/C++** derleyici seçeneği kategorisini seçin. Her derleyici seçeneğinin başlığı, geliştirme ortamında nasıl ayarlanabileceği ve nerede bulunabileceğini tanımlar. Bkz: [MSVC derleyici seçenekleri](compiler-options.md) tam listesi için.

## <a name="from-the-command-line"></a>Komut satırından

Derleyici (CL.exe) seçeneklerini ayarlayabilirsiniz:

- [Komut satırında](compiler-command-line-syntax.md)

- [Komut dosyaları](cl-command-files.md)

- [CL ortam değişkeninde](cl-environment-variables.md)

CL ortam değişkeninde belirtilen seçenekler, CL her çağrıldığında kullanılır. Bir komut dosyası CL ortam değişkeninde veya komut satırında adlandırılmışsa, komut dosyasında belirtilen seçenekler kullanılır. Komut satırında veya CL ortam değişkeninde olanın aksine, komut dosyası birden fazla satırı seçeneği ve dosya adı kullanmanıza izin verir.

Derleyici seçenekleri "soldan sağa" işlenir ve bir çakışma ile karşılaşıldığında son (en sağ) seçenek tercih edilir. CL ortam değişkeni komut satırından önce işlenir, bu nedenle CL ve komut satırı arasındaki çakışma durumlarında komut satırı önceliklidir.

## <a name="additional-compiler-topics"></a>Ek Derleyici Başlıkları

- [MSVC Derleyicisi Seçenekleri](compiler-options.md)

- [Önceden Derlenmiş Üst Bilgi Dosyaları](../creating-precompiled-header-files.md)

- [CL Bağlayıcı Çağırır](cl-invokes-the-linker.md)

Derleyici konak ve hedef mimari seçme hakkında daha fazla bilgi için bkz [yapılandırma C++ projeleri 64-bit için x64 hedefleri](../configuring-programs-for-64-bit-visual-cpp.md).

## <a name="see-also"></a>Ayrıca bkz.

[C/C++ Derleme Başvurusu](c-cpp-building-reference.md)
