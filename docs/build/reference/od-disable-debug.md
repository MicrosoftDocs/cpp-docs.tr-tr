---
description: Daha fazla bilgi edinin:/OD (devre dışı bırak (Hata Ayıkla))
title: /Od (Devre Dışı Bırak (Hata Ayıkla))
ms.date: 11/04/2016
f1_keywords:
- /od
helpviewer_keywords:
- no optimizations
- fast compiling
- /Od compiler option [C++]
- disable optimizations
- Od compiler option [C++]
- -Od compiler option [C++]
- disable (debug) compiler option [C++]
ms.assetid: b1ac31b7-e086-4eeb-be5e-488f7513f5f5
ms.openlocfilehash: 9d425244a1790a9bb74e1c92db88f32bb0372ab2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97214311"
---
# <a name="od-disable-debug"></a>/Od (Devre Dışı Bırak (Hata Ayıkla))

Programdaki tüm iyileştirmeleri kapatır ve derlemeyi hızlandırır.

## <a name="syntax"></a>Syntax

```
/Od
```

## <a name="remarks"></a>Açıklamalar

Bu seçenek varsayılandır. **/Od** kod hareketini bastırdığı için hata ayıklama işlemini basitleştirir. Hata ayıklama için derleyici seçenekleri hakkında daha fazla bilgi için bkz. [/Z7,/Zi,/ZI (hata ayıklama bilgileri biçimi)](z7-zi-zi-debug-information-format.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **C/C++** klasörünü tıklatın.

1. **İyileştirme** Özellik sayfasına tıklayın.

1. **Optimizasyon** özelliğini değiştirin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Optimization%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[/O seçenekler (kodu Iyileştirme)](o-options-optimize-code.md)<br/>
[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)<br/>
[/Z7,/Zi,/ZI (hata ayıklama bilgileri biçimi)](z7-zi-zi-debug-information-format.md)
