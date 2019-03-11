---
title: Bildirim aracı yapılandırma özellikleri (Visual C++)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCManifestTool.MergeRulesFile
- VC.Project.VCManifestTool.UseUnicodeResponseFiles
- VC.Project.VCManifestTool.SuppressStartupBanner
- VC.Project.VCManifestTool.UseFAT32Workaround
- VC.Project.VCManifestTool.VerboseOutput
- VC.Project.VCManifestTool.AssemblyIdentity
ms.assetid: b99368a5-6819-482c-a06e-f2409290cfd1
ms.openlocfilehash: 9bd2f0bb67e06fbf462ea6a7779de07b2cc54592
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57745119"
---
# <a name="general-manifest-tool-configuration-properties-ltprojectnamegt-property-pages-dialog-box"></a>Genel, bildirim aracı, yapılandırma özellikleri, &lt;Projectname&gt; özellik sayfaları iletişim kutusu

Genel seçeneklerini belirtmek için bu iletişim kutusunu kullanın [Mt.exe](https://msdn.microsoft.com/library/aa375649).

Bu özellik sayfası iletişim kutusu erişmek için projenizi veya, özellik sayfası için özellik sayfalarını açın. Genişletin **bildirim aracında** düğümünde **yapılandırma özellikleri**ve ardından **genel**.

## <a name="uielement-list"></a>UIElement Listesi

- **Başlangıç başlığını gösterme**

   **Evet (/ nologo)** bildirim aracı başlatıldığında standart Microsoft telif hakkı verileri gizlenir belirtir. Bir yapı ortamı veya bir yapı işleminin bir parçası olarak mt.exe çalıştırdığınızda günlük dosyalarında istenmeyen çıkış gizlemek için bu seçeneği kullanın.

- **Ayrıntılı çıkış**

   **Evet (/ verbose)** bildirim oluşturulması sırasında ek yapı bilgilerini gösterileceğini belirtir.

- **Derleme kimliği**

   Bir kimlik dizesi belirtmek için /identity seçeneğini kullanan özniteliklerini oluşan [ \<assemblyIdentity > öğesi](/visualstudio/deployment/assemblyidentity-element-clickonce-application). Bir kimlik dizesi değeri ile başlayan `name` özniteliği ve takip *özniteliği* = *değer* çiftleri. Bir kimlik dizesi öznitelikleri virgülle sınırlandırılmıştır.

   Kimlik dizesi örneği verilmiştir:

   `Microsoft.Windows.Common-Controls, processorArchitecture=x86, version=6.0.0.0, type=win32, publicKeyToken=6595b64144ccf1df`

## <a name="see-also"></a>Ayrıca bkz.

[ClickOnce Uygulama Bildirimi](/visualstudio/deployment/clickonce-application-manifest)<br>
[Bildirim Aracı özellik sayfaları](../ide/manifest-tool-property-pages.md)<br>
[Proje Özellikleriyle Çalışma](../ide/working-with-project-properties.md)
