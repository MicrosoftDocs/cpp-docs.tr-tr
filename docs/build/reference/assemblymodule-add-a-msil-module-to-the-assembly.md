---
title: -ASSEMBLYMODULE (derlemeye MSIL Modülü Ekle) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /assemblymodule
- VC.Project.VCLinkerTool.AddModuleNamesToAssembly
dev_langs:
- C++
helpviewer_keywords:
- ASSEMBLYMODULE linker option
- assemblies [C++], adding modules to
- assemblies [C++]
- /ASSEMBLYMODULE linker option
- -ASSEMBLYMODULE linker option
ms.assetid: 67357da8-e4b6-49fd-932c-329a5777f143
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8c1b5104a264a3fbeeada080b6c34a6b1c5e23ca
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45703943"
---
# <a name="assemblymodule-add-a-msil-module-to-the-assembly"></a>/ASSEMBLYMODULE (Derlemeye MSIL Modülü Ekle)

```
/ASSEMBLYMODULE:filename
```

## <a name="arguments"></a>Arguments

*Dosya adı*<br/>
Bu derlemede dahil etmek istediğiniz modülü.

## <a name="remarks"></a>Açıklamalar

Assemblymodule seçeneği, bir derlemeye bir modül başvurusu eklemenize olanak sağlar. Tür bilgisi modül başvurusu eklenen derleme programı için kullanılamaz. Ancak modüldeki tür bilgileri derlemenin başvurduğu herhangi bir programı için kullanılabilir.

Kullanım [#using](../../preprocessor/hash-using-directive-cpp.md) hem bir derlemeye bir modül başvurusu ekleyin ve modülün tür bilgisi derleme programı için kullanılabilir hale getirmek için.

Örneğin, aşağıdaki senaryoları düşünün:

1. Sahip bir modül oluşturma [/LN](../../build/reference/ln-create-msil-module.md).

1. Assemblymodule farklı bir projede bir derleme oluşturur geçerli derlemede modülü kullanın. Bu proje modülle başvuruda bulunmamaya `#using`.

1. Bu derlemenin başvurduğu tüm proje türleri modülden şimdi de kullanabilirsiniz.

Bütünleştirilmiş kod oluşturmayı etkileyen diğer bağlayıcı seçenekleri şunlardır:

- [/ ASSEMBLYDEBUG](../../build/reference/assemblydebug-add-debuggableattribute.md)

- [/ ASSEMBLYLINKRESOURCE](../../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md)

- [/ ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md)

- [/ DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md)

- [/ NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md)

- [/ KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)

- [/ KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)

Visual C++ bağlayıcı girişi .netmodule dosyaları kabul eder ve bağlayıcı tarafından üretilen çıkış dosyası bir derleme veya .netmodule herhangi bir bağlayıcıya giriş netmodule'leri hiçbir çalışma zamanı bağımlılığa sahip olacaktır.  Daha fazla bilgi için [bağlayıcı girişi olarak .netmodule dosyaları](../../build/reference/netmodule-files-as-linker-input.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).

1. Tıklayın **bağlayıcı** klasör.

1. Tıklayın **giriş** özellik sayfası.

1. Değiştirme **derlemeye Modül Ekle** özelliği.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AddModuleNamesToAssembly%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)