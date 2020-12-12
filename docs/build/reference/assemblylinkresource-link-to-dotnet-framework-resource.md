---
description: Şu konuda daha fazla bilgi edinin:/ASSEMBLYLINKRESOURCE (.NET Framework kaynağına bağlantı)
title: /ASSEMBLYLINKRESOURCE (.NET Framework Kaynağına Bağlantı)
ms.date: 11/04/2016
f1_keywords:
- /ASSEMBLYLINKRESOURCE
- VC.Project.VCLinkerTool.AssemblyLinkResource
helpviewer_keywords:
- -ASSEMBLYLINKRESOURCE linker option
- ASSEMBLYLINKRESOURCE linker option
- /ASSEMBLYLINKRESOURCE linker option
ms.assetid: 8b6ad184-1b33-47a4-8513-4803cf915b64
ms.openlocfilehash: 32761cb16e8428d5e3c18330dffb49a50a42903c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97183015"
---
# <a name="assemblylinkresource-link-to-net-framework-resource"></a>/ASSEMBLYLINKRESOURCE (.NET Framework Kaynağına Bağlantı)

```
/ASSEMBLYLINKRESOURCE:filename
```

## <a name="arguments"></a>Arguments

*filename*<br/>
Derlemeden bağlamak istediğiniz .NET Framework kaynak dosyası.

## <a name="remarks"></a>Açıklamalar

/ASSEMBLYLINKRESOURCE seçeneği, çıkış dosyasında bir .NET Framework kaynağına bir bağlantı oluşturur; kaynak dosyası çıkış dosyasına yerleştirilmez. [/ASSEMBLYRESOURCE](assemblyresource-embed-a-managed-resource.md) bir kaynak dosyasını çıkış dosyasına katıştırır.

Bağlantılı kaynaklar, bağlayıcı ile oluşturulduğunda derlemede ortaktır.

/ASSEMBLYLINKRESOURCE, derlemenin [/clr](clr-common-language-runtime-compilation.md)içermesini gerektirir; [/Ln](ln-create-msil-module.md) veya [/noAssembly](noassembly-create-a-msil-module.md) ,/assemblylinkresourceile kullanılamaz.

*Dosya adı* , örneğin, [Resgen.exe](/dotnet/framework/tools/resgen-exe-resource-file-generator) veya geliştirme ortamında oluşturulmuş bir .NET Framework kaynak dosyası Ise, **System. resources** ad alanındaki üyelerle erişilebilir. Daha fazla bilgi için bkz. [System. resources. ResourceManager](/dotnet/api/system.resources.resourcemanager). Diğer tüm kaynaklar için,  \* çalışma zamanında kaynağa erişmek üzere **System. Reflection. Assembly** sınıfında GetManifestResource yöntemlerini kullanın.

Dosya *adı* herhangi bir dosya biçimi olabilir. Örneğin, derlemenin yerel bir DLL parçası yapmak isteyebilirsiniz, bu nedenle genel derleme önbelleğine yüklenebilir ve derlemedeki yönetilen koddan erişilebilir.

Derleme üretimini etkileyen diğer bağlayıcı seçenekleri şunlardır:

- [/ASSEMBLYDEBUG](assemblydebug-add-debuggableattribute.md)

- [/ASSEMBLYMODULE](assemblymodule-add-a-msil-module-to-the-assembly.md)

- [/ASSEMBLYRESOURCE](assemblyresource-embed-a-managed-resource.md)

- [/DELAYSIGN](delaysign-partially-sign-an-assembly.md)

- [/KEYCONTAINER](keycontainer-specify-a-key-container-to-sign-an-assembly.md)

- [/KEYFILE](keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)

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
