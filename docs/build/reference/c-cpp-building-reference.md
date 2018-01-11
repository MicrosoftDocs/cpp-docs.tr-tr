---
title: "C/C++ oluşturma başvurusu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- compiling source code [C++], additional information
- cl.exe compiler [C++], building programs
- linker [C++], building reference
- builds [C++], additional information
ms.assetid: 100b4ccf-572c-4d1f-970c-fa0bc0cc0d2d
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9e2269be27dd039357c11d38a2be83b5fc9d6504
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cc-building-reference"></a>C/C++ Oluşturma Başvurusu
Visual C++ C/C++ programı oluşturmanın iki yolu sağlar. En kolay (ve en yaygın) yolu [Visual C++ geliştirme ortamında yapı](../../ide/building-cpp-projects-in-visual-studio.md). Diğer yolu [komut satırı araçlarını kullanarak bir komut isteminden yapı](../../build/building-on-the-command-line.md). Her iki durumda da, Kaynak dosyalarınız Visual C++ kaynak Düzenleyicisi veya bir üçüncü taraf düzenleyiciyi kullanarak oluşturabilirsiniz.  
  
 Programınızı .vcxproj dosya yerine bir derleme görevleri dosyası kullanıyorsa, hala, geliştirme ortamında oluşturabileceğiniz bir [harici proje](../../ide/building-external-projects.md).  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [C/C++ Programı Derleme](../../build/reference/compiling-a-c-cpp-program.md)  
 Makine kodu, bağlayıcı yönergeleri, bölümler, dış başvuruları ve işlev/veri adlarını içeren bir nesne dosyası oluşturur derleyici açıklar.  
  
 [Bağlama](../../build/reference/linking.md)  
 Derleyici tarafından oluşturulan nesne dosyalarından ve statik olarak bağlantılı kitaplıklarından kodu birleştirir, bağlayıcı adı başvuruları çözümler ve yürütülebilir bir dosya oluşturur.  
  
 [Yayın Derlemeleri](../../build/reference/release-builds.md)  
 Neden ve ne zaman bir hata ayıklama değiştirmek istersiniz sunar hakkında daha fazla bilgi için yayın derlemesi oluşturun ve ayrıca bazı hata ayıklama için yayın derlemesi değiştirirken karşılaşabileceğiniz sorunları ele alır.  
  
 [Kodunuzu İyileştirme](../../build/reference/optimizing-your-code.md)  
 Kodu iyileştirme mekanizmalar ele konulara bağlantılar sağlar:  
  
 [C/C++ Derleme Araçları](../../build/reference/c-cpp-build-tools.md)  
 Görüntüleme veya düzenleme yapı çıktı için aşağıdaki komut satırı araçları sağlar:  
  
 [C/C++ Derleme Hataları](../../error-messages/compiler-errors-1/c-cpp-build-errors.md)  
 Derleme hataları bölüm tablosundaki İçindekiler tanıtır.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [C/C++ Ön İşlemci Başvurusu](../../preprocessor/c-cpp-preprocessor-reference.md)  
 Makrolar, işleçler ve yönergeleri çevirerek kaynak dosyaları için derleyici hazırlar önişlemci açıklanır.  
  
 [Özel Derleme Adımlarını ve Derleme Olaylarını Anlama](../../ide/understanding-custom-build-steps-and-build-events.md)  
 Derleme işlemi özelleştirme açıklanır.  
  
 [C/C++ programı oluşturma](../../build/building-c-cpp-programs.md)  
 Komut satırından veya Visual Studio tümleşik geliştirme ortamı'ndan programınızı oluşturma açıklayan konulara bağlantılar sağlar.  
  
 [Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)  
 Derleyici seçeneklerini ayarlama geliştirme ortamında veya komut satırında açıklar.  
  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)  
 Derleyici seçenekleri kullanarak ele konulara bağlantılar sağlar.  
  
 [Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)  
 Bağlayıcı seçeneklerini ayarlama veya tümleşik geliştirme ortamı dışındaki açıklar.  
  
 [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)  
 Bağlayıcı seçeneklerini kullanarak ele konulara bağlantılar sağlar.  
  
 [BSCMAKE Başvurusu](../../build/reference/bscmake-reference.md)  
 Microsoft gözatma bilgileri bakım yardımcı programı (BSCMAKE. açıklanır .Sbr gözatma bilgileri dosyası (.bsc) derlemeler EXE), derleme sırasında oluşturulan dosyalar.  
  
 [LIB Başvurusu](../../build/reference/lib-reference.md)  
 Microsoft kitaplığı oluşturur ve ortak nesne dosyası biçimi (COFF) nesne dosyaları içeren bir kitaplık yöneten Yöneticisi'ni (LIB.exe) açıklar.  
  
 [EDITBIN Başvurusu](../../build/reference/editbin-reference.md)  
 Microsoft COFF ikili dosya Düzenleyicisi'ni (EDITBIN. açıklar EXE), ortak nesne dosyası biçimi (COFF) ikili dosyalarını değiştirir.  
  
 [DUMPBIN Başvurusu](../../build/reference/dumpbin-reference.md)  
 Microsoft COFF ikili dosya Dumper (DUMPBIN. açıklar EXE), ortak nesne dosyası biçimi (COFF) ikili dosyaları hakkındaki bilgileri görüntüler.  
  
 [NMAKE Başvurusu](../../build/nmake-reference.md)  
 Microsoft Program Bakımı yardımcı programı'nı (NMAKE. açıklar EXE) olduğu projeleri derlemeler bir aracı tanım dosyasında yer alan komutları göre.