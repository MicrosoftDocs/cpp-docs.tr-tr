---
title: "Derleyici seçeneklerini ayarlama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- compiler options, setting
- cl.exe compiler, setting options
ms.assetid: 4b079f5b-0017-4124-aad6-0d2b58e427e0
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: dbbc7111ceae2353e8bc9820ead319556ce0016b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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