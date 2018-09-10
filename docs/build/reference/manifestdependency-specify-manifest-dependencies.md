---
title: -MANIFESTDEPENDENCY (bildirim bağımlılıklarını belirt) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.AdditionalManifestDependencies
dev_langs:
- C++
helpviewer_keywords:
- MANIFESTDEPENDENCY linker option
- /MANIFESTDEPENDENCY linker option
- -MANIFESTDEPENDENCY linker option
ms.assetid: e4b68313-33a2-4c3e-908e-ac2b9f7d6a73
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5b82bd32bec0e665f815563ccea2ee05f6ae5172
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44315424"
---
# <a name="manifestdependency-specify-manifest-dependencies"></a>/MANIFESTDEPENDENCY (Bildirim Bağımlılıklarını Belirt)

```
/MANIFESTDEPENDENCY:manifest_dependency
```

## <a name="remarks"></a>Açıklamalar

/ MANIFESTDEPENDENCY yerleştirilecek öznitelikleri belirlemenizi sağlar \<bağımlılık > bölümüne bildirim dosyasının.

Bkz: [/MANIFEST (oluşturma yan yana derleme bildirimi)](../../build/reference/manifest-create-side-by-side-assembly-manifest.md) bir bildirim dosyası oluşturma hakkında daha fazla bilgi için.

Daha fazla bilgi için \<bağımlılık > bölümüne bildirim dosyası, bkz: [yayımcı yapılandırma dosyaları](/windows/desktop/SbsCs/publisher-configuration-files).

/ MANIFESTDEPENDENCY bilgi iki yoldan biriyle bağlayıcı geçirilebilir:

- Doğrudan komut satırında (veya bir yanıt dosyası) /MANIFESTDEPENDENCY ile.

- Aracılığıyla [yorum](../../preprocessor/comment-c-cpp.md) pragması.

Pragma geçirilen /MANIFESTDEPENDENCY yorum aşağıdaki örnekte,

```cpp
#pragma comment(linker, "\"/manifestdependency:type='Win32' name='Test.Research.SampleAssembly' version='6.0.0.0' processorArchitecture='X86' publicKeyToken='0000000000000000' language='*'\"")
```

Bu, bildirim dosyasındaki şu girdiyi sonuçlanır:

```xml
<dependency>
  <dependentAssembly>
    <assemblyIdentity type='Win32' name='Test.Research.SampleAssembly' version='6.0.0.0' processorArchitecture='X86' publicKeyToken='0000000000000000' language='*' />
  </dependentAssembly>
</dependency>
```

Aynı /MANIFESTDEPENDENCY yorumları komut satırında şu şekilde geçirilebilir:

```cmd
"/manifestdependency:type='Win32' name='Test.Research.SampleAssembly' version='6.0.0.0' processorArchitecture='X86' publicKeyToken='0000000000000000' language='*'\"
```

Bağlayıcı /MANIFESTDEPENDENCY açıklamaları toplamak, yinelenen girişler ortadan kaldırın ve sonra elde edilen XML dizesi bildirim dosyasına ekleyin.  Çakışan girişleri bağlayıcı bulur, bildirim dosyası bozuk hale gelir ve uygulamayı başlatmakta başarısız olacaktır (bir giriş hatanın kaynağını gösteren olay günlüğü için eklenebilir).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **bağlayıcı** > **bildirim dosyası** özellik sayfası.

1. Değiştirme **ek bildirim bağımlılıkları** özelliği.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

1. Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalManifestDependencies%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)