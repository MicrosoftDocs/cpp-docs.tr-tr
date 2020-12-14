---
description: :/KEYFILE hakkında daha fazla bilgi edinin (bir derlemeyi Imzalamak için anahtar veya anahtar çiftini belirtin)
title: /KEYFILE (Derlemeyi İmzalamak için Anahtar veya Anahtar Çiftini Belirt)
ms.date: 11/04/2016
f1_keywords:
- /keyfile
- VC.Project.VCLinkerTool.KeyFile
helpviewer_keywords:
- /KEYFILE linker option
- -KEYFILE linker option
- KEYFILE linker option
ms.assetid: 9b71f8c0-541c-4fe5-a0c7-9364f42ecb06
ms.openlocfilehash: 23c4962ab57688f5d8c1af27fd412d7d36be01a0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97191166"
---
# <a name="keyfile-specify-key-or-key-pair-to-sign-an-assembly"></a>/KEYFILE (Derlemeyi İmzalamak için Anahtar veya Anahtar Çiftini Belirt)

```
/KEYFILE:filename
```

## <a name="arguments"></a>Arguments

*filename*<br/>
Anahtarı içeren dosya. Dizeyi, bir boşluk içeriyorsa çift tırnak işaretleri ("") içine koyun.

## <a name="remarks"></a>Açıklamalar

Bağlayıcı, ortak anahtarı derleme bildirimine ekler ve ardından son derlemeyi özel anahtarla imzalar. Anahtar dosyası oluşturmak için komut satırına [sn-k](/dotnet/framework/tools/sn-exe-strong-name-tool) *dosya adı* yazın. İmzalı bir derlemenin tanımlayıcı adı olduğu söylenir.

[/Ln](ln-create-msil-module.md)ile derlerseniz, anahtar dosyasının adı modülde tutulur ve modüle açık bir başvuru içeren bir derlemeyi derlediğinizde, [#using](../../preprocessor/hash-using-directive-cpp.md)aracılığıyla veya [/ASSEMBLYMODULE](assemblymodule-add-a-msil-module-to-the-assembly.md)ile bağlanırken oluşturulan derlemeye dahil edilir.

Ayrıca, şifreleme bilgilerinizi [/keycontainer](keycontainer-specify-a-key-container-to-sign-an-assembly.md)ile bağlayıcıya geçirebilirsiniz. Kısmen imzalanmış bir derleme istiyorsanız [/delaysign](delaysign-partially-sign-an-assembly.md) kullanın. Bir derlemeyi imzalama hakkında daha fazla bilgi için bkz. [tanımlayıcı ad derlemeleri (derleme imzalama) (C++/CLI)](../../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md) .

Hem **/keyfile** hem de **/keycontainer** belirtildiğinde (komut satırı seçeneğine veya özel özniteliğe göre), bağlayıcı öncelikle anahtar kapsayıcısını dener. Bu başarılı olursa, derleme anahtar kapsayıcısındaki bilgilerle imzalanır. Bağlayıcı anahtar kapsayıcısını bulamazsa,/KEYFILEILE belirtilen dosyayı dener. Bu başarılı olursa, derleme anahtar dosyasındaki bilgilerle imzalanır ve anahtar bilgileri, sonraki derlemede anahtar kapsayıcısının geçerli olacağı şekilde anahtar kapsayıcısına (sn-ı ' ye benzer) yüklenir.

Anahtar dosyasının yalnızca ortak anahtar içerebileceğini unutmayın.

Bir derlemeyi imzalama hakkında daha fazla bilgi için bkz. [Strong-Named derlemeleri oluşturma ve kullanma](/dotnet/framework/app-domains/create-and-use-strong-named-assemblies) .

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
