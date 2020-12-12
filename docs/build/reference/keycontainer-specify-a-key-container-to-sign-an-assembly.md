---
description: :/KEYCONTAINER hakkında daha fazla bilgi edinin (bir derlemeyi Imzalamak için bir anahtar kapsayıcısı belirtin)
title: /KEYCONTAINER (Derlemeyi İmzalamak için Anahtar Kapsayıcısını Belirt)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.KeyContainer
- /keycontainer
helpviewer_keywords:
- KEYCONTAINER linker option
- /KEYCONTAINER linker option
- -KEYCONTAINER linker option
ms.assetid: 94882d12-b77a-49c7-96d0-18a31aee001e
ms.openlocfilehash: 5f32fdc5400103d4038139fa2dfe9409c9740236
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97199590"
---
# <a name="keycontainer-specify-a-key-container-to-sign-an-assembly"></a>/KEYCONTAINER (Derlemeyi İmzalamak için Anahtar Kapsayıcısını Belirt)

```
/KEYCONTAINER:name
```

## <a name="arguments"></a>Arguments

*ada*<br/>
Anahtarı içeren kapsayıcı. Dizeyi, bir boşluk içeriyorsa çift tırnak işaretleri ("") içine koyun.

## <a name="remarks"></a>Açıklamalar

Bağlayıcı, derleme bildirimine ortak anahtar ekleyerek ve son derlemeyi özel anahtarla imzalayarak imzalı bir derleme oluşturur. Anahtar dosyası oluşturmak için komut satırına [sn-k](/dotnet/framework/tools/sn-exe-strong-name-tool) *dosya adı* yazın. **sn-** anahtar çiftini bir kapsayıcıya yükledim.

[/Ln](ln-create-msil-module.md)ile derlerseniz, anahtar dosyasının adı modülde tutulur ve modüle açık bir başvuru içeren bir derlemeyi derlediğinizde, [#using](../../preprocessor/hash-using-directive-cpp.md)aracılığıyla veya [/ASSEMBLYMODULE](assemblymodule-add-a-msil-module-to-the-assembly.md)ile bağlanırken oluşturulan derlemeye dahil edilir.

Ayrıca, şifreleme bilgilerinizi [/keyfile](keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)ile derleyiciye geçirebilirsiniz. Kısmen imzalanmış bir derleme istiyorsanız [/delaysign](delaysign-partially-sign-an-assembly.md) kullanın. Bir derlemeyi imzalama hakkında daha fazla bilgi için bkz. [tanımlayıcı ad derlemeleri (derleme imzalama) (C++/CLI)](../../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md) .

Derleme üretimini etkileyen diğer bağlayıcı seçenekleri şunlardır:

- [/ASSEMBLYDEBUG](assemblydebug-add-debuggableattribute.md)

- [/ASSEMBLYLıNKRESOURCE](assemblylinkresource-link-to-dotnet-framework-resource.md)

- [/ASSEMBLYMODULE](assemblymodule-add-a-msil-module-to-the-assembly.md)

- [/ASSEMBLYRESOURCE](assemblyresource-embed-a-managed-resource.md)

- [/NOASSEMBLY](noassembly-create-a-msil-module.md)

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Bağlayıcı** klasörüne tıklayın.

1. **Komut satırı** Özellik sayfasına tıklayın.

1. Seçeneği **ek seçenekler** kutusuna yazın.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
