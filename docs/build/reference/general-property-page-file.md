---
title: Genel Özellik Sayfası (Dosya)
ms.date: 08/30/2019
f1_keywords:
- VC.Project.VCFileConfiguration.ExcludedFromBuild
- VC.Project.VCFileConfiguration.Tool
ms.assetid: 26e3711e-9e7d-4e8d-bc4c-2474538efdad
ms.openlocfilehash: 41366e2eae479c3d00f79cc47da9100b22129d50
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70218186"
---
# <a name="general-property-page-file"></a>Genel Özellik Sayfası (Dosya)

Bu konu, Windows projeleri için geçerlidir. Windows dışı projeler için bkz. [Linux C++ Özellik sayfası başvurusu](../../linux/prop-pages-linux.md).

**Çözüm Gezgini**bir dosya düğümüne sağ tıkladığınızda, **yapılandırma özellikleri** düğümü altındaki **genel** Özellik sayfası açılır. Aşağıdaki özellikleri içerir:

- **Derlemeden hariç tutuldu**

   Dosyanın geçerli yapılandırma için yapıda olması gerekip gerekmediğini belirtir.

   Bu özelliğe programlı bir şekilde erişmek için <xref:Microsoft.VisualStudio.VCProjectEngine.VCFileConfiguration.ExcludedFromBuild%2A>bkz.

- **İçerik** (Yalnızca UWP uygulamaları için geçerlidir.) Dosyanın uygulama paketine dahil edilecek içerik içerip içermediğini belirtir.

- **Öğe türü**

   **Öğe türü** , derleme işlemi sırasında dosyayı işlemek için kullanılacak aracı belirtir. [Uzantısı Visual Studio tarafından bilinen dosyaların](/visualstudio/extensibility/visual-cpp-project-extensibility?view=vs-2019#project-items) bu özellikte varsayılan bir değeri vardır. Özel bir dosya türüne sahipseniz veya bilinen bir dosya türü için varsayılan aracı geçersiz kılmak istiyorsanız burada özel bir araç belirtebilirsiniz. Daha fazla bilgi için bkz. [özel derleme araçları belirtme](../specifying-custom-build-tools.md) . Bu özellik sayfasını, bir dosyanın yapı sürecinin bir parçası olmadığı belirtmek için de kullanabilirsiniz.

   Aşağıdaki çizimde bir *. cpp* dosyası için özellik sayfası gösterilmektedir. Bu dosya türü için varsayılan **öğe türü** **C/C++ derleyicidir** (*CL. exe*) ve özellik sayfası yalnızca bu dosyaya uygulanabilen çeşitli derleyici ayarlarını gösterir.

   ![Proje öğesi Için genel özellik sayfası](media/file-general-item-type.png "Öğe türü seçenekleri")

    Aşağıdaki tabloda varsayılan öğe türleri listelenmektedir:

    |Dosya Uzantısı|Öğe türü|Varsayılan araç|
    |-|-|-|
    |. appx|XAML uygulama tanımı|[Uygulama paketleyicisi](/windows/win32/appxpkg/make-appx-package--makeappx-exe-)|
    |. HLSL,. cso|HLSL derleyicisi|[fxc. exe](/windows/win32/direct3dtools/fxc)|
    |. h|C/C++ üst bilgi|[C/C++ Ön İşlemcisi](../../preprocessor/c-cpp-preprocessor-reference.md)|
    |yok|Derlemede yer almaz|yok|
    |. xml,. XSLT,. Xsl|Xml|[XML Düzenleyicisi](/visualstudio/xml-tools/xml-editor)|
    |. resw,. resjson|PRı kaynağı (UWP uygulamaları)|[MakePri. exe](/windows/uwp/app-resources/compile-resources-manually-with-makepri)|
    ||Medya (UWP)|[Uygulama paketleyicisi](/windows/win32/appxpkg/make-appx-package--makeappx-exe-)|
    |. xsd|XML veri Oluşturucu aracı|[XML şema tanımı Aracı (xsd. exe)](/dotnet/standard/serialization/xml-schema-definition-tool-xsd-exe) (.NET iş yükü gerektirir. MSVC 'e dahil değildir.)|
    ||Bildirim Aracı|[mt. exe](/windows/win32/sbscs/mt-exe)|
    |. RC|Kaynak|[Windows Kaynak derleyicisi (RC. exe)](/windows/win32/menurc/resource-compiler)|
    |. appxmanifest|Uygulama paketi bildirimi|[Uygulama paketleyicisi](/windows/win32/appxpkg/make-appx-package--makeappx-exe-)|
    |.obj|Nesne|[C/C++ bağlayıcı (LINK. exe)](cl-invokes-the-linker.md)|
    |. ttf|Yazý|yok|
    |c|Metin|yok|
    |yok|Özel yapı aracı|Kullanıcı tanımlı|
    |yok|Dosyayı Kopyala|yok|
    |. packagelayout|Uygulama paketi düzeni|[Uygulama paketleyicisi](/windows/win32/appxpkg/make-appx-package--makeappx-exe-)|
    |.resx|Derleyici tarafından yönetilen kaynak|[Resgen.exe (Kaynak Dosya Oluşturucu)](/dotnet/framework/tools/resgen-exe-resource-file-generator)|
    |. natvis|C++Hata ayıklayıcı görselleştirme dosyası|[Natvis çerçevesi](/visualstudio/debugger/create-custom-views-of-native-objects)|
    |. jpg,. bmp,. ico, vb.|Görüntü|Uygulama türünü temel alan kaynak derleyicisi.|
    |. cpp|C/C++ derleyici|CL. exe|

   Bu özelliğe programlı bir şekilde erişmek için <xref:Microsoft.VisualStudio.VCProjectEngine.VCFileConfiguration.Tool%2A>bkz.

**Yapılandırma özellikleri** düğümü altındaki **genel** Özellik sayfasına erişme hakkında daha fazla bilgi Için bkz. [Visual Studio 'Da C++ derleyici ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

## <a name="see-also"></a>Ayrıca bkz.

[C++Proje özellik sayfası başvurusu](property-pages-visual-cpp.md)