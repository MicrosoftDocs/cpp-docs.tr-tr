---
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
ms.openlocfilehash: b7cbf8de06e698e67e370eb399da5bb00b262895
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50595809"
---
# <a name="od-disable-debug"></a>/Od (Devre Dışı Bırak (Hata Ayıkla))

Programdaki tüm iyileştirmeler devre dışı bırakır ve derleme hızlandırır.

## <a name="syntax"></a>Sözdizimi

```
/Od
```

## <a name="remarks"></a>Açıklamalar

Bu seçenek varsayılandır. Çünkü **/Od** kod taşıma bastırır hata ayıklama işlemi basitleştirir. Hata ayıklama için derleyici seçenekleri hakkında daha fazla bilgi için bkz. [/z7, / zi, /zı (hata ayıklama bilgileri biçimi)](../../build/reference/z7-zi-zi-debug-information-format.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Tıklayın **C/C++** klasör.

1. Tıklayın **iyileştirme** özellik sayfası.

1. Değiştirme **iyileştirme** özelliği.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Optimization%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[/O Seçenekler (Kodu İyileştir)](../../build/reference/o-options-optimize-code.md)<br/>
[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)<br/>
[/Z7, /Zi, /ZI (Hata Ayıklama Bilgileri Biçimi)](../../build/reference/z7-zi-zi-debug-information-format.md)