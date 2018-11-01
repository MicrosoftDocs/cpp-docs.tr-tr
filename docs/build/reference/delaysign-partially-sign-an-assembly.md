---
title: /DELAYSIGN (Derlemeyi Kısmen İmzala)
ms.date: 11/04/2016
f1_keywords:
- /delaysign
- VC.Project.VCLinkerTool.DelaySign
helpviewer_keywords:
- /DELAYSIGN linker option
- DELAYSIGN linker option
- -DELAYSIGN linker option
ms.assetid: 15244d30-3ecb-492f-a408-ffe81f38de20
ms.openlocfilehash: 233a41a3e55ff2726712541b0af9db1f5e55eb56
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50435626"
---
# <a name="delaysign-partially-sign-an-assembly"></a>/DELAYSIGN (Derlemeyi Kısmen İmzala)

```
/DELAYSIGN[:NO]
```

## <a name="arguments"></a>Arguments

**YOK**<br/>
Derleme olmayan kısmen imzalanması gerektiğini belirtir.

## <a name="remarks"></a>Açıklamalar

Kullanım **/delaysign** yalnızca derleme içinde ortak anahtar yerleştirmek istiyorsanız. Varsayılan değer **delaysıgn: No**.

**/Delaysign** seçeneği ile birlikte kullanılmadığı sürece hiçbir etkiye sahiptir [/keyfile](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md) veya [/keycontainer](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md).

Tam imzalı bir derleme istediğinizde; derleyici bildirimi (derleme meta verileri) içeren ve karmayı özel anahtarla imzalar dosyayı karma hale getirir. Elde edilen dijital imza, bildirimi içeren dosyada depolanır. Bir derlemeyi gecikmeli imzalanmış olduğunda, bağlayıcı işlem değil ve daha sonra imzanın eklenmesi için dosyada depolamak imzaya ancak ayırır.

Örneğin, kullanarak **/delaysign** derlemeyi genel önbellek üzerine koymasına olanak sağlar. Test edildikten sonra özel anahtarı derlemeye koyarak derlemenin tam olarak oturum açabilirsiniz.

Bkz: [tanımlayıcı ad derlemeleri (derleme imzalama) (C + +/ CLI)](../../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md) ve [derlemeyi imzalamayı geciktirme](/dotnet/framework/app-domains/delay-sign-assembly) derleme imzalama hakkında daha fazla bilgi.

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