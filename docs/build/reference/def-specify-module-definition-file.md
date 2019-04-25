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
ms.openlocfilehash: c08412fb50835485e7941b2bb1db088943387b71
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62272314"
---
# <a name="def-specify-module-definition-file"></a>/DEF (Modül Tanım Dosyasını Belirt)

```
/DEF:filename
```

## <a name="arguments"></a>Arguments

*Dosya adı*<br/>
Modül tanım dosyasını (.def) bağlayıcıya geçirilecek adı.

## <a name="remarks"></a>Açıklamalar

/ DEF seçeneği modül tanım dosyasını (.def) bağlayıcıya iletir. BAĞLANTI için yalnızca bir .def dosyası belirtilebilir. .Def dosyaları hakkında daha fazla ayrıntı için bkz: [modül-tanımlama dosyaları](module-definition-dot-def-files.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Tıklayın **bağlayıcı** klasör.

1. Tıklayın **giriş** özellik sayfası.

1. Değiştirme **modül tanım dosyası** özelliği.

Geliştirme ortamında bir .def dosyası belirtmek için birlikte diğer dosyalar projeye ekleyin ve ardından/DEF seçeneği dosyayı belirtin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ModuleDefinitionFile%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC Bağlayıcı Seçenekleri](linker-options.md)
