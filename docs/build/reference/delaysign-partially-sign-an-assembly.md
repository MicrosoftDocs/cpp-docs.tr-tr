---
description: Daha fazla bilgi edinin:/DELAYSIGN (bir derlemeyi kısmen Imzala)
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
ms.openlocfilehash: 40eeaef958b6a188fd4739fcdc0f5ef5123b220a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201488"
---
# <a name="delaysign-partially-sign-an-assembly"></a>/DELAYSIGN (Derlemeyi Kısmen İmzala)

```
/DELAYSIGN[:NO]
```

## <a name="arguments"></a>Arguments

**EŞLEŞEN**<br/>
Derlemenin kısmen imzalı olmaması gerektiğini belirtir.

## <a name="remarks"></a>Açıklamalar

Yalnızca ortak anahtarı derlemeye koymak istiyorsanız **/delaysign** kullanın. Varsayılan değer **/delaysign: No**' dır.

**/Delaysign** seçeneği, [/keyfile](keyfile-specify-key-or-key-pair-to-sign-an-assembly.md) veya [/keycontainer](keycontainer-specify-a-key-container-to-sign-an-assembly.md)ile kullanılmamışsa hiçbir etkiye sahip değildir.

Tam olarak imzalanan bir derleme istediğinizde, derleyici bildirimi içeren dosyayı (derleme meta verileri) karma hale getirir ve bu karmayı özel anahtarla imzalar. Elde edilen dijital imza, bildirimi içeren dosyada depolanır. Bir derlemenin gecikmesi gecikmeli olduğunda bağlayıcı, imzayı hesaplamaz ve depolamaz, ancak imzanın daha sonra eklenebilmesi için dosyada yer ayırır.

Örneğin, **/delaysign** kullanılması, bir sınayıcı 'ın derlemeyi genel önbellekte almasına izin verir. Test ettikten sonra, özel anahtarı derlemeye yerleştirerek derlemeyi tamamen imzalayabilirsiniz.

Bir derlemeyi imzalama hakkında daha fazla bilgi için bkz. [tanımlayıcı ad derlemeleri (derleme imzalama) (C++/CLI)](../../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md) ve [bir derlemeyi imzalamayı geciktirme](/dotnet/framework/app-domains/delay-sign-assembly) .

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
