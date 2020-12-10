---
title: 'Nasıl yapılır: CLR Konsol Uygulamaları Oluşturma (C++/CLI)'
description: Visual Studio 'da C++/CLı kullanmak için CLR Konsol uygulaması projeleri oluşturmayı öğrenin.
ms.date: 12/08/2020
helpviewer_keywords:
- console applications, templates
- CLR console applications, project template
ms.openlocfilehash: ef74ca4cc31884543ff18d63d981504f36d1838e
ms.sourcegitcommit: 754df5278f795f661d4eeb0d4cacc908aa630159
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/09/2020
ms.locfileid: "96933228"
---
# <a name="how-to-create-clr-console-applications-ccli"></a>Nasıl yapılır: CLR Konsol Uygulamaları Oluşturma (C++/CLI)

::: moniker range="msvc-140"

**Yeni proje** Iletişim kutusundaki **clr konsol uygulaması** şablonunu, zaten temel proje başvuruları ve dosyaları olan bir konsol uygulaması projesi oluşturmak için kullanabilirsiniz.

::: moniker-end
::: moniker range="msvc-150"

**Yeni proje** Iletişim kutusundaki **clr konsol uygulaması** şablonunu, zaten temel proje başvuruları ve dosyaları olan bir konsol uygulaması projesi oluşturmak için kullanabilirsiniz.

C++/CLı desteği, bir Visual Studio C++ iş yükü yüklediğinizde varsayılan olarak yüklenmez. **Yeni proje** iletişim kutusunda Visual C++ altında bir clr başlığı görmüyorsanız, C++/CLI desteğini yüklemeniz gerekebilir. Daha fazla bilgi için bkz. [C++/CLI ile .NET programlama](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md).

::: moniker-end
::: moniker range="msvc-160"

Zaten temel proje başvuruları ve dosyaları olan bir konsol uygulaması projesi oluşturmak için **Yeni proje oluştur** Iletişim kutusunda **clr konsol uygulaması (.NET Framework)** şablonunu kullanabilirsiniz.

C++/CLı desteği, bir Visual Studio C++ iş yükü yüklediğinizde varsayılan olarak yüklenmez. **Yeni proje oluştur** ILETIŞIM kutusunda clr proje şablonları görmüyorsanız, C++/CLI desteğini yüklemeniz gerekebilir. Daha fazla bilgi için bkz. [C++/CLI ile .NET programlama](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md).

::: moniker-end

Genellikle, bir konsol uygulaması tek başına yürütülebilir bir dosyaya derlenir ancak grafik kullanıcı arabirimine sahip değildir. Kullanıcılar konsol uygulamasını bir komut isteminde çalıştırır. Çalışan uygulamaya yönergeler vermek için komut satırını kullanabilirler. Uygulama, komut penceresinde çıktı bilgilerini metin olarak sağlar. Konsol uygulamasının anında geri bildirimi, programlama öğrenmenin harika bir yolunu sunar. Grafik Kullanıcı arabirimini uygulama hakkında endişelenmeniz gerekmez.

::: moniker range="msvc-140"

Bir proje oluşturmak için CLR Konsol uygulaması şablonunu kullandığınızda, otomatik olarak bu başvuruları ve dosyaları ekler:

- Bu .NET Framework ad alanlarına başvurular:

  - <xref:System>, <xref:System.Data> , <xref:System.Xml> : Bu başvurular, yaygın olarak kullanılan türler, olaylar, arabirimler, öznitelikler ve özel durumlar tanımlayan temel sınıfları içerir.

  - *`mscorlib.dll`*: .NET Framework geliştirmeyi destekleyen derleme DLL 'SI.

- Kaynak dosyalar:

  - *`ConsoleApplicationName.cpp`*: Ana kaynak dosya ve giriş noktası uygulamaya. Bu dosya, projeniz için belirttiğiniz temel ada sahip. Proje DLL dosyasını ve proje ad alanını tanımlar. Bu dosyada kendi kodunuzu girin.

  - *`AssemblyInfo.cpp`*: Projenin derleme meta verilerini değiştirmek için kullanabileceğiniz öznitelikleri ve ayarları içerir. Daha fazla bilgi için bkz. [bütünleştirilmiş kod içeriği](/dotnet/framework/app-domains/assembly-contents).

  - *`stdafx.cpp`*: Adlı önceden derlenmiş bir üstbilgi dosyası *`ConsoleApplicationName.pch`* ve adında önceden derlenmiş bir tür dosyası oluşturmak için kullanılır *`stdafx.obj`* .

- Üst bilgi dosyaları:

  - *`stdafx.h`*: Adlı önceden derlenmiş bir üstbilgi dosyası *`ConsoleApplicationName.pch`* ve adında önceden derlenmiş bir tür dosyası oluşturmak için kullanılır *`stdafx.obj`* .

  - *`resource.h`*: İçin üretilen bir içerme dosyası *`app.rc`* .

- Kaynak dosyaları:

  - *`app.rc`*: Bir programın kaynak betik dosyası.

  - *`app.ico`*: Bir programın simge dosyası.

- *`ReadMe.txt`*: Projedeki dosyaları açıklar.

::: moniker-end
::: moniker range=">=msvc-150"

Bir proje oluşturmak için CLR Konsol uygulaması şablonunu kullandığınızda, otomatik olarak bu başvuruları ve dosyaları ekler:

- Bu .NET Framework ad alanlarına başvurular:

  - <xref:System>, <xref:System.Data> , <xref:System.Xml> : Bu başvurular, yaygın olarak kullanılan türler, olaylar, arabirimler, öznitelikler ve özel durumlar tanımlayan temel sınıfları içerir.

  - *`mscorlib.dll`*: .NET Framework geliştirmeyi destekleyen derleme DLL 'SI.

- Kaynak dosyalar:

  - *`ConsoleApplicationName.cpp`*: Ana kaynak dosya ve giriş noktası uygulamaya. Bu dosya, projeniz için belirttiğiniz temel ada sahip. Proje DLL dosyasını ve proje ad alanını tanımlar. Bu dosyada kendi kodunuzu girin.

  - *`AssemblyInfo.cpp`*: Projenin derleme meta verilerini değiştirmek için kullanabileceğiniz öznitelikleri ve ayarları içerir. Daha fazla bilgi için bkz. [bütünleştirilmiş kod içeriği](/dotnet/framework/app-domains/assembly-contents).

  - *`pch.cpp`*: Adlı önceden derlenmiş bir üstbilgi dosyası *`ConsoleApplicationName.pch`* ve adında önceden derlenmiş bir tür dosyası oluşturmak için kullanılır *`pch.obj`* .

- Üst bilgi dosyaları:

  - *`pch.h`*: Adlı önceden derlenmiş bir üstbilgi dosyası *`ConsoleApplicationName.pch`* ve adında önceden derlenmiş bir tür dosyası oluşturmak için kullanılır *`pch.obj`* .

  - *`Resource.h`*: İçin üretilen bir içerme dosyası *`app.rc`* .

- Kaynak dosyaları:

  - *`app.rc`*: Bir programın kaynak betik dosyası.

  - *`app.ico`*: Bir programın simge dosyası.

::: moniker-end

## <a name="to-create-a-clr-console-app-project"></a>CLR Konsol uygulaması projesi oluşturmak için

::: moniker range="msvc-140"

1. Menü çubuğunda **Dosya** > **Yeni** > **Proje**' yi seçin.

1. **Yeni proje** iletişim kutusunda, **yüklü** > **Şablonlar** > **Visual C++** > **clr** düğümünü seçin ve ardından **clr konsol uygulaması** şablonunu seçin.

1. **Ad** kutusuna uygulamanız için benzersiz bir ad girin.

   Diğer proje ve çözüm ayarlarını belirtebilirsiniz, ancak bunlar gerekli değildir.

1. Proje ve kaynak dosyalarını oluşturmak için **Tamam** düğmesini seçin.

::: moniker-end
::: moniker range="msvc-150"

1. Menü çubuğunda **Dosya** > **Yeni** > **Proje**' yi seçin.

1. **Yeni proje** iletişim kutusunda, **yüklü** > **Visual C++** > **clr** düğümünü seçin ve ardından **clr konsol uygulaması** şablonunu seçin.

1. **Ad** kutusuna uygulamanız için benzersiz bir ad girin.

   Diğer proje ve çözüm ayarlarını belirtebilirsiniz, ancak bunlar gerekli değildir.

1. Proje ve kaynak dosyalarını oluşturmak için **Tamam** düğmesini seçin.

::: moniker-end
::: moniker range="msvc-160"

1. Menü çubuğunda **Dosya** > **Yeni** > **Proje**' yi seçin.

1. **Yeni proje oluştur** iletişim kutusunda, arama kutusuna "clr konsolu" yazın. **Clr konsol uygulaması (.NET Framework)** şablonunu seçin ve ardından **İleri**' yi seçin.

1. **Ad** kutusuna uygulamanız için benzersiz bir ad girin.

   Diğer proje ve çözüm ayarlarını belirtebilirsiniz, ancak bunlar gerekli değildir.

1. Proje ve kaynak dosyalarını oluşturmak için **Oluştur** düğmesini seçin.

::: moniker-end

## <a name="see-also"></a>Ayrıca bkz.

[CLR projeleri](../build/reference/files-created-for-clr-projects.md)
