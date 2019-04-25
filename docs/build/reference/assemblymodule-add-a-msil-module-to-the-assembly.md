---
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
ms.openlocfilehash: 728e8a84ff8d1afac99f99dbb975c7fd9360bcc1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62273026"
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

1. Sahip bir modül oluşturma [/LN](ln-create-msil-module.md).

1. Assemblymodule farklı bir projede bir derleme oluşturur geçerli derlemede modülü kullanın. Bu proje modülle başvuruda bulunmamaya `#using`.

1. Bu derlemenin başvurduğu tüm proje türleri modülden şimdi de kullanabilirsiniz.

Bütünleştirilmiş kod oluşturmayı etkileyen diğer bağlayıcı seçenekleri şunlardır:

- [/ ASSEMBLYDEBUG](assemblydebug-add-debuggableattribute.md)

- [/ ASSEMBLYLINKRESOURCE](assemblylinkresource-link-to-dotnet-framework-resource.md)

- [/ ASSEMBLYRESOURCE](assemblyresource-embed-a-managed-resource.md)

- [/ DELAYSIGN](delaysign-partially-sign-an-assembly.md)

- [/ NOASSEMBLY](noassembly-create-a-msil-module.md)

- [/ KEYFILE](keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)

- [/ KEYCONTAINER](keycontainer-specify-a-key-container-to-sign-an-assembly.md)

MSVC bağlayıcı girişi .netmodule dosyaları kabul eder ve bağlayıcı tarafından üretilen çıkış dosyası bir derleme veya .netmodule herhangi bir bağlayıcıya giriş netmodule'leri hiçbir çalışma zamanı bağımlılığa sahip olacaktır.  Daha fazla bilgi için [bağlayıcı girişi olarak .netmodule dosyaları](netmodule-files-as-linker-input.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Tıklayın **bağlayıcı** klasör.

1. Tıklayın **giriş** özellik sayfası.

1. Değiştirme **derlemeye Modül Ekle** özelliği.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AddModuleNamesToAssembly%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC Bağlayıcı Seçenekleri](linker-options.md)
