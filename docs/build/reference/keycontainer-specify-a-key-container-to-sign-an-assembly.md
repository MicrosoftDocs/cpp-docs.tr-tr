---
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
ms.openlocfilehash: 96d2f5fed0e450224f82ee909cea9d56082505fb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62291619"
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

Derleme yaparsanız [/LN](ln-create-msil-module.md), anahtar dosyasının adını modülde tutulur ve aracılığıyla modül açık bir başvuru içeren bir derleme derlediğinizde, oluşturulan bütünleştirilmiş dahil [#using](../../preprocessor/hash-using-directive-cpp.md), veya ile bağlarken [assemblymodule](assemblymodule-add-a-msil-module-to-the-assembly.md).

Derleyici ile şifreleme bilgilerinizi de geçirebilirsiniz [/keyfile](keyfile-specify-key-or-key-pair-to-sign-an-assembly.md). Kullanım [/delaysign](delaysign-partially-sign-an-assembly.md) kısmen imzalı bir derleme istiyorsanız. Bkz: [tanımlayıcı ad derlemeleri (derleme imzalama) (C++/CLI)](../../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md) derleme imzalama hakkında daha fazla bilgi.

Bütünleştirilmiş kod oluşturmayı etkileyen diğer bağlayıcı seçenekleri şunlardır:

- [/ ASSEMBLYDEBUG](assemblydebug-add-debuggableattribute.md)

- [/ ASSEMBLYLINKRESOURCE](assemblylinkresource-link-to-dotnet-framework-resource.md)

- [/ ASSEMBLYMODULE](assemblymodule-add-a-msil-module-to-the-assembly.md)

- [/ ASSEMBLYRESOURCE](assemblyresource-embed-a-managed-resource.md)

- [/ NOASSEMBLY](noassembly-create-a-msil-module.md)

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Tıklayın **bağlayıcı** klasör.

1. Tıklayın **komut satırı** özellik sayfası.

1. Seçeneğini yazın **ek seçenekler** kutusu.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC Bağlayıcı Seçenekleri](linker-options.md)
