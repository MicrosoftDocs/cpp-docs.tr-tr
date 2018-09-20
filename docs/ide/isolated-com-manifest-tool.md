---
title: Bildirim aracı yalıtılmış COM özellikleri (Visual C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.VCManifestTool.RegistrarScriptFile
- VC.Project.VCManifestTool.ComponentFileName
- VC.Project.VCManifestTool.TypeLibraryFile
- VC.Project.VCManifestTool.ReplacementsFile
dev_langs:
- C++
ms.assetid: 457582b8-cfde-49c0-92e3-3a6b9e8c08eb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cdb472ce082809a48dd3e42afd4481149eff3a28
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46407564"
---
# <a name="isolated-com-manifest-tool-configuration-properties-ltprojectnamegt-property-pages-dialog-box"></a>Yalıtılmış COM, bildirim aracı, yapılandırma özellikleri, &lt;Projectname&gt; özellik sayfaları iletişim kutusu

Bu iletişim kutusunu belirtin kullanacağınız **yalıtılmış COM** seçenekleri [Mt.exe](https://msdn.microsoft.com/library/aa375649).

Bu özellik sayfası iletişim kutusu erişmek için projenizi veya, özellik sayfası için özellik sayfalarını açın. Genişletin **bildirim aracında** düğümünde **ortak özellikler**ve ardından **yalıtılmış COM**.

## <a name="task-list"></a>Görev Listesi

- [Nasıl Yapılır: COM Bileşenlerini Kullanacak Yalıtılmış Uygulamalar Derleme](../build/how-to-build-isolated-applications-to-consume-com-components.md)

## <a name="uielement-list"></a>UIElement Listesi

- **Tür kitaplığı dosyası**

   Bildirim aracı, bildirim dosyası oluşturmak için kullanacağı tür kitaplığı dosyası (.tlb dosyası) adını belirtmek için/TLB seçeneğini kullanır.

- **Kaydedici betik dosyası**

   Bildirim aracı, bildirim dosyası oluşturmak için kullanacağı Kaydedici betik dosyasını (.rgs dosyası) adını belirtmek için /rgs seçeneğini kullanır.

- **Bileşen dosyası adı**

   Bildirim aracı üreten kaynağın adını belirtmek için/dll seçeneğini kullanır. Bu özellik için bir değer girin, ya da değerler **tür kitaplığı dosyası** veya **Kaydedici betik dosyasını** belirtilir.

- **Yenileme dosyası**

   /Replacements seçenek .rgs dosyasındaki değiştirilebilir dizeleri için değerler içeren dosyanın tam yolunu belirtmek için kullanır.

## <a name="see-also"></a>Ayrıca Bkz.

[Yalıtılmış uygulamalar](/windows/desktop/SbsCs/isolated-applications)<br>
[ClickOnce Uygulama Bildirimi](/visualstudio/deployment/clickonce-application-manifest)<br>
[Bildirim Aracı özellik sayfaları](../ide/manifest-tool-property-pages.md)<br>
[Proje Özellikleriyle Çalışma](../ide/working-with-project-properties.md)