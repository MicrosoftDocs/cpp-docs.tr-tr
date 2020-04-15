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
ms.openlocfilehash: c4a3048bfa07e9635662534b510fa57caa091f00
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81336084"
---
# <a name="resources-property-page"></a>Kaynaklar özellik sayfası

Yerel Windows masaüstü programları için yapı, [kaynak derleyicisini (rc.exe)](/windows/win32/menurc/resource-compiler) ikili ye resim, dize tabloları ve *.res* dosyalarını eklemek için çağırır. Bu özellik sayfasında açığa çıkan özellikler Kaynak Derleyicisine aktarılır, C++ derleyicisine veya bağlayıcıya değil. Burada listelenen özellikler ve RC komut satırı seçenekleriyle nasıl eşlendikleri hakkında daha fazla bilgi için [bkz.](/windows/win32/menurc/using-rc-the-rc-command-line-) **Kaynaklar** özellik sayfalarına nasıl erişilisin, [Bkz. C++ derleyicisi ayarla ve Visual Studio'da özellikler oluşturmak.](../working-with-project-properties.md) Bu özelliklere programlı olarak <xref:Microsoft.VisualStudio.VCProjectEngine.VCResourceCompilerTool>erişmek için bkz.

C++/CLI uygulamalarındaki .NET kaynaklarının özellikleri [Yönetilen Kaynaklar Özelliği Sayfasında](managed-resources-property-page.md)açıklanır.

## <a name="preprocessor-definitions"></a>Önişlemci Tanımları

Kaynak derleyicisi için bir veya daha fazla tanım belirtir. (/d[makro])

## <a name="undefine-preprocessor-definitions"></a>Tanımsız Önİşlemci Tanımları

Bir sembolü tanımlamıyor. (/u)

## <a name="culture"></a>Kültür

Kaynaklarda kullanılan kültürü (ABD İngilizcesi veya İtalyanca gibi) listeler. (/l [num])

## <a name="additional-include-directories"></a>Ek Dahil Dizinler

İçle yoluna eklenecek bir veya daha fazla dizin belirtir; birden fazla ise yarı kolon delimiter kullanın. (/I[yol])

## <a name="ignore-standard-include-paths"></a>Standardı Yoksay Yollar

Kaynak derleyicisinin INCLUDE ortam değişkenlerinde belirtilen dizinlere dahil dosyaları aramasını engeller. (/X)

## <a name="show-progress"></a>İlerlemeyi Göster

Çıkış penceresine ilerleme iletileri gönderin. (/v)

## <a name="suppress-startup-banner"></a>Başlangıç Banner'ı bastır

Başlangıç afişinin ve bilgi iletisinin (/nologo) görüntülenmesini bastırma

## <a name="resource-file-name"></a>Kaynak Dosya Adı

Kaynak dosyasının adını belirtir (/fo[dosya])

## <a name="null-terminate-strings"></a>Null Sonlandırma Dizeleri

Dize tablolarındaki tüm dizeleri için null's ekleme. (/n)

## <a name="see-also"></a>Ayrıca bkz.

[C++ proje özelliği sayfası başvurusu](property-pages-visual-cpp.md)
