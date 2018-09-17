---
title: Derleyici seçeneklerini ayarlama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- compiler options, setting
- cl.exe compiler, setting options
ms.assetid: 4b079f5b-0017-4124-aad6-0d2b58e427e0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cf7ee185f43f62f9e9a735650801e0cbd1a1b43d
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45712471"
---
# <a name="setting-compiler-options"></a>Derleyici Seçeneklerini Ayarlama

C ve C++ derleyici seçenekleri geliştirme ortamında veya komut satırında ayarlanabilir.

## <a name="in-the-development-environment"></a>Geliştirme Ortamında

Her proje için derleyici seçeneklerini ayarlayabilirsiniz kendi **özellik sayfaları** iletişim kutusu. Sol bölmede seçin **yapılandırma özellikleri**, **C/C++** derleyici seçeneği kategorisini seçin. Her derleyici seçeneğinin başlığı, geliştirme ortamında nasıl ayarlanabileceği ve nerede bulunabileceğini tanımlar. Bkz: [derleyici seçenekleri](../../build/reference/compiler-options.md) tam listesi için.

## <a name="outside-the-development-environment"></a>Geliştirme Ortamının Dışında

Derleyici (CL.exe) seçeneklerini ayarlayabilirsiniz:

- [Komut satırında](../../build/reference/compiler-command-line-syntax.md)

- [Komut dosyaları](../../build/reference/cl-command-files.md)

- [CL ortam değişkeninde](../../build/reference/cl-environment-variables.md)

CL ortam değişkeninde belirtilen seçenekler, CL her çağrıldığında kullanılır. Bir komut dosyası CL ortam değişkeninde veya komut satırında adlandırılmışsa, komut dosyasında belirtilen seçenekler kullanılır. Komut satırında veya CL ortam değişkeninde olanın aksine, komut dosyası birden fazla satırı seçeneği ve dosya adı kullanmanıza izin verir.

Derleyici seçenekleri "soldan sağa" işlenir ve bir çakışma ile karşılaşıldığında son (en sağ) seçenek tercih edilir. CL ortam değişkeni komut satırından önce işlenir, bu nedenle CL ve komut satırı arasındaki çakışma durumlarında komut satırı önceliklidir.

## <a name="additional-compiler-topics"></a>Ek Derleyici Başlıkları

- [Hızlı Derleme](../../build/reference/fast-compilation.md)

- [CL Bağlayıcı Çağırır](../../build/reference/cl-invokes-the-linker.md)

## <a name="see-also"></a>Ayrıca Bkz.

[C/C++ Derleme Başvurusu](../../build/reference/c-cpp-building-reference.md)<br/>
[Derleyici Seçenekleri](../../build/reference/compiler-options.md)