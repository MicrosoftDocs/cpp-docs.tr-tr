---
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
ms.openlocfilehash: 6896993f7be8e088242e8a2e3279aa1f6c9a721d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50524962"
---
# <a name="keyfile-specify-key-or-key-pair-to-sign-an-assembly"></a>/KEYFILE (Derlemeyi İmzalamak için Anahtar veya Anahtar Çiftini Belirt)

```
/KEYFILE:filename
```

## <a name="arguments"></a>Arguments

*Dosya adı*<br/>
Anahtarı içeren dosya. Dize, çift tırnak içine yerleştirin ("") bir boşluk içeriyorsa.

## <a name="remarks"></a>Açıklamalar

Bağlayıcı, ortak anahtarı derleme bildirimine ekler ve ardından son derlemeyi özel anahtarla imzalar. Bir anahtar dosyası oluşturmak için şunu yazın [sn -k](/dotnet/framework/tools/sn-exe-strong-name-tool) *filename* komut satırına. İmzalı bir derleme tanımlayıcı bir ada sahip bildirilir.

Derleme yaparsanız [/LN](../../build/reference/ln-create-msil-module.md), anahtar dosyasının adını modülde tutulur ve aracılığıyla modül açık bir başvuru içeren bir derleme derlediğinizde, oluşturulan bütünleştirilmiş dahil [#using](../../preprocessor/hash-using-directive-cpp.md), veya ile bağlarken [assemblymodule](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md).

İle bağlayıcıya şifreleme bilgilerinizi de geçirebilirsiniz [/keycontainer](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md). Kullanım [/delaysign](../../build/reference/delaysign-partially-sign-an-assembly.md) kısmen imzalı bir derleme istiyorsanız. Bkz: [tanımlayıcı ad derlemeleri (derleme imzalama) (C + +/ CLI)](../../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md) derleme imzalama hakkında daha fazla bilgi.

İçinde her ikisi de case **/keyfile** ve **/keycontainer** belirtilen (komut satırı seçeneği veya özel öznitelik tarafından), bağlayıcı ilk anahtar kapsayıcısı deneyin. Bu başarılı olursa derleme anahtar kapsayıcısındaki bilgilerle imzalanır. Bağlayıcı anahtar kapsayıcısını bulamazsa, / keyfile ile belirtilen dosyayı deneyecektir. Bu başarılı olursa derleme anahtar dosyası içindeki bilgilerle imzalanır ve anahtar bilgileri anahtar kapsayıcısının içine yüklenir (sn benzer -i) ve böylece sonraki derlemede, anahtar kapsayıcısı geçerli olacaktır.

Bir anahtar dosyası yalnızca ortak anahtar içerebileceğini unutmayın.

Bkz: [bkz](/dotnet/framework/app-domains/create-and-use-strong-named-assemblies) derleme imzalama hakkında daha fazla bilgi.

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

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)