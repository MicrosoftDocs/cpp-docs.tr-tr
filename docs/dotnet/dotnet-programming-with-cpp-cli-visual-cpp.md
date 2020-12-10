---
title: C++/CLI ile .NET programlama
description: C++/CLı kullanarak Visual Studio 'da .NET uygulamaları ve bileşenleri oluşturma hakkında bilgi edinin.
ms.date: 12/08/2020
helpviewer_keywords:
- programming [C++], .NET programming
- .NET Framework [C++]
- .NET applications [C++]
- Visual C++, .NET programming
ms.openlocfilehash: 80a9743016976e307158608134155dc7272d44a8
ms.sourcegitcommit: 754df5278f795f661d4eeb0d4cacc908aa630159
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/09/2020
ms.locfileid: "96933189"
---
# <a name="net-programming-with-ccli"></a>C++/CLI ile .NET programlama

::: moniker range="msvc-140"

Varsayılan olarak, 4.5.2 .NET Framework Visual Studio 2015 Target ile oluşturulan CLR projeleri. Yeni bir proje oluştururken .NET Framework 4,6 ' i hedefleyebilirsiniz. **Yeni proje** iletişim kutusunda, iletişim kutusunun üst ortasındaki açılan menüde hedef çerçevesini değiştirin. Mevcut bir projenin hedef çerçevesini değiştirmek için projeyi kapatın, proje dosyasını ( *`.vcxproj`* ) düzenleyin ve hedef Framework sürümü değerini 4,6 olarak değiştirin. Değişiklikler projeyi bir sonraki açışınızda etkili olur.

::: moniker-end
::: moniker range="msvc-150"

Visual Studio 2017 ' de, varsayılan hedef .NET Framework 4.6.1 ' dir. Framework sürüm Seçicisi, **Yeni proje** iletişim kutusunun en altında bulunur.

## <a name="install-ccli-support-in-visual-studio-2017"></a>Visual Studio 2017 ' de C++/CLı desteğini yükler

C++/CLı, Visual Studio C++ iş yükünü yüklediğinizde varsayılan olarak yüklenmez. Visual Studio yüklendikten sonra bileşeni yüklemek için Visual Studio Yükleyicisi açın. Visual Studio 'nun yüklü sürümünüzün yanındaki **Değiştir** düğmesini seçin. **Yüklü bileşenler** sekmesini seçin. **Derleyiciler, derleme araçları ve çalışma zamanları** bölümüne gidin ve **C++/CLI desteği**' ni seçin. Visual Studio 'Yu güncelleştirmek için **Değiştir** ' i seçin.

::: moniker-end
::: moniker range="msvc-160"

Visual Studio 2019 ' de, .NET Core projeleri için varsayılan hedef Framework 5,0 ' dir. .NET Framework projeleri için varsayılan değer 4.7.2 ' dir. .NET Framework sürüm Seçicisi **Yeni proje oluştur** iletişim kutusunun **yeni projenizi yapılandırın** sayfasında bulunur.
## <a name="install-ccli-support-in-visual-studio-2019"></a>Visual Studio 2019 ' de C++/CLı desteğini yükler

C++/CLı, Visual Studio C++ iş yükünü yüklediğinizde varsayılan olarak yüklenmez. Visual Studio yüklendikten sonra bileşeni yüklemek için Visual Studio Yükleyicisi açın. Visual Studio 'nun yüklü sürümünüzün yanındaki **Değiştir** düğmesini seçin. **Yüklü bileşenler** sekmesini seçin. **Derleyiciler, derleme araçları ve çalışma zamanları** bölümüne gidin ve **v142 derleme araçları bileşeni için en son C++/CLI desteğini** seçin. Visual Studio 'Yu güncelleştirmek için **Değiştir** ' i seçin.

::: moniker-end

## <a name="in-this-section"></a>Bu bölümde

[C++/CLI görevleri](../dotnet/cpp-cli-tasks.md)

[Yerel ve.NET birlikte çalışabilirliği](../dotnet/native-and-dotnet-interoperability.md)

[Saf ve Doğrulanabilen kod (C++/CLı)](../dotnet/pure-and-verifiable-code-cpp-cli.md)

[Normal ifadeler (C++/CLı)](../dotnet/regular-expressions-cpp-cli.md)

[Dosya işleme ve g/ç (C++/CLı)](../dotnet/file-handling-and-i-o-cpp-cli.md)

[Grafik işlemleri (C++/CLı)](../dotnet/graphics-operations-cpp-cli.md)

[Windows işlemleri (C++/CLı)](../dotnet/windows-operations-cpp-cli.md)

[ADO.NET kullanarak veri erişimi (C++/CLı)](../dotnet/data-access-using-adonet-cpp-cli.md)

[Diğer .NET dilleri ile birlikte çalışabilirlik (C++/CLı)](../dotnet/interoperability-with-other-dotnet-languages-cpp-cli.md)

[Seri Hale Getirme (C++/CLI)](../dotnet/serialization-cpp-cli.md)

[Yönetilen türler (C++/CLı)](../dotnet/managed-types-cpp-cli.md)

[Yansıma (C++/CLI)](../dotnet/reflection-cpp-cli.md)

[Tanımlayıcı ad derlemeleri (derleme imzalama) (C++/CLı)](../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md)

[Hata ayıklama sınıfı (C++/CLı)](../dotnet/debug-class-cpp-cli.md)

[STL/CLR kitaplık başvurusu](../dotnet/stl-clr-library-reference.md)

[C++ destek kitaplığı](../dotnet/cpp-support-library.md)

[C++/CLI Özel Durumları](../dotnet/exceptions-in-cpp-cli.md)

[Kutulama (C++/CLI)](../dotnet/boxing-cpp-cli.md)

## <a name="see-also"></a>Ayrıca bkz.

[Yerel ve.NET birlikte çalışabilirliği](../dotnet/native-and-dotnet-interoperability.md)
