---
title: /Qimprecise_fwaits (Try Blokları İçindeki fwaits'i Kaldır)
ms.date: 11/04/2016
f1_keywords:
- /Qimprecise_fwaits
helpviewer_keywords:
- -Qimprecise_fwaits compiler option (C++)
- /Qimprecise_fwaits compiler option (C++)
ms.assetid: b1501f21-7e08-4fea-95e8-176ec03a635b
ms.openlocfilehash: 40683382686ea64a80563f3f29b7d3523f4144a8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62319596"
---
# <a name="qimprecisefwaits-remove-fwaits-inside-try-blocks"></a>/Qimprecise_fwaits (Try Blokları İçindeki fwaits'i Kaldır)

Kaldırır `fwait` komutları için iç `try` engeller kullandığınızda [/FP: except](fp-specify-floating-point-behavior.md) derleyici seçeneği.

## <a name="syntax"></a>Sözdizimi

```
/Qimprecise_fwaits
```

## <a name="remarks"></a>Açıklamalar

Bu seçenek, hiçbir etkisi olmaz **/FP: except** de ayrıca belirtilmemişse. Belirtirseniz **/FP: dışında** derleyici seçeneğini ekler bir `fwait` komutunu her kod satırı etrafında bir `try` blok. Bu şekilde, derleyici belirli bir özel durum oluşturan kod satırına tanımlayabilirsiniz. **/ Qimprecise_fwaits** kaldırır iç `fwait` yönergeler, yalnızca geçici bir çözüm bekler bırakarak `try` blok. Bunun yapılması performansı artırır, ancak derleyicinin yalnızca hangi söyleyin mümkün olacaktır `try` blok bir özel durum, hangi satır neden olur.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Tıklayın **C/C++** klasör.

1. Tıklayın **komut satırı** özellik sayfası.

1. Derleyici seçeneğini yazın **ek seçenekler** kutusu.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[/Q Seçenekler (Düşük Düzey İşlemler)](q-options-low-level-operations.md)<br/>
[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)
