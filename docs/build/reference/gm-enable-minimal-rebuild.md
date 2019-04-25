---
title: /Gm (En Az Yeniden Derlemeyi Etkinleştir)
ms.date: 11/12/2018
f1_keywords:
- VC.Project.VCCLCompilerTool.MinimalRebuild
- /Gm
- /FD
- VC.Project.VCCLWCECompilerTool.MinimalRebuild
helpviewer_keywords:
- /Gm compiler option [C++]
- minimal rebuild
- enable minimal rebuild compiler option [C++]
- Gm compiler option [C++]
- -Gm compiler option [C++]
ms.assetid: d8869ce0-d2ea-40eb-8dae-6d2cdb61dd59
ms.openlocfilehash: 4a66dda37b84119a4b8bc23f7fc719d50e8786f9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62292074"
---
# <a name="gm-enable-minimal-rebuild"></a>/Gm (En Az Yeniden Derlemeyi Etkinleştir)

Kullanım dışı. Değiştirilmiş C++ sınıf tanımlarını (Üstbilgi (.h) dosyalarında depolanan) içeren C++ kaynak dosyalarının derlenmesi gerekip gerekmediğini belirler. en az yeniden derlemeyi etkinleştirir.

## <a name="syntax"></a>Sözdizimi

```
/Gm
```

## <a name="remarks"></a>Açıklamalar

**/GM derlemeyi** kullanım dışı bırakılmıştır. Üstbilgi dosya değişiklikleri belirli türden bir derleme tetiklemeyebilir. Bu gibi durumlarda, bu seçenek güvenli bir şekilde projelerinizden çıkarabilirsiniz. Derleme sürelerini geliştirmek için önceden derlenmiş üstbilgileri kullanmak ve artımlı ve paralel seçenekleri bunun yerine derleme öneririz. Kullanım dışı derleyici seçeneklerinin bir listesi için bkz. **kullanım dışı ve derleyici seçenekleri kaldırıldı** konusundaki [kategoriye göre listelenmiş derleyici seçenekleri](compiler-options-listed-by-category.md).

Derleyici, sınıf tanımları ve kaynak dosyaları arasındaki bağımlılık bilgileri ilk derleme sırasında projenin .idb dosyasında depolar. (Bağımlılık bilgileri hangi kaynak dosyası hangi sınıf tanımını temel bağımlı olduğunu bildirir ve hangi .h dosya tanımı içinde yer alır.) Sonraki derler .idb dosyasında depolanan bilgileri değiştirilmiş .h dosyası içerse bile bir kaynak dosyası derlenecek gerekip gerekmediğini belirlemek için kullanın.

> [!NOTE]
> En az yeniden derleme sınıfı kullanır tanımları arasında değiştirme olmayan dosyaları içerir. Sınıf tanımları (bulunmamalıdır belirli bir sınıfın sadece bir tanım) bir proje için genel olmalıdır .idb dosyasındaki bağımlılık bilgileri için tüm proje oluşturulduğundan. Projenizdeki bir sınıf için birden fazla tanıma sahip en az yeniden derlemeyi devre dışı bırakın.

Artımlı bağlayıcı kullanılarak .obj dosyalarında dahil Windows meta verileri desteklemediğinden [/ZW (Windows çalışma zamanı derlemesi)](zw-windows-runtime-compilation.md) seçeneği **/GM derlemeyi** seçeneği ile uyumlu  **/ZW**.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **C/C++** > **kod oluşturma** özellik sayfası.

1. Değiştirme **en az yeniden derlemeyi etkinleştir** özelliği.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.MinimalRebuild%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)
