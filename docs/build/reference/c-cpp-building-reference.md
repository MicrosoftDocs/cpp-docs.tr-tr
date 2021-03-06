---
title: C/C++ oluşturma başvurusu - Visual Studio
description: Visual Studio'da C/C++ proje sistemi ve derleme araçları için başvuru içeriği.
ms.date: 05/06/2019
helpviewer_keywords:
- compiling source code [C++], additional information
- cl.exe compiler [C++], building programs
- linker [C++], building reference
- builds [C++], additional information
ms.assetid: 100b4ccf-572c-4d1f-970c-fa0bc0cc0d2d
ms.openlocfilehash: abe946ce516e915cd597a0f863c5949fed212bfa
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65221447"
---
# <a name="cc-building-reference"></a>C/C++ Oluşturma Başvurusu

Visual Studio C oluşturmanın iki yolu sağlar /C++ program. En kolay (ve yaygın) yolu [Visual Studio IDE içinden derleme](../creating-and-managing-visual-cpp-projects.md). Diğer yol ise [derleme komut satırı araçlarını kullanarak bir komut isteminden](../building-on-the-command-line.md). Her iki durumda da oluşturabilir ve kaynak dosyalarınızı Visual Studio veya seçtiğiniz üçüncü taraf bir düzenleyiciyi kullanarak düzenleyin.

## <a name="in-this-section"></a>Bu Bölümde

[C++ projeleri için MSBuild başvurusu](msbuild-visual-cpp-overview.md)

[MSVC Derleyicisi Başvurusu](compiling-a-c-cpp-program.md)<br/>
MSVC derleyicisi, makine kodu, bağlayıcı yönergeleri, bölümler, dış başvuruları ve işlev/veri adları içeren bir nesne dosyası oluşturur açıklar.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
Kod derleyici tarafından oluşturulan nesne dosyaları ve statik olarak bağlanan kitaplıklar birleştirir, bağlayıcı adı başvuruları giderir ve yürütülebilir bir dosya oluşturur.

[Derleyicide ve Bağlayıcıda Unicode Desteği](unicode-support-in-the-compiler-and-linker.md)

[Ek MSVC derleme araçları](c-cpp-build-tools.md)<br/>
C++ için ek komut satırı araçları.

[C/C++ Derleme Hataları](../../error-messages/compiler-errors-1/c-cpp-build-errors.md)<br/>
İçindekiler tablosunda derleme hataları bölüm tanıtır.

## <a name="related-sections"></a>İlgili Bölümler

[C/C++ Ön İşlemci Başvurusu](../../preprocessor/c-cpp-preprocessor-reference.md)<br/>
Önişlemci makroları, işleç ve yönergeleri çevirerek derleyici için kaynak dosyaları hazırlar açıklanır.

[Özel Derleme Adımlarını ve Derleme Olaylarını Anlama](../understanding-custom-build-steps-and-build-events.md)<br/>
Oluşturma işlemini özelleştirme açıklanır.

[C/C++ programı oluşturma](../projects-and-build-systems-cpp.md)<br/>
Programınızın komut satırından veya Visual Studio'nun tümleşik geliştirme ortamından oluşturmayı açıklayan konulara bağlantılar sağlar.

[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)<br/>
Geliştirme ortamında veya komut satırında derleyici seçeneklerini ayarlama açıklanır.

[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
Derleyici seçeneklerini kullanarak açıklayan konulara bağlantılar sağlar.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
Bağlayıcı seçeneklerini ayarlama içinde veya tümleşik geliştirme ortamı dışında açıklar.

[MSVC Bağlayıcı Seçenekleri](linker-options.md)<br/>
Bağlayıcı seçeneklerinin kullanımını açıklayan konulara bağlantılar sağlar.

[BSCMAKE Başvurusu](bscmake-reference.md)<br/>
Microsoft gözatma bilgileri bakım yardımcı programı (BSCMAKE. açıklanır .Sbr gözatma bilgisi dosyası (.bsc) oluşturur (EXE), derleme sırasında oluşturulan dosyalar.

[LIB Başvurusu](lib-reference.md)<br/>
Microsoft kitaplığı oluşturduğu ve yönettiği ortak nesne dosyası biçimi (COFF) nesne dosyası Kitaplığı Yöneticisi (LIB.exe) açıklar.

[EDITBIN Başvurusu](editbin-reference.md)<br/>
Microsoft COFF ikili dosya Düzenleyicisi'ni (EDITBIN. açıklar EXE), ikili dosyaları ortak nesne dosyası biçimi (COFF) değiştirir.

[DUMPBIN Başvurusu](dumpbin-reference.md)<br/>
Microsoft COFF ikili dosya Dumper (DUMPBIN. açıklar EXE), ikili dosyaları ortak nesne dosyası biçimi (COFF) ilgili bilgileri görüntüler.

[NMAKE Başvurusu](nmake-reference.md)<br/>
Microsoft Program Bakımı yardımcı programı'nı (NMAKE. açıklar EXE) olan bir araç olan projeleri derler tanım dosyasında yer alan komutları göre.
