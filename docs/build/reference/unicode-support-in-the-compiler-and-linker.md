---
title: "Derleyicide ve bağlayıcıda Unicode desteği | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.UseUnicodeResponseFiles
- VC.Project.VCLibrarianTool.UseUnicodeResponseFiles
- VC.Project.VCCLCompilerTool.UseUnicodeResponseFiles
- VC.Project.VCXDCMakeTool.UseUnicodeResponseFiles
dev_langs: C++
helpviewer_keywords: Unicode, Visual C++
ms.assetid: acc1d322-56b9-4696-a30e-2af891a4e288
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 15fefc4cc44edfd67bd8ba89ab68c6965c8639a6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="unicode-support-in-the-compiler-and-linker"></a>Derleyicide ve Bağlayıcıda Unicode Desteği
Bu konuda, Visual C++ derleme araçları Unicode desteği açıklanmaktadır.  
  
 Dosya Adları  
 Komut satırında veya derleyici yönergeleri belirtilen dosya adları (gibi #include) şimdi Unicode karakterler içerebilir.  
  
 Kaynak kodu dosyaları  
 Unicode karakterler tanımlayıcıları, makroları, dize ve karakter değişmez değerleri ve açıklamaları artık desteklenmektedir.  Evrensel karakter adları de artık desteklenmektedir.  
  
 Unicode aşağıdaki Kodlamalar bir kaynak kodu dosyasına girebilirsiniz:  
  
-   UTF-16 little endian bayt sırası işareti (BOM) olmadan veya ile  
  
-   UTF-16 big endian ile veya olmadan AĞACI  
  
-   UTF-8 ile AĞACI  
  
 Çıkış  
 Derleme sırasında derleyici UTF-16 konsolunda tanılama çıkarır.  Konsol penceresinde özellikler, konsolda görüntülenen karakterleri bağlıdır.  Bir dosyaya yeniden yönlendirilen derleyici çıkışı geçerli ANSI konsol kod sayfasında yapılır.  
  
 Bağlayıcı yanıt dosyaları ve. DEF dosyaları  
 Yanıt dosyaları ve DEF dosyaları ya da UTF-16 bayt sırası işareti veya ANSI sahip olabilir.  Daha önce yalnızca ANSI destekleniyordu.  
  
 .asm ve .cod dökümleri  
 .asm ve .cod dökümleri ANSI MASM ile uyumluluk için varsayılan olan.  UTF-8 çıktısını almak için /FAu kullanın.  /FAs belirtirseniz, intermingled kaynak yalnızca doğrudan basılır ve, örneğin kaynak kodu UTF-8'dir ve /FAsu belirtmediğiniz bozuk görünebilir unutmayın.  
  
 Unicode dosya adlarını geliştirme ortamında etkinleştirebilirsiniz (bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md)) uygun aracı seçerek ve seçerek **Unicode yanıt dosyaları etkinleştir** özelliği Varsayılan olarak etkindir. Bu varsayılan değişebilir bir geliştirme ortamınızı Unicode desteği olmayan bir derleyici kullanacak şekilde değiştirirseniz nedenidir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Komut satırında C/C++ kodu derleme](../../build/building-on-the-command-line.md)