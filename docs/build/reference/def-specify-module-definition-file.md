---
title: /DEF (Modül Tanım Dosyasını Belirt)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.ModuleDefinitionFile
- /def
helpviewer_keywords:
- module definition files, specifying
- DEF linker option
- -DEF linker option
- module definition files
- /DEF linker option
ms.assetid: 6497fa68-65f0-48ca-8f66-b87166fc631a
ms.openlocfilehash: 607af17a60612f69bb24708179bb453409098bde
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50654759"
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

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ModuleDefinitionFile%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)