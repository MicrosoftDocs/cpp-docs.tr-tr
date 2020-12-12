---
description: :/ASSEMBLYRESOURCE (yönetilen kaynağı katıştır) hakkında daha fazla bilgi edinin
title: /ASSEMBLYRESOURCE (Yönetilen Kaynağı Katıştır)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.EmbedManagedResourceFile
- /ASSEMBLYRESOURCE
helpviewer_keywords:
- ASSEMBLYRESOURCE linker option
- assemblies [C++]
- -ASSEMBLYRESOURCE linker option
- assemblies [C++], linking resource files
- /ASSEMBLYRESOURCE linker option
ms.assetid: 0ce6e1fb-921b-4b1b-a59c-d35388d789f2
ms.openlocfilehash: 3f79cc177df72bb83288a0a229fdf47adb0e7fc0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182924"
---
# <a name="assemblyresource-embed-a-managed-resource"></a>/ASSEMBLYRESOURCE (Yönetilen Kaynağı Katıştır)

```
/ASSEMBLYRESOURCE:filename[,[name][,PRIVATE]]
```

## <a name="parameters"></a>Parametreler

*filename*<br/>
Bu derlemeye eklemek istediğiniz yönetilen kaynak.

*ada*<br/>
İsteğe bağlı. Kaynağın mantıksal adı; kaynağı yüklemek için kullanılan ad. Varsayılan değer, dosyanın adıdır.

İsteğe bağlı olarak, dosyanın derleme bildiriminde özel olup olmadığını belirtebilirsiniz. Varsayılan olarak, *ad* derlemede ortak olur.

## <a name="remarks"></a>Açıklamalar

Bir derlemeye kaynak eklemek için/ASSEMBLYRESOURCE seçeneğini kullanın.

Bağlayıcı ile oluşturulduğunda kaynaklar derlemede ortaktır. Bağlayıcı, derlemede kaynağı yeniden adlandırmanıza izin vermez.

*Dosya adı* , örneğin, [kaynak dosya üreticisi (Resgen.exe)](/dotnet/framework/tools/resgen-exe-resource-file-generator) veya geliştirme ortamında oluşturulmuş bir .NET Framework kaynak (. resources) dosyası Ise, **System. resources** ad alanındaki üyelerle erişilebilir (daha fazla bilgi için bkz. [System. resources. ResourceManager](/dotnet/api/system.resources.resourcemanager) ). Diğer tüm kaynaklar için,  \* çalışma zamanında kaynağa erişmek üzere **System. Reflection. Assembly** sınıfındaki GetManifestResource yöntemlerini kullanın.

Derleme üretimini etkileyen diğer bağlayıcı seçenekleri şunlardır:

- [/ASSEMBLYDEBUG](assemblydebug-add-debuggableattribute.md)

- [/ASSEMBLYLıNKRESOURCE](assemblylinkresource-link-to-dotnet-framework-resource.md)

- [/ASSEMBLYMODULE](assemblymodule-add-a-msil-module-to-the-assembly.md)

- [/DELAYSIGN](delaysign-partially-sign-an-assembly.md)

- [/KEYFILE](keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)

- [/KEYCONTAINER](keycontainer-specify-a-key-container-to-sign-an-assembly.md)

- [/NOASSEMBLY](noassembly-create-a-msil-module.md)

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Bağlayıcı** klasörüne tıklayın.

1. **Giriş** Özellik sayfasına tıklayın.

1. **Yönetilen kaynak dosyası Ekle** özelliğini değiştirin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

1. Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EmbedManagedResourceFile%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
