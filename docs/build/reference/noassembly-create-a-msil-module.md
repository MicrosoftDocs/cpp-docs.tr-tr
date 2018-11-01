---
title: /NOASSEMBLY (MSIL Modülü Oluştur)
ms.date: 11/04/2016
f1_keywords:
- /NOASSEMBLY
- VC.Project.VCLinkerTool.TurnOffAssemblyGeneration
helpviewer_keywords:
- assemblies [C++]
- -NOASSEMBLY linker option
- /NOASSEMBLY linker option
- NOASSEMBLY linker option
- assemblies [C++], not creating an assembly
ms.assetid: 3cea4e70-f451-4395-a626-1930b1b127fe
ms.openlocfilehash: c1508de88b9678898990f0e5b946ad4ced8d6d24
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50582045"
---
# <a name="noassembly-create-a-msil-module"></a>/NOASSEMBLY (MSIL Modülü Oluştur)

```
/NOASSEMBLY
```

## <a name="remarks"></a>Açıklamalar

/ Noassembly seçeneği bağlayıcıya geçerli çıkış dosyası olmadan bir .NET Framework derlemesi için görüntü oluşturma söyler. Bir MSIL çıkış dosyası bir derleme bildirimi olmadan, bir modül adı verilir.

Varsayılan olarak, bir derleme oluşturulur. Ayrıca [/LN (MSIL modülü Oluştur)](../../build/reference/ln-create-msil-module.md) bir modül oluşturma derleyici seçeneği.

Bütünleştirilmiş kod oluşturmayı etkileyen diğer bağlayıcı seçenekleri şunlardır:

- [/ ASSEMBLYDEBUG](../../build/reference/assemblydebug-add-debuggableattribute.md)

- [/ ASSEMBLYLINKRESOURCE](../../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md)

- [/ ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)

- [/ ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md)

- [/ DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md)

- [/ KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)

- [/ KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).

1. Tıklayın **bağlayıcı** klasör.

1. Tıklayın **Gelişmiş** özellik sayfası.

1. Değiştirme **bütünleştirilmiş kod oluşturmayı devre dışı kapatma** özelliği.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TurnOffAssemblyGeneration%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)