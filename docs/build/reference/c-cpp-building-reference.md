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
ms.openlocfilehash: 116ddca6ed9f5e0b3ea02652958931f88cc8fc13
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45703228"
---
# <a name="cc-building-reference"></a>C/C++ Oluşturma Başvurusu

Visual C++, C/C++ programı oluşturma iki yolu sağlar. En kolay (ve yaygın) yolu [Visual C++ geliştirme ortamında yapı](../../ide/building-cpp-projects-in-visual-studio.md). Diğer yol ise [derleme komut satırı araçlarını kullanarak bir komut isteminden](../../build/building-on-the-command-line.md). Her iki durumda da, kaynak dosyalarınızı Visual C++ kaynak Düzenleyicisi veya bir üçüncü taraf düzenleyiciyi kullanarak oluşturabilirsiniz.

Programınız bir .vcxproj dosyası yerine bir derleme görevleri dosyası kullanıyorsa, hala onu geliştirme ortamında oluşturabileceğinizi bir [dış proje](../../ide/building-external-projects.md).

## <a name="in-this-section"></a>Bu Bölümde

[C/C++ programını derleme](../../build/reference/compiling-a-c-cpp-program.md) makine kodu, bağlayıcı yönergeleri, bölümler, dış başvuruları ve işlev/veri adları içeren bir nesne dosyası oluşturan derleyici açıklar.

[Bağlama](../../build/reference/linking.md) kod derleyici tarafından oluşturulan nesne dosyaları ve statik olarak bağlanan kitaplıklar birleştirir, bağlayıcı açıklar ad başvurularını çözümler ve yürütülebilir bir dosya oluşturur.

[Yayın derlemeleri](../../build/reference/release-builds.md) neden ve ne zaman bir yayın yapısı için hata ayıklama derlemeden değiştirmek istiyorsunuz hakkında bilgi gösterir ve ayrıca bazı karşılaşabileceğiniz hata ayıklama'dan bir yayın yapısı için değiştirirken sorunlar açıklanır.

[Kodunuzu iyileştirme](../../build/reference/optimizing-your-code.md) kod iyileştirmek için mekanizmaları açıklayan konulara bağlantılar sağlar:

[C/C++ derleme Araçları](../../build/reference/c-cpp-build-tools.md) görüntüleme ya da yapı çıkış işleme için aşağıdaki komut satırı araçları sağlar:

[C/C++ derleme hataları](../../error-messages/compiler-errors-1/c-cpp-build-errors.md) içindekiler tablosunda derleme hataları bölüm tanıtır.

## <a name="related-sections"></a>İlgili Bölümler

[C/C++ önişlemci başvurusu](../../preprocessor/c-cpp-preprocessor-reference.md) Önişlemci makroları, işleç ve yönergeleri çevirerek derleyici için kaynak dosyaları hazırlar açıklanır.

[Anlama özel derleme adımlarını ve derleme olaylarını](../../ide/understanding-custom-build-steps-and-build-events.md) Discusses oluşturma işlemini özelleştirme.

[C/C++ programı oluşturma](../../build/building-c-cpp-programs.md) programınızın komut satırından veya Visual Studio'nun tümleşik geliştirme ortamından oluşturmayı açıklayan konulara bağlantılar sağlar.

[Derleyici seçeneklerini ayarlama](../../build/reference/setting-compiler-options.md) geliştirme ortamında veya komut satırında derleyici seçeneklerini ayarlama açıklanmaktadır.

[Derleyici Seçenekleri](../../build/reference/compiler-options.md) derleyici seçeneklerini kullanarak açıklayan konulara bağlantılar sağlar.

[Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md) içinde veya tümleşik geliştirme ortamı dışında bağlayıcı seçeneklerini ayarlama açıklanmaktadır.

[Bağlayıcı seçenekleri](../../build/reference/linker-options.md) bağlayıcı seçeneklerinin kullanımını açıklayan konulara bağlantılar sağlar.

[BSCMAKE başvurusu](../../build/reference/bscmake-reference.md) Microsoft gözatma bilgileri bakım yardımcı programı (BSCMAKE. açıklanır .Sbr gözatma bilgisi dosyası (.bsc) oluşturur (EXE), derleme sırasında oluşturulan dosyalar.

[LIB başvurusu](../../build/reference/lib-reference.md) Microsoft kitaplığı oluşturduğu ve yönettiği ortak nesne dosyası biçimi (COFF) nesne dosyası Kitaplığı Yöneticisi (LIB.exe) açıklar.

[EDITBIN başvurusu](../../build/reference/editbin-reference.md) Microsoft COFF ikili dosya Düzenleyicisi'ni (EDITBIN. açıklar EXE), ikili dosyaları ortak nesne dosyası biçimi (COFF) değiştirir.

[DUMPBIN başvurusu](../../build/reference/dumpbin-reference.md) Microsoft COFF ikili dosya Dumper (DUMPBIN. açıklar EXE), ikili dosyaları ortak nesne dosyası biçimi (COFF) ilgili bilgileri görüntüler.

[NMAKE başvurusu](../../build/nmake-reference.md) Microsoft Program Bakımı yardımcı programı'nı (NMAKE. açıklar EXE) olan bir araç olan projeleri derler tanım dosyasında yer alan komutları göre.