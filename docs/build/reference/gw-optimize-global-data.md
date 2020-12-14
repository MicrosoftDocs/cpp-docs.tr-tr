---
description: Daha fazla bilgi edinin:/GW (genel verileri en Iyileştir)
title: /Gw (Genel Verileri En İyileştir)
ms.date: 11/04/2016
f1_keywords:
- /Gw
helpviewer_keywords:
- /Gw compiler option [C++]
- -Gw compiler option [C++]
ms.assetid: 6f90f4e9-5eb8-4c47-886e-631278a5a4a9
ms.openlocfilehash: 2f9a6b9452f09473e650a5453ad2600cc73f0c00
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200149"
---
# <a name="gw-optimize-global-data"></a>/Gw (Genel Verileri En İyileştir)

COMDAT bölümlerindeki küresel verileri iyileştirme için paketleyin.

## <a name="syntax"></a>Syntax

```
/Gw[-]
```

## <a name="remarks"></a>Açıklamalar

**/GW** seçeneği derleyicinin genel verileri tek BIR COMDAT bölümünde paketlamasına neden olur. Varsayılan olarak, **/GW** kapalıdır ve açıkça etkin olmalıdır. Açıkça devre dışı bırakmak için **/GW-** kullanın. Hem **/GW** hem de [/GL](gl-whole-program-optimization.md) etkinleştirildiğinde bağlayıcı, başvurulmayan genel verileri dışlamak veya özdeş salt yazılır genel verileri birleştirmek için birden çok nesne dosyası genelinde COMDAT bölümlerini karşılaştırmak için tam program iyileştirmesi kullanır. Bu, ortaya çıkan ikili yürütülebilir dosyanın boyutunu önemli ölçüde azaltabilir.

Ayrı olarak derleyip bağladığınızda, [/OPT: ref](opt-optimizations.md) bağlayıcı seçeneğini kullanarak, **/GW** seçeneğiyle derlenen nesne dosyalarındaki başvurulmayan genel verileri dışarıda bırakabilirsiniz.

Ayrıca, [/OPT: ICF](opt-optimizations.md) ve [/LTCG](ltcg-link-time-code-generation.md) bağlayıcı seçeneklerini birlikte kullanarak, **/GW** seçeneğiyle derlenen birden çok nesne dosyasında aynı salt okunurdur, genel verileri çalıştırılabilir dosyada birleştirebilirsiniz.

Daha fazla bilgi için bkz. C++ ekip blogu üzerinde [/GW Derleyicisi anahtarı Ile tanışın](https://devblogs.microsoft.com/cppblog/introducing-gw-compiler-switch/) .

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **C/C++** klasörünü seçin.

1. **Komut satırı** özellik sayfasını seçin.

1. **Ek seçenekler** özelliğini **/GW** içerecek şekilde değiştirin ve ardından **Tamam**' ı seçin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)
