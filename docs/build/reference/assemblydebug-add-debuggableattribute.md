---
description: Şu konuda daha fazla bilgi edinin:/ASSEMBLYDEBUG (hata Ayıklıbağlantı Ekle)
title: /ASSEMBLYDEBUG (DebuggableAttribute Ekleme)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.AssemblyDebug
- /ASSEMBLYDEBUG
helpviewer_keywords:
- /ASSEMBLYDEBUG linker option
- -ASSEMBLYDEBUG linker option
- ASSEMBLYDEBUG linker option
ms.assetid: 94443af3-470c-41d7-83a0-7434563d7982
ms.openlocfilehash: 7d63ae4ffd86099147b076a499321ed5dcf3ca54
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97183041"
---
# <a name="assemblydebug-add-debuggableattribute"></a>/ASSEMBLYDEBUG (DebuggableAttribute Ekleme)

```
/ASSEMBLYDEBUG[:DISABLE]
```

/ASSEMBLYDEBUG hata ayıklama bilgileri izleme ile hata ayıklayıcı **Ggableattribute** özniteliğini yayar ve JIT iyileştirmelerini devre dışı bırakır. Bu, kaynağında aşağıdaki özniteliği belirtmeyle aynıdır:

```
[assembly:Debuggable(true, true)];   // same as /ASSEMBLYDEBUG
```

/ASSEMBLYDEBUG: DıSABLE **Ggableattribute** özniteliğini yayar, ancak hata ayıklama bilgilerinin izlenmesini devre dışı bırakır ve JIT iyileştirmelerini etkinleştirilir. Bu, kaynağında aşağıdaki özniteliği belirtmeyle aynıdır:

```
[assembly:Debuggable(false, false)];   // same as /ASSEMBLYDEBUG:DISABLE
```

Varsayılan değer, hata ayıklama **Ggableattribute** özniteliğini göstermemelidir.

Hata ayıklama Ggableattribute, doğrudan kaynak kodunda bir derlemeye de eklenebilir. Örneğin,

```
[assembly:Debuggable(true, true)];   // same as /ASSEMBLYDEBUG
```

## <a name="remarks"></a>Açıklamalar

Yönetilen bir görüntünün hata ayıklanabilir olmasını açıkça belirtmeniz gerekir. Yalnızca [/Zi](z7-zi-zi-debug-information-format.md) kullanılması yeterli değildir.

Derleme üretimini etkileyen diğer bağlayıcı seçenekleri şunlardır:

- [/ASSEMBLYLıNKRESOURCE](assemblylinkresource-link-to-dotnet-framework-resource.md)

- [/ASSEMBLYMODULE](assemblymodule-add-a-msil-module-to-the-assembly.md)

- [/ASSEMBLYRESOURCE](assemblyresource-embed-a-managed-resource.md)

- [/DELAYSIGN](delaysign-partially-sign-an-assembly.md)

- [/KEYCONTAINER](keycontainer-specify-a-key-container-to-sign-an-assembly.md)

- [/KEYFILE](keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)

- [/NOASSEMBLY](noassembly-create-a-msil-module.md)

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Bağlayıcı** klasörüne tıklayın.

1. **Hata ayıklama** Özellik sayfasına tıklayın.

1. **Hata ayıklanabilir Assembly** özelliğini değiştirin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AssemblyDebug%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
