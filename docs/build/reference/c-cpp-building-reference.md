---
title: C/C++ oluşturma başvurusu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- compiling source code [C++], additional information
- cl.exe compiler [C++], building programs
- linker [C++], building reference
- builds [C++], additional information
ms.assetid: 100b4ccf-572c-4d1f-970c-fa0bc0cc0d2d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5935c0642ba0cd69992c68c521d284c3e8733ce4
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46390038"
---
# <a name="cc-building-reference"></a>C/C++ Oluşturma Başvurusu

Visual C++, C/C++ programı oluşturma iki yolu sağlar. En kolay (ve yaygın) yolu [Visual C++ geliştirme ortamında yapı](../../ide/building-cpp-projects-in-visual-studio.md). Diğer yol ise [derleme komut satırı araçlarını kullanarak bir komut isteminden](../../build/building-on-the-command-line.md). Her iki durumda da, kaynak dosyalarınızı Visual C++ kaynak Düzenleyicisi veya bir üçüncü taraf düzenleyiciyi kullanarak oluşturabilirsiniz.

Programınız bir .vcxproj dosyası yerine bir derleme görevleri dosyası kullanıyorsa, hala onu geliştirme ortamında oluşturabileceğinizi bir [dış proje](../../ide/building-external-projects.md).

## <a name="in-this-section"></a>Bu Bölümde

[C/C++ Programı Derleme](../../build/reference/compiling-a-c-cpp-program.md)<br/>
Makine kodu, bağlayıcı yönergeleri, bölümler, dış başvuruları ve işlev/veri adları içeren bir nesne dosyası oluşturan derleyici açıklar.

[Bağlama](../../build/reference/linking.md)<br/>
Kod derleyici tarafından oluşturulan nesne dosyaları ve statik olarak bağlanan kitaplıklar birleştirir, bağlayıcı adı başvuruları giderir ve yürütülebilir bir dosya oluşturur.

[Yayın Derlemeleri](../../build/reference/release-builds.md)<br/>
Neden ve ne zaman bir hata ayıklama'dan değiştirmek istiyorsunuz sunar bilgi yayın derlemesi için derleme ve ayrıca bazı hata ayıklama'dan bir yayın yapısı için değiştirilirken karşılaşabileceğiniz sorunlar açıklanır.

[Kodunuzu İyileştirme](../../build/reference/optimizing-your-code.md)<br/>
Kodu iyileştirme mekanizmaları açıklayan konulara bağlantılar sağlar:

[C/C++ Derleme Araçları](../../build/reference/c-cpp-build-tools.md)<br/>
Aşağıdaki komut satırı araçları, görüntüleme ya da yapı çıkış işleme için sağlar:

[C/C++ Derleme Hataları](../../error-messages/compiler-errors-1/c-cpp-build-errors.md)<br/>
İçindekiler tablosunda derleme hataları bölüm tanıtır.

## <a name="related-sections"></a>İlgili Bölümler

[C/C++ Ön İşlemci Başvurusu](../../preprocessor/c-cpp-preprocessor-reference.md)<br/>
Önişlemci makroları, işleç ve yönergeleri çevirerek derleyici için kaynak dosyaları hazırlar açıklanır.

[Özel Derleme Adımlarını ve Derleme Olaylarını Anlama](../../ide/understanding-custom-build-steps-and-build-events.md)<br/>
Oluşturma işlemini özelleştirme açıklanır.

[C/C++ programı oluşturma](../../build/building-c-cpp-programs.md)<br/>
Programınızın komut satırından veya Visual Studio'nun tümleşik geliştirme ortamından oluşturmayı açıklayan konulara bağlantılar sağlar.

[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)<br/>
Geliştirme ortamında veya komut satırında derleyici seçeneklerini ayarlama açıklanır.

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
Derleyici seçeneklerini kullanarak açıklayan konulara bağlantılar sağlar.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
Bağlayıcı seçeneklerini ayarlama içinde veya tümleşik geliştirme ortamı dışında açıklar.

[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)<br/>
Bağlayıcı seçeneklerinin kullanımını açıklayan konulara bağlantılar sağlar.

[BSCMAKE Başvurusu](../../build/reference/bscmake-reference.md)<br/>
Microsoft gözatma bilgileri bakım yardımcı programı (BSCMAKE. açıklanır .Sbr gözatma bilgisi dosyası (.bsc) oluşturur (EXE), derleme sırasında oluşturulan dosyalar.

[LIB Başvurusu](../../build/reference/lib-reference.md)<br/>
Microsoft kitaplığı oluşturduğu ve yönettiği ortak nesne dosyası biçimi (COFF) nesne dosyası Kitaplığı Yöneticisi (LIB.exe) açıklar.

[EDITBIN Başvurusu](../../build/reference/editbin-reference.md)<br/>
Microsoft COFF ikili dosya Düzenleyicisi'ni (EDITBIN. açıklar EXE), ikili dosyaları ortak nesne dosyası biçimi (COFF) değiştirir.

[DUMPBIN Başvurusu](../../build/reference/dumpbin-reference.md)<br/>
Microsoft COFF ikili dosya Dumper (DUMPBIN. açıklar EXE), ikili dosyaları ortak nesne dosyası biçimi (COFF) ilgili bilgileri görüntüler.

[NMAKE Başvurusu](../../build/nmake-reference.md)<br/>
Microsoft Program Bakımı yardımcı programı'nı (NMAKE. açıklar EXE) olan bir araç olan projeleri derler tanım dosyasında yer alan komutları göre.