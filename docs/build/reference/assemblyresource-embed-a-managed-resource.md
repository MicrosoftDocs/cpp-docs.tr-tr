---
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
ms.openlocfilehash: 1eac489ffd01f6bd79fc8c5bbda23adb751c9486
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62295077"
---
# <a name="assemblyresource-embed-a-managed-resource"></a>/ASSEMBLYRESOURCE (Yönetilen Kaynağı Katıştır)

```
/ASSEMBLYRESOURCE:filename[,[name][,PRIVATE]]
```

## <a name="parameters"></a>Parametreler

*Dosya adı*<br/>
Bu derlemede katıştırmak için istediğiniz yönetilen kaynak.

*Adı*<br/>
İsteğe bağlı. Kaynağın mantıksal adı; Kaynak yüklemek için kullanılan ad. Varsayılan dosya adıdır.

İsteğe bağlı olarak dosyanın derleme bildiriminde özel olup olmayacağını belirtebilirsiniz. Varsayılan olarak, *adı* derleme içinde geneldir.

## <a name="remarks"></a>Açıklamalar

Bir kaynak derlemede katıştırmak için koduna konmaz seçeneği kullanın.

Bağlayıcı ile oluşturulan derleme içinde geneldir kaynaklardır. Bağlayıcı derlemedeki kaynağı yeniden adlandırmak izin vermez.

Varsa *filename* , örneğin, tarafından oluşturulmuş bir .NET Framework kaynak (.resources) dosyası [kaynak dosya oluşturucu (Resgen.exe)](/dotnet/framework/tools/resgen-exe-resource-file-generator) veya geliştirme ortamında, bu üye ile erişilebilir **System.Resources** ad alanı (bkz [System.Resources.ResourceManager](/dotnet/api/system.resources.resourcemanager) daha fazla bilgi için). Diğer tüm kaynaklar için kullanmak **T:System.Reflection.Assembly** \* yöntemleri **System.Reflection.Assembly** çalışma zamanında kaynağa erişmek için sınıf.

Bütünleştirilmiş kod oluşturmayı etkileyen diğer bağlayıcı seçenekleri şunlardır:

- [/ ASSEMBLYDEBUG](assemblydebug-add-debuggableattribute.md)

- [/ ASSEMBLYLINKRESOURCE](assemblylinkresource-link-to-dotnet-framework-resource.md)

- [/ ASSEMBLYMODULE](assemblymodule-add-a-msil-module-to-the-assembly.md)

- [/ DELAYSIGN](delaysign-partially-sign-an-assembly.md)

- [/ KEYFILE](keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)

- [/ KEYCONTAINER](keycontainer-specify-a-key-container-to-sign-an-assembly.md)

- [/ NOASSEMBLY](noassembly-create-a-msil-module.md)

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Tıklayın **bağlayıcı** klasör.

1. Tıklayın **giriş** özellik sayfası.

1. Değiştirme **yönetilen kaynak dosyasını katıştır** özelliği.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

1. Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EmbedManagedResourceFile%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC Bağlayıcı Seçenekleri](linker-options.md)
