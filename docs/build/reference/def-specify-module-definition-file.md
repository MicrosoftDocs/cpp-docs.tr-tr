---
description: Daha fazla bilgi edinin:/DEF (Module-Definition dosyası belirtin)
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
ms.openlocfilehash: 3b9178004621a55f999f7c2636eaa5b697d2de98
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201709"
---
# <a name="def-specify-module-definition-file"></a>/DEF (Modül Tanım Dosyasını Belirt)

```
/DEF:filename
```

## <a name="arguments"></a>Arguments

*filename*<br/>
Bağlayıcıya geçirilecek modül tanımı dosyası (. def) adı.

## <a name="remarks"></a>Açıklamalar

/DEF seçeneği bir modül tanım dosyasını (. def) bağlayıcıya geçirir. BAĞLAMAK için yalnızca bir. def dosyası belirtilebilir. . Def dosyaları hakkında daha fazla bilgi için bkz. [modül tanım dosyaları](module-definition-dot-def-files.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Bağlayıcı** klasörüne tıklayın.

1. **Giriş** Özellik sayfasına tıklayın.

1. **Modül tanım dosyası** özelliğini değiştirin.

Geliştirme ortamının içinden bir. def dosyası belirtmek için, bunu projeye diğer dosyalarla birlikte eklemeniz ve sonra dosyayı/DEF seçeneğine belirtmeniz gerekir.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ModuleDefinitionFile%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
