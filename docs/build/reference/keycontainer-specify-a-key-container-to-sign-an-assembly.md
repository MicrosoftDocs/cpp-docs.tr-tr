---
title: -KEYCONTAINER (derlemeyi imzalamak için anahtar kapsayıcısını belirt) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.KeyContainer
- /keycontainer
dev_langs:
- C++
helpviewer_keywords:
- KEYCONTAINER linker option
- /KEYCONTAINER linker option
- -KEYCONTAINER linker option
ms.assetid: 94882d12-b77a-49c7-96d0-18a31aee001e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 850a8173dba3e69eaf52fdf174674e1dba58a4d8
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45723768"
---
# <a name="keycontainer-specify-a-key-container-to-sign-an-assembly"></a>/KEYCONTAINER (Derlemeyi İmzalamak için Anahtar Kapsayıcısını Belirt)

```
/KEYCONTAINER:name
```

## <a name="arguments"></a>Arguments

*Adı*<br/>
Anahtarı içeren kapsayıcı. Dize, çift tırnak içine yerleştirin ("") bir boşluk içeriyorsa.

## <a name="remarks"></a>Açıklamalar

Bağlayıcı, derleme bildirimine ortak anahtar ekleme ve son derlemeyi özel anahtarla imzalama tarafından imzalı bir derleme oluşturur. Bir anahtar dosyası oluşturmak için şunu yazın [sn -k](/dotnet/framework/tools/sn-exe-strong-name-tool) *filename* komut satırına. **sn -i** bir kapsayıcıya anahtar çifti yükler.

Derleme yaparsanız [/LN](../../build/reference/ln-create-msil-module.md), anahtar dosyasının adını modülde tutulur ve aracılığıyla modül açık bir başvuru içeren bir derleme derlediğinizde, oluşturulan bütünleştirilmiş dahil [#using](../../preprocessor/hash-using-directive-cpp.md), veya ile bağlarken [assemblymodule](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md).

Derleyici ile şifreleme bilgilerinizi de geçirebilirsiniz [/keyfile](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md). Kullanım [/delaysign](../../build/reference/delaysign-partially-sign-an-assembly.md) kısmen imzalı bir derleme istiyorsanız. Bkz: [tanımlayıcı ad derlemeleri (derleme imzalama) (C + +/ CLI)](../../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md) derleme imzalama hakkında daha fazla bilgi.

Bütünleştirilmiş kod oluşturmayı etkileyen diğer bağlayıcı seçenekleri şunlardır:

- [/ ASSEMBLYDEBUG](../../build/reference/assemblydebug-add-debuggableattribute.md)

- [/ ASSEMBLYLINKRESOURCE](../../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md)

- [/ ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)

- [/ ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md)

- [/ NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md)

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).

1. Tıklayın **bağlayıcı** klasör.

1. Tıklayın **komut satırı** özellik sayfası.

1. Seçeneğini yazın **ek seçenekler** kutusu.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)