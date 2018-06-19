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
ms.openlocfilehash: 322d4add32aca1c57b45a601e4704b2ec5d99a02
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32375812"
---
# <a name="setting-compiler-options"></a>Derleyici Seçeneklerini Ayarlama
C ve C++ derleyici seçenekleri geliştirme ortamında veya komut satırında ayarlanabilir.  
  
## <a name="in-the-development-environment"></a>Geliştirme Ortamında  
 Derleyici seçenekleri her proje için ayarlayabileceğiniz kendi **özellik sayfaları** iletişim kutusu. Sol bölmede seçin **yapılandırma özellikleri**, **C/C++** ve derleyici seçeneği kategori seçin. Her derleyici seçeneğinin başlığı, geliştirme ortamında nasıl ayarlanabileceği ve nerede bulunabileceğini tanımlar. Bkz: [derleyici seçenekleri](../../build/reference/compiler-options.md) tam listesi için.  
  
## <a name="outside-the-development-environment"></a>Geliştirme Ortamının Dışında  
 Derleyici (CL.exe) seçeneklerini ayarlayabilirsiniz:  
  
-   [Komut satırında](../../build/reference/compiler-command-line-syntax.md)  
  
-   [Komut dosyaları](../../build/reference/cl-command-files.md)  
  
-   [CL ortam değişkeni](../../build/reference/cl-environment-variables.md)  
  
 CL ortam değişkeninde belirtilen seçenekler, CL her çağrıldığında kullanılır. Bir komut dosyası CL ortam değişkeninde veya komut satırında adlandırılmışsa, komut dosyasında belirtilen seçenekler kullanılır. Komut satırında veya CL ortam değişkeninde olanın aksine, komut dosyası birden fazla satırı seçeneği ve dosya adı kullanmanıza izin verir.  
  
 Derleyici seçenekleri "soldan sağa" işlenir ve bir çakışma ile karşılaşıldığında son (en sağ) seçenek tercih edilir. CL ortam değişkeni komut satırından önce işlenir, bu nedenle CL ve komut satırı arasındaki çakışma durumlarında komut satırı önceliklidir.  
  
## <a name="additional-compiler-topics"></a>Ek Derleyici Başlıkları  
  
-   [Hızlı Derleme](../../build/reference/fast-compilation.md)  
  
-   [CL Bağlayıcı Çağırır](../../build/reference/cl-invokes-the-linker.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C/C++ oluşturma başvurusu](../../build/reference/c-cpp-building-reference.md)   
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)