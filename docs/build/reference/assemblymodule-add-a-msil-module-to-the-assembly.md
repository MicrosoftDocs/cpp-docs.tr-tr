---
description: :/ASSEMBLYMODULE (derlemeye MSIL Modülü Ekle) hakkında daha fazla bilgi edinin
title: /ASSEMBLYMODULE (Derlemeye MSIL Modülü Ekle)
ms.date: 11/04/2016
f1_keywords:
- /assemblymodule
- VC.Project.VCLinkerTool.AddModuleNamesToAssembly
helpviewer_keywords:
- ASSEMBLYMODULE linker option
- assemblies [C++], adding modules to
- assemblies [C++]
- /ASSEMBLYMODULE linker option
- -ASSEMBLYMODULE linker option
ms.assetid: 67357da8-e4b6-49fd-932c-329a5777f143
ms.openlocfilehash: d56895b6bec05efda1104e319e93a040f818e06e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182950"
---
# <a name="assemblymodule-add-a-msil-module-to-the-assembly"></a>/ASSEMBLYMODULE (Derlemeye MSIL Modülü Ekle)

```
/ASSEMBLYMODULE:filename
```

## <a name="arguments"></a>Arguments

*filename*<br/>
Bu derlemeye eklemek istediğiniz modül.

## <a name="remarks"></a>Açıklamalar

/ASSEMBLYMODULE seçeneği bir derlemeye modül başvurusu eklemenize olanak tanır. Modüldeki tür bilgileri, modül başvurusunu ekleyen derleme programı tarafından kullanılamaz. Ancak, modüldeki tür bilgileri derlemeye başvuran tüm programlar için kullanılabilir olacaktır.

Bir derlemeye modül başvurusu eklemek ve modülün tür bilgilerini derleme programı için kullanılabilir hale getirmek için [#using](../../preprocessor/hash-using-directive-cpp.md) kullanın.

Örneğin, aşağıdaki senaryoları düşünün:

1. [/Ln](ln-create-msil-module.md)ile bir modül oluşturun.

1. Modülü, bir derleme oluşturacak geçerli derlemeye eklemek için farklı bir projede/ASSEMBLYMODULE kullanın. Bu proje, modülüne modüle başvurmayacak `#using` .

1. Bu derlemeye başvuran tüm projeler artık modülden türler de kullanabilir.

Derleme üretimini etkileyen diğer bağlayıcı seçenekleri şunlardır:

- [/ASSEMBLYDEBUG](assemblydebug-add-debuggableattribute.md)

- [/ASSEMBLYLıNKRESOURCE](assemblylinkresource-link-to-dotnet-framework-resource.md)

- [/ASSEMBLYRESOURCE](assemblyresource-embed-a-managed-resource.md)

- [/DELAYSIGN](delaysign-partially-sign-an-assembly.md)

- [/NOASSEMBLY](noassembly-create-a-msil-module.md)

- [/KEYFILE](keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)

- [/KEYCONTAINER](keycontainer-specify-a-key-container-to-sign-an-assembly.md)

MSVC Bağlayıcısı. netmodule dosyalarını girdi olarak kabul eder ve bağlayıcı tarafından üretilen çıkış dosyası, bağlayıcıya giriş yapan. netmodules üzerinde çalışma zamanı bağımlılığı olmayan bir derleme veya. netmodule olur.  Daha fazla bilgi için, bkz [.. netmodule dosyaları bağlayıcı girişi olarak](netmodule-files-as-linker-input.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Bağlayıcı** klasörüne tıklayın.

1. **Giriş** Özellik sayfasına tıklayın.

1. **Modül Ekle özelliğini derleme** özelliğine değiştirin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AddModuleNamesToAssembly%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
