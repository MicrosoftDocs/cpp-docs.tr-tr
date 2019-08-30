---
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
ms.openlocfilehash: 916b6615d80000d601c909f771a1ec8f1b947927
ms.sourcegitcommit: e10a5feea193c249ddc5a6faba48e7c6d8784e73
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/30/2019
ms.locfileid: "70177345"
---
# <a name="resources-property-page"></a>Kaynaklar özellik sayfası

Yerel Windows Masaüstü programlarında, derleme, ikili dosyaya görüntü, dize tabloları ve *. res* dosyaları eklemek Için [kaynak derleyicisini (RC. exe)](/windows/win32/menurc/resource-compiler) çağırır. Bu özellik sayfasında gösterilen özellikler, C++ derleyiciye veya bağlayıcıya değil kaynak derleyiciye geçirilir. Burada listelenen özellikler ve RC komut satırı seçeneklerine nasıl eşlendikleri hakkında daha fazla bilgi için bkz. [RC kullanma (rc komut satırı)](/windows/win32/menurc/using-rc-the-rc-command-line-). **Kaynak** özelliği sayfalarına erişme hakkında daha fazla bilgi için bkz. [Visual Studio C++ 'Da derleyici ve derleme özelliklerini ayarlama](../working-with-project-properties.md). Bu özelliklere programlı bir şekilde erişmek için <xref:Microsoft.VisualStudio.VCProjectEngine.VCResourceCompilerTool>bkz.

C++/CLı uygulamalarında .net kaynaklarının özellikleri, [yönetilen kaynaklar özellik sayfasında](managed-resources-property-page.md)gösterilir.

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

[C++Proje özellik sayfası başvurusu](property-pages-visual-cpp.md)