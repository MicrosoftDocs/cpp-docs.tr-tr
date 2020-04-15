---
title: /Gy (İşlev Düzeyi Bağlamayı Etkinleştir)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.EnableFunctionLevelLinking
- /gy
- VC.Project.VCCLWCECompilerTool.EnableFunctionLevelLinking
helpviewer_keywords:
- enable function-level linking compiler option [C++]
- COMDAT function
- Gy compiler option [C++]
- -Gy compiler option [C++]
- /Gy compiler option [C++]
- packaged functions
ms.assetid: 0d3cf14c-ed7d-4ad3-b4b6-104e56f61046
ms.openlocfilehash: 8724ae4d018948c0f6aa9456f229db96878d7bf2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328275"
---
# <a name="gy-enable-function-level-linking"></a>/Gy (İşlev Düzeyi Bağlamayı Etkinleştir)

Derleyicinin tek tek işlevleri paketlenmiş işlevler (COMDATs) biçiminde paketlemesine olanak tanır.

## <a name="syntax"></a>Sözdizimi

```
/Gy[-]
```

## <a name="remarks"></a>Açıklamalar

Bağlayıcı, dll veya .exe dosyasındaki tek tek işlevleri dışlamak veya sipariş etmek için işlevlerin COMDA olarak ayrı olarak paketlenir.

Referanssız paket işlevleri .exe dosyasından hariç tutmak için bağlayıcı [/OPT (Optimizasyonlar)](opt-optimizations.md) seçeneğini kullanabilirsiniz.

.exe dosyasında belirli bir sırada paketlenmiş işlevleri eklemek için bağlayıcı [/ORDER (Sırayla İşlevler Koy)](order-put-functions-in-order.md) seçeneğini kullanabilirsiniz.

Satır altı işlevleri her zaman çağrı olarak anında paketlenirse (örneğin, satır ara kapalıysa veya bir işlev adresi alıyorsanız oluşur). Buna ek olarak, sınıf bildiriminde tanımlanan C++ üye işlevleri otomatik olarak paketlenir; diğer işlevler değildir ve bu seçeneğin seçilmesi, bunları paketlenmiş işlevler olarak derlemek için gereklidir.

> [!NOTE]
> Edit ve Continue için kullanılan [/ZI](z7-zi-zi-debug-information-format.md) seçeneği otomatik olarak **/Gy** seçeneğini ayarlar.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik Sayfaları** iletişim kutusunu açın. Ayrıntılar için [Visual Studio'da C++ derleyicisi ayarlanın ve özellikler oluşturun.](../working-with-project-properties.md)

1. **C/C++** klasörünü tıklatın.

1. Kod **Oluşturma** özelliği sayfasını tıklatın.

1. **İşlev Düzeyi Bağlama** özelliğini etkinleştir'i değiştirin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableFunctionLevelLinking%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)
