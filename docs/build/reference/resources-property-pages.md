---
description: 'Daha fazla bilgi için: kaynaklar özellik sayfası'
title: Kaynaklar
ms.date: 08/28/2019
ms.topic: article
ms.assetid: dade2f6b-c51f-4c33-9023-41956ae4b5f6
f1_keywords:
- VC.Project.VCResourceCompilerTool.PreprocessorDefinitions
- VC.Project.VCResourceCompilerTool.UndefineProcessorDefinitions
- VC.Project.VCResourceCompilerTool.Culture
- VC.Project.VCResourceCompilerTool.AdditionalIncludeDirectories
- VC.Project.VCResourceCompilerTool.IgnoreStandardIncludePath
- VC.Project.VCResourceCompilerTool.ShowProgress
- VC.Project.VCResourceCompilerTool.SuppressStartupBanner
- VC.Project.VCResourceCompilerTool.ResourceOutputFileName
- VC.Project.VCResourceCompilerTool.NullTerminateStrings
- vc.project.AdditionalOptionsPage
ms.openlocfilehash: d074cbb6035bd138ca322197e50e9a3f892b325b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225108"
---
# <a name="resources-property-page"></a>Kaynaklar özellik sayfası

Yerel Windows Masaüstü programlarında, derleme, ikili dosyaya görüntü, dize tabloları ve *. res* dosyaları eklemek Için [kaynak derleyicisini (rc.exe)](/windows/win32/menurc/resource-compiler) çağırır. Bu özellik sayfasında gösterilen özellikler, C++ derleyicisine veya bağlayıcıya değil kaynak derleyiciye geçirilir. Burada listelenen özellikler ve RC komut satırı seçeneklerine nasıl eşlendikleri hakkında daha fazla bilgi için bkz. [RC kullanma (rc komut satırı)](/windows/win32/menurc/using-rc-the-rc-command-line-). **Kaynak** özelliği sayfalarına erişme hakkında daha fazla bilgi için bkz. [Visual Studio 'da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md). Bu özelliklere programlı bir şekilde erişmek için bkz <xref:Microsoft.VisualStudio.VCProjectEngine.VCResourceCompilerTool> ..

C++/CLı uygulamalarında .NET kaynaklarının özellikleri, [yönetilen kaynaklar özellik sayfasında](managed-resources-property-page.md)gösterilir.

## <a name="preprocessor-definitions"></a>Önişlemci tanımları

Kaynak derleyicisi için bir veya daha fazla tanımlar belirtir. (/d [makro])

## <a name="undefine-preprocessor-definitions"></a>Önişlemci tanımlarının tanımı kaldırılıyor

Bir simgenin tanımlanunnu kaldır. p

## <a name="culture"></a>Kültür

Kaynaklarda kullanılan kültürü (ABD Ingilizcesi veya Italyanca gibi) listeler. (/l [sayı])

## <a name="additional-include-directories"></a>Ek Içerme dizinleri

Ekleme yoluna eklenecek bir veya daha fazla dizin belirtir; birden fazlaysa noktalı virgül sınırlayıcısı kullanın. (/I [yol])

## <a name="ignore-standard-include-paths"></a>Standart Içerme yollarını yoksay

Kaynak derleyicisinin ıNCLUDE ortam değişkenlerinde belirtilen dizinlerde bulunan içerme dosyalarını aramasını engeller. /X

## <a name="show-progress"></a>Ilerlemeyi göster

İlerleme iletilerini çıkış penceresine gönder. çıktıda

## <a name="suppress-startup-banner"></a>Başlangıç başlığını gösterme

Başlangıç başlığının ve bilgi iletisinin görüntülenmesini engelle (/nologo)

## <a name="resource-file-name"></a>Kaynak dosya adı

Kaynak dosyasının adını belirtir (/fo [dosya])

## <a name="null-terminate-strings"></a>Null sonlandırma dizeleri

Dize tablolarındaki tüm dizelere null değeri ekleyin. /n

## <a name="see-also"></a>Ayrıca bkz.

[C++ proje özellik sayfası başvurusu](property-pages-visual-cpp.md)
