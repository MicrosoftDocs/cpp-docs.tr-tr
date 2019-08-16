---
title: /MANIFESTDEPENDENCY (Bildirim Bağımlılıklarını Belirt)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.AdditionalManifestDependencies
helpviewer_keywords:
- MANIFESTDEPENDENCY linker option
- /MANIFESTDEPENDENCY linker option
- -MANIFESTDEPENDENCY linker option
ms.assetid: e4b68313-33a2-4c3e-908e-ac2b9f7d6a73
ms.openlocfilehash: 43239efe70cc555d1a7e03c5d67e99e40ccd480e
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69492704"
---
# <a name="manifestdependency-specify-manifest-dependencies"></a>/MANIFESTDEPENDENCY (Bildirim Bağımlılıklarını Belirt)

```
/MANIFESTDEPENDENCY:manifest_dependency
```

## <a name="remarks"></a>Açıklamalar

/Manifestdependency, bildirim dosyasının \<bağımlılık > bölümüne yerleştirilecek öznitelikleri belirtmenize olanak tanır.

Bildirim dosyası oluşturma hakkında bilgi için bkz. [/manifest (yan yana derleme bildirimi oluşturma)](manifest-create-side-by-side-assembly-manifest.md) .

Bildirim dosyasının \<bağımlılık > bölümü hakkında daha fazla bilgi için bkz. [Publisher yapılandırma dosyaları](/windows/win32/SbsCs/publisher-configuration-files).

/MANIFESTDEPENDENCY bilgileri bağlayıcıya iki şekilde geçirilebilir:

- Doğrudan komut satırına (veya bir yanıt dosyasına)/MANIFESTDEPENDENCYILE.

- Açıklama aracılığıyla [ekleyin](../../preprocessor/comment-c-cpp.md) .

Aşağıdaki örnek, pragma aracılığıyla geçirilmiş bir/MANIFESTDEPENDENCY açıklaması gösterir

```cpp
#pragma comment(linker, "\"/manifestdependency:type='Win32' name='Test.Research.SampleAssembly' version='6.0.0.0' processorArchitecture='X86' publicKeyToken='0000000000000000' language='*'\"")
```

bildirim dosyasında aşağıdaki girdiye neden olur:

```xml
<dependency>
  <dependentAssembly>
    <assemblyIdentity type='Win32' name='Test.Research.SampleAssembly' version='6.0.0.0' processorArchitecture='X86' publicKeyToken='0000000000000000' language='*' />
  </dependentAssembly>
</dependency>
```

Aynı/MANIFESTDEPENDENCY açıklamaları komut satırına aşağıdaki gibi geçirilebilir:

```cmd
"/manifestdependency:type='Win32' name='Test.Research.SampleAssembly' version='6.0.0.0' processorArchitecture='X86' publicKeyToken='0000000000000000' language='*'\"
```

Bağlayıcı/MANIFESTDEPENDENCY açıklamalarını toplar, yinelenen girdileri ortadan kaldırır ve sonra elde edilen XML dizesini bildirim dosyasına ekler.  Bağlayıcı çakışan girdileri bulursa, bildirim dosyası bozulur ve uygulama başlatılamaz (hatanın kaynağını belirten olay günlüğüne bir giriş eklenebilir).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual C++ Studio 'da derleyici ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri** > bağlayıcıbildirim > **dosyası** özellik sayfasını seçin.

1. **Ek bildirim bağımlılıkları** özelliğini değiştirin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

1. Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalManifestDependencies%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC Bağlayıcı Seçenekleri](linker-options.md)
