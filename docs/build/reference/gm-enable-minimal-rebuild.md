---
title: /Gm (En Az Yeniden Derlemeyi Etkinleştir)
ms.date: 11/12/2018
f1_keywords:
- VC.Project.VCCLCompilerTool.MinimalRebuild
- /Gm
- VC.Project.VCCLWCECompilerTool.MinimalRebuild
helpviewer_keywords:
- /Gm compiler option [C++]
- minimal rebuild
- enable minimal rebuild compiler option [C++]
- Gm compiler option [C++]
- -Gm compiler option [C++]
ms.assetid: d8869ce0-d2ea-40eb-8dae-6d2cdb61dd59
ms.openlocfilehash: 9b928f3add0a2ec10257bf63fe61a824336c19b8
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79439645"
---
# <a name="gm-enable-minimal-rebuild"></a>/Gm (En Az Yeniden Derlemeyi Etkinleştir)

Kullanım dışı. Değiştirilen C++ sınıf tanımlarının (üst bilgi ( C++ . h) dosyalarında depolanan) yeniden derlenmesi gerekip gerekmediğini belirleyen en az yeniden oluşturmayı sağlar.

## <a name="syntax"></a>Sözdizimi

```
/Gm
```

## <a name="remarks"></a>Açıklamalar

**/GD** kullanım dışıdır. Belirli türde üstbilgi dosyası değişiklikleri için bir derlemeyi tetiklemeyebilir. Bu seçeneği projelerinizden güvenle kaldırabilirsiniz. Derleme sürelerini geliştirmek için, bunun yerine önceden derlenmiş üst bilgileri ve artımlı ve paralel derleme seçeneklerini kullanmanızı öneririz. Kullanım dışı bırakılan derleyici seçeneklerinin bir listesi için, [kategoriye göre listelenen derleyici seçenekleri](compiler-options-listed-by-category.md)konusunun **kullanım dışı ve kaldırılmış derleyici seçenekleri** bölümüne bakın.

Derleyici, ilk derleme sırasında projenin. IDB dosyasındaki kaynak dosyalar ve sınıf tanımları arasında bağımlılık bilgilerini depolar. (Bağımlılık bilgileri hangi kaynak dosyanın hangi sınıf tanımına bağlı olduğunu ve tanımın hangi. h dosyasına olduğunu söyler.) Sonraki derleme, değiştirilmiş bir. h dosyası içerse de, bir kaynak dosyanın derlenmesi gerekip gerekmediğini öğrenmek için. IDB dosyasında depolanan bilgileri kullanır.

> [!NOTE]
> En az yeniden oluşturma, ekleme dosyaları arasında değişmez sınıf tanımlarına bağımlıdır. Tüm proje için. IDB dosyasındaki bağımlılık bilgileri oluşturulduğundan, bir proje için sınıf tanımlarının genel olması gerekir (belirli bir sınıfın yalnızca bir tanımı olmalıdır). Projenizdeki bir sınıf için birden fazla tanımınız varsa, en az yeniden derlemeyi devre dışı bırakın.

Artımlı bağlayıcı, [/ZW (Windows çalışma zamanı derlemesi)](zw-windows-runtime-compilation.md) seçeneği kullanılarak. obj dosyalarında yer alan Windows meta verilerini desteklemediğinden, **/GI** seçeneği **/ZW**ile uyumsuzdur.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual C++ Studio 'da derleyici ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri** > **CC++ /**  > **kod oluşturma** Özellik sayfası ' nı seçin.

1. **En az yeniden derlemeyi etkinleştir** özelliğini değiştirin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.MinimalRebuild%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)
