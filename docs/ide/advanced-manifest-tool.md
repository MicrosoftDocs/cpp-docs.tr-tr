---
title: Gelişmiş, bildirim aracı, yapılandırma özellikleri, &lt;Projectname&gt; özellik sayfaları iletişim kutusu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.VCManifestTool.KeyFile
- VC.Project.VCManifestTool.UpdateFileHashes
- VC.Project.VCManifestTool.UpdateFileHashesSearchPath
- VC.Project.VCManifestTool.ValidateSignature
- VC.Project.VCManifestTool.KeyContainer
dev_langs:
- C++
ms.assetid: 3d587366-05ea-4956-a978-313069660735
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1e44ba6065658c085777ada39f75bd5fa1cdc2fb
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46382953"
---
# <a name="advanced-manifest-tool-configuration-properties-ltprojectnamegt-property-pages-dialog-box"></a>Gelişmiş, bildirim aracı, yapılandırma özellikleri, &lt;Projectname&gt; özellik sayfaları iletişim kutusu

Gelişmiş seçeneklerini belirtmek için bu iletişim kutusunu kullanın [Mt.exe](https://msdn.microsoft.com/library/aa375649).

Bu özellik sayfası iletişim kutusu erişmek için projenizi veya, özellik sayfası için özellik sayfalarını açın. Genişletin **bildirim aracında** düğümünde **yapılandırma özellikleri**ve ardından **Gelişmiş**.

## <a name="uielement-list"></a>UIElement Listesi

- **Dosya karmalarını güncelle**

   Bildirim aracı tarafından belirtilen dosya karması bilgi işlem olduğunu belirtmek için /hashupdate seçeneğini kullanan `<file>` öğeleri ve karma öznitelikleri hesaplanan değerle güncelleştirin.

- **Dosya karması arama yolunu güncelle**

   İçinde başvurulan dosyaları için arama yolunu belirtir `<file>` öğeleri. Bu seçenek ayrıca /hashupdate seçeneğini kullanır.

## <a name="see-also"></a>Ayrıca Bkz.

[\<Dosya > öğesi](/visualstudio/deployment/file-element-clickonce-application)<br>
[ClickOnce Uygulama Bildirimi](/visualstudio/deployment/clickonce-application-manifest)<br>
[Bildirim Aracı özellik sayfaları](../ide/manifest-tool-property-pages.md)<br>
[Proje Özellikleriyle Çalışma](../ide/working-with-project-properties.md)