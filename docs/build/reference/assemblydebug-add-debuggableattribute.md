---
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
ms.openlocfilehash: e9b39791e6537976be37b942292e1b1d42d5f700
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50478656"
---
# <a name="assemblydebug-add-debuggableattribute"></a>/ASSEMBLYDEBUG (DebuggableAttribute Ekleme)

```
/ASSEMBLYDEBUG[:DISABLE]
```

/ ASSEMBLYDEBUG yayan **DebuggableAttribute** hata ayıklama bilgisi izleme ve devre dışı bırakır JIT iyileştirmelerini özniteliğiyle. Bu kaynakta aşağıdaki öznitelik belirterek aynıdır:

```
[assembly:Debuggable(true, true)];   // same as /ASSEMBLYDEBUG
```

DISABLE yayan **DebuggableAttribute** özniteliği ancak hata ayıklama bilgisi izlemeyi devre dışı bırakır ve JIT iyileştirmelerini sağlar. Bu kaynakta aşağıdaki öznitelik belirterek aynıdır:

```
[assembly:Debuggable(false, false)];   // same as /ASSEMBLYDEBUG:DISABLE
```

Ktıları varsayılandır **DebuggableAttribute** özniteliği.

Bir derlemeye doğrudan kaynak kodundaki DebuggableAttribute da eklenebilir. Örneğin,

```
[assembly:Debuggable(true, true)];   // same as /ASSEMBLYDEBUG
```

## <a name="remarks"></a>Açıklamalar

Yönetilen bir görüntü hataları ayıklanabilir olmayacak açıkça belirtmek gereklidir. Kullanarak [/zi](../../build/reference/z7-zi-zi-debug-information-format.md) tek başına yeterli değildir.

Bütünleştirilmiş kod oluşturmayı etkileyen diğer bağlayıcı seçenekleri şunlardır:

- [/ ASSEMBLYLINKRESOURCE](../../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md)

- [/ ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)

- [/ ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md)

- [/ DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md)

- [/ KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)

- [/ KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)

- [/ NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md)

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).

1. Tıklayın **bağlayıcı** klasör.

1. Tıklayın **hata ayıklama** özellik sayfası.

1. Değiştirme **hatası ayıklanabilir bütünleşmiş kod** özelliği.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AssemblyDebug%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)