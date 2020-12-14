---
description: 'Daha fazla bilgi edinin: genel özellik sayfası (dosya)'
title: Genel Özellik Sayfası (Dosya)
ms.date: 08/30/2019
f1_keywords:
- VC.Project.VCFileConfiguration.ExcludedFromBuild
- VC.Project.VCFileConfiguration.Tool
ms.assetid: 26e3711e-9e7d-4e8d-bc4c-2474538efdad
ms.openlocfilehash: 03b91a028bce5423bcf80fab24153a36eb7435e8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200344"
---
# <a name="general-property-page-file"></a>Genel Özellik Sayfası (Dosya)

Bu konu, Windows projeleri için geçerlidir. Windows dışı projeler için bkz. [Linux C++ Özellik sayfası başvurusu](../../linux/prop-pages-linux.md).

**Çözüm Gezgini** bir dosya düğümüne sağ tıkladığınızda, **yapılandırma özellikleri** düğümü altındaki **genel** Özellik sayfası açılır. Aşağıdaki özellikleri içerir:

- **Derlemeden hariç tutuldu**

   Dosyanın geçerli yapılandırma için yapıda olması gerekip gerekmediğini belirtir.

   Bu özelliğe programlı bir şekilde erişmek için bkz <xref:Microsoft.VisualStudio.VCProjectEngine.VCFileConfiguration.ExcludedFromBuild%2A> ..

- **İçerik** (yalnızca UWP uygulamaları için geçerlidir.) Dosyanın uygulama paketine dahil edilecek içerik içerip içermediğini belirtir.

- **Öğe türü**

   **Öğe türü** , derleme işlemi sırasında dosyayı işlemek için kullanılacak aracı belirtir. [Uzantısı Visual Studio tarafından bilinen dosyaların](/visualstudio/extensibility/visual-cpp-project-extensibility#project-items) bu özellikte varsayılan bir değeri vardır. Özel bir dosya türüne sahipseniz veya bilinen bir dosya türü için varsayılan aracı geçersiz kılmak istiyorsanız burada özel bir araç belirtebilirsiniz. Daha fazla bilgi için bkz. [özel derleme araçları belirtme](../specifying-custom-build-tools.md) . Bu özellik sayfasını, bir dosyanın yapı sürecinin bir parçası olmadığı belirtmek için de kullanabilirsiniz.

   Aşağıdaki çizimde bir *. cpp* dosyası için özellik sayfası gösterilmektedir. Bu dosya türü için varsayılan **öğe türü** **C/C++ derleyicisidir** (*cl.exe*) ve özellik sayfası yalnızca bu dosyaya uygulanabilen çeşitli derleyici ayarlarını gösterir.

   ![Proje öğesi için genel özellik sayfası](media/file-general-item-type.png "Öğe türü seçenekleri")

    Aşağıdaki tabloda varsayılan öğe türleri listelenmektedir:

    |Dosya uzantısı|Öğe türü|Varsayılan araç|
    |-|-|-|
    |.appx|XAML uygulama tanımı|[Uygulama paketleyicisi](/windows/win32/appxpkg/make-appx-package--makeappx-exe-)|
    |. HLSL,. cso|HLSL derleyicisi|[fxc.exe](/windows/win32/direct3dtools/fxc)|
    |. h|C/C++ üst bilgisi|[C/C++ ön Işlemcisi](../../preprocessor/c-cpp-preprocessor-reference.md)|
    |yok|Derlemede yer almaz|yok|
    |. xml,. XSLT,. Xsl|Xml|[XML Düzenleyicisi](/visualstudio/xml-tools/xml-editor)|
    |. resw,. resjson|PRı kaynağı (UWP uygulamaları)|[MakePri.exe](/windows/uwp/app-resources/compile-resources-manually-with-makepri)|
    ||Medya (UWP)|[Uygulama paketleyicisi](/windows/win32/appxpkg/make-appx-package--makeappx-exe-)|
    |. xsd|XML veri Oluşturucu aracı|[XML şema tanımı Aracı (Xsd.exe)](/dotnet/standard/serialization/xml-schema-definition-tool-xsd-exe) (.NET iş yükü gerektirir. MSVC 'e dahil değildir.)|
    ||Bildirim Aracı|[mt.exe](/windows/win32/sbscs/mt-exe)|
    |. RC|Kaynak|[Windows Kaynak derleyicisi (rc.exe)](/windows/win32/menurc/resource-compiler)|
    |. appxmanifest|Uygulama paketi bildirimi|[Uygulama paketleyicisi](/windows/win32/appxpkg/make-appx-package--makeappx-exe-)|
    |.obj|Nesne|[C/C++ Bağlayıcısı (link.exe)](cl-invokes-the-linker.md)|
    |. ttf|Yazı tipi|yok|
    |.txt|Metin|yok|
    |yok|Özel yapı aracı|Kullanıcı tanımlı|
    |yok|Dosyayı Kopyala|yok|
    |. packagelayout|Uygulama paketi düzeni|[Uygulama paketleyicisi](/windows/win32/appxpkg/make-appx-package--makeappx-exe-)|
    |.resx|Derleyici tarafından yönetilen kaynak|[Resgen.exe (kaynak dosya Oluşturucu)](/dotnet/framework/tools/resgen-exe-resource-file-generator)|
    |. natvis|C++ hata ayıklayıcısı görselleştirme dosyası|[Natvis çerçevesi](/visualstudio/debugger/create-custom-views-of-native-objects)|
    |. jpg,. bmp,. ico, vb.|Görüntü|Uygulama türünü temel alan kaynak derleyicisi.|
    |. cpp|C/C++ derleyicisi|cl.exe|

   Bu özelliğe programlı bir şekilde erişmek için bkz <xref:Microsoft.VisualStudio.VCProjectEngine.VCFileConfiguration.Tool%2A> ..

**Yapılandırma özellikleri** düğümü altındaki **genel** Özellik sayfasına erişme hakkında daha fazla bilgi Için bkz. [Visual Studio 'da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

## <a name="see-also"></a>Ayrıca bkz.

[C++ proje özellik sayfası başvurusu](property-pages-visual-cpp.md)
