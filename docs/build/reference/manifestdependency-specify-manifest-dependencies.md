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
ms.openlocfilehash: 676059b8d398fd108d8f8fc163c85a3da3c657b4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62321598"
---
# <a name="manifestdependency-specify-manifest-dependencies"></a>/MANIFESTDEPENDENCY (Bildirim Bağımlılıklarını Belirt)

```
/MANIFESTDEPENDENCY:manifest_dependency
```

## <a name="remarks"></a>Açıklamalar

/ MANIFESTDEPENDENCY yerleştirilecek öznitelikleri belirlemenizi sağlar \<bağımlılık > bölümüne bildirim dosyasının.

Bkz: [/MANIFEST (oluşturma yan yana derleme bildirimi)](manifest-create-side-by-side-assembly-manifest.md) bir bildirim dosyası oluşturma hakkında daha fazla bilgi için.

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

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **bağlayıcı** > **bildirim dosyası** özellik sayfası.

1. Değiştirme **ek bildirim bağımlılıkları** özelliği.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

1. Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalManifestDependencies%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC Bağlayıcı Seçenekleri](linker-options.md)
