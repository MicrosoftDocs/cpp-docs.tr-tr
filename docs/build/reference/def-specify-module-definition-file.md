---
title: -DEF (modül tanım dosyasını belirt) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.ModuleDefinitionFile
- /def
dev_langs:
- C++
helpviewer_keywords:
- module definition files, specifying
- DEF linker option
- -DEF linker option
- module definition files
- /DEF linker option
ms.assetid: 6497fa68-65f0-48ca-8f66-b87166fc631a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0ec7458f5b81dd2b9d5aac49959b935f49377081
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45720420"
---
# <a name="def-specify-module-definition-file"></a>/DEF (Modül Tanım Dosyasını Belirt)

```
/DEF:filename
```

## <a name="arguments"></a>Arguments

*Dosya adı*<br/>
Modül tanım dosyasını (.def) bağlayıcıya geçirilecek adı.

## <a name="remarks"></a>Açıklamalar

/ DEF seçeneği modül tanım dosyasını (.def) bağlayıcıya iletir. BAĞLANTI için yalnızca bir .def dosyası belirtilebilir. .Def dosyaları hakkında daha fazla ayrıntı için bkz: [modül-tanımlama dosyaları](../../build/reference/module-definition-dot-def-files.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).

1. Tıklayın **bağlayıcı** klasör.

1. Tıklayın **giriş** özellik sayfası.

1. Değiştirme **modül tanım dosyası** özelliği.

Geliştirme ortamında bir .def dosyası belirtmek için birlikte diğer dosyalar projeye ekleyin ve ardından/DEF seçeneği dosyayı belirtin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ModuleDefinitionFile%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)