---
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
ms.openlocfilehash: fb707a2721ed40ee3ec37d01b2bbcfcc51f05c38
ms.sourcegitcommit: faa42c8a051e746d99dcebe70fd4bbaf3b023ace
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/15/2019
ms.locfileid: "57807812"
---
# <a name="assemblylinkresource-link-to-net-framework-resource"></a>/ASSEMBLYLINKRESOURCE (.NET Framework Kaynağına Bağlantı)

```
/ASSEMBLYLINKRESOURCE:filename
```

## <a name="arguments"></a>Arguments

*Dosya adı*<br/>
Derlemeden bağlamak istediğiniz .NET Framework kaynak dosyası.

## <a name="remarks"></a>Açıklamalar

/ Assemblylınkresource seçeneği, çıkış dosyasında .NET Framework kaynağına bağlantı oluşturur; kaynak dosyası çıkış dosyasına yerleştirilmez. [/ ASSEMBLYRESOURCE](assemblyresource-embed-a-managed-resource.md) bir kaynak dosyasını çıkış dosyası na ekler.

Bağlı kaynaklar ile bağlayıcı oluştururken derleme içinde geneldir.

/ ASSEMBLYLINKRESOURCE gerektirir derleme içerdiğini [/CLR](clr-common-language-runtime-compilation.md); [/LN](ln-create-msil-module.md) veya [noassembly](noassembly-create-a-msil-module.md) ile/assemblylınkresource izin verilmez.

Varsa *filename* , örneğin, tarafından oluşturulmuş bir .NET Framework kaynak dosyası [Resgen.exe](/dotnet/framework/tools/resgen-exe-resource-file-generator) veya geliştirme ortamında üyelerle erişilebileceğini **System.Resources** ad alanı. Daha fazla bilgi için [System.Resources.ResourceManager](/dotnet/api/system.resources.resourcemanager). Diğer tüm kaynaklar için kullanmak **T:System.Reflection.Assembly** \* yöntemleri **System.Reflection.Assembly** çalışma zamanında kaynağa erişmek için sınıf.

*filename* herhangi bir dosya biçiminde olabilir. Örneğin, genel derleme önbelleğine yüklenebilir ve derlemedeki yönetilen koddan erişilebilir derlemenin yerel bir DLL parçası olmak isteyebilirsiniz.

Bütünleştirilmiş kod oluşturmayı etkileyen diğer bağlayıcı seçenekleri şunlardır:

- [/ ASSEMBLYDEBUG](assemblydebug-add-debuggableattribute.md)

- [/ ASSEMBLYMODULE](assemblymodule-add-a-msil-module-to-the-assembly.md)

- [/ ASSEMBLYRESOURCE](assemblyresource-embed-a-managed-resource.md)

- [/ DELAYSIGN](delaysign-partially-sign-an-assembly.md)

- [/ KEYCONTAINER](keycontainer-specify-a-key-container-to-sign-an-assembly.md)

- [/ KEYFILE](keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)

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
[MSVC bağlayıcı seçenekleri](linker-options.md)
