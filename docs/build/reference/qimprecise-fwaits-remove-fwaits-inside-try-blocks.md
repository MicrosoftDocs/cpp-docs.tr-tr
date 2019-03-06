---
title: /Qimprecise_fwaits (Try Blokları İçindeki fwaits'i Kaldır)
ms.date: 11/04/2016
f1_keywords:
- /Qimprecise_fwaits
helpviewer_keywords:
- -Qimprecise_fwaits compiler option (C++)
- /Qimprecise_fwaits compiler option (C++)
ms.assetid: b1501f21-7e08-4fea-95e8-176ec03a635b
ms.openlocfilehash: 3f2a0e6bc28fb812e087a689716be6119640ffca
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57422149"
---
# <a name="qimprecisefwaits-remove-fwaits-inside-try-blocks"></a>/Qimprecise_fwaits (Try Blokları İçindeki fwaits'i Kaldır)

Kaldırır `fwait` komutları için iç `try` engeller kullandığınızda [/FP: except](../../build/reference/fp-specify-floating-point-behavior.md) derleyici seçeneği.

## <a name="syntax"></a>Sözdizimi

```
/Qimprecise_fwaits
```

## <a name="remarks"></a>Açıklamalar

Bu seçenek, hiçbir etkisi olmaz **/FP: except** de ayrıca belirtilmemişse. Belirtirseniz **/FP: dışında** derleyici seçeneğini ekler bir `fwait` komutunu her kod satırı etrafında bir `try` blok. Bu şekilde, derleyici belirli bir özel durum oluşturan kod satırına tanımlayabilirsiniz. **/ Qimprecise_fwaits** kaldırır iç `fwait` yönergeler, yalnızca geçici bir çözüm bekler bırakarak `try` blok. Bunun yapılması performansı artırır, ancak derleyicinin yalnızca hangi söyleyin mümkün olacaktır `try` blok bir özel durum, hangi satır neden olur.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Tıklayın **C/C++** klasör.

1. Tıklayın **komut satırı** özellik sayfası.

1. Derleyici seçeneğini yazın **ek seçenekler** kutusu.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[/Q Seçenekler (Düşük Düzey İşlemler)](../../build/reference/q-options-low-level-operations.md)<br/>
[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)
