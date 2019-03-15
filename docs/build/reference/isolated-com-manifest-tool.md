---
title: Bildirim aracı yalıtılmış COM özellikleri
ms.date: 12/10/2018
f1_keywords:
- VC.Project.VCManifestTool.RegistrarScriptFile
- VC.Project.VCManifestTool.ComponentFileName
- VC.Project.VCManifestTool.TypeLibraryFile
- VC.Project.VCManifestTool.ReplacementsFile
ms.assetid: 457582b8-cfde-49c0-92e3-3a6b9e8c08eb
ms.openlocfilehash: 2fda169ecf304373d27d699bf313bde124dc399f
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57824037"
---
# <a name="isolated-com-manifest-tool-configuration-properties-ltprojectnamegt-property-pages-dialog-box"></a>Yalıtılmış COM, bildirim aracı, yapılandırma özellikleri, &lt;Projectname&gt; özellik sayfaları iletişim kutusu

Bu iletişim kutusunu belirtin kullanacağınız **yalıtılmış COM** seçenekleri [Mt.exe](https://msdn.microsoft.com/library/aa375649).

Bu özellik sayfası iletişim kutusu erişmek için projenizi veya, özellik sayfası için özellik sayfalarını açın. Genişletin **bildirim aracında** düğümünde **ortak özellikler**ve ardından **yalıtılmış COM**.

## <a name="task-list"></a>Görev Listesi

- [Nasıl yapılır: COM Bileşenlerini Kullanacak Yalıtılmış Uygulamalar Derleme](../how-to-build-isolated-applications-to-consume-com-components.md)

## <a name="uielement-list"></a>UIElement Listesi

- **Tür kitaplığı dosyası**

   Bildirim aracı, bildirim dosyası oluşturmak için kullanacağı tür kitaplığı dosyası (.tlb dosyası) adını belirtmek için/TLB seçeneğini kullanır.

- **Kaydedici betik dosyası**

   Bildirim aracı, bildirim dosyası oluşturmak için kullanacağı Kaydedici betik dosyasını (.rgs dosyası) adını belirtmek için /rgs seçeneğini kullanır.

- **Bileşen dosyası adı**

   Bildirim aracı üreten kaynağın adını belirtmek için/dll seçeneğini kullanır. Bu özellik için bir değer girin, ya da değerler **tür kitaplığı dosyası** veya **Kaydedici betik dosyasını** belirtilir.

- **Yenileme dosyası**

   /Replacements seçenek .rgs dosyasındaki değiştirilebilir dizeleri için değerler içeren dosyanın tam yolunu belirtmek için kullanır.

## <a name="see-also"></a>Ayrıca bkz.

[Yalıtılmış uygulamalar](/windows/desktop/SbsCs/isolated-applications)<br>
[ClickOnce Uygulama Bildirimi](/visualstudio/deployment/clickonce-application-manifest)<br>
[Bildirim Aracı özellik sayfaları](manifest-tool-property-pages.md)<br>
[C++ derleyicisi ayarlayın ve derleme Visual Studio özellikleri](../working-with-project-properties.md)
