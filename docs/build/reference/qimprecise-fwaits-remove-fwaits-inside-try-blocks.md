---
description: Şu konuda daha fazla bilgi edinin:/Qimprecise_fwaits (TRY blokları Içinde fwait 'i Kaldır)
title: /Qimprecise_fwaits (Try Blokları İçindeki fwaits'i Kaldır)
ms.date: 11/04/2016
f1_keywords:
- /Qimprecise_fwaits
helpviewer_keywords:
- -Qimprecise_fwaits compiler option (C++)
- /Qimprecise_fwaits compiler option (C++)
ms.assetid: b1501f21-7e08-4fea-95e8-176ec03a635b
ms.openlocfilehash: 5f3d96656d062a7e5b0c4ad78ba7cd536069e013
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225628"
---
# <a name="qimprecise_fwaits-remove-fwaits-inside-try-blocks"></a>/Qimprecise_fwaits (Try Blokları İçindeki fwaits'i Kaldır)

`fwait` **`try`** [/FP: except](fp-specify-floating-point-behavior.md) derleyici seçeneğini kullandığınızda iç blokları olan komutları kaldırır.

## <a name="syntax"></a>Syntax

```
/Qimprecise_fwaits
```

## <a name="remarks"></a>Açıklamalar

**/FP: except** de belirtilmemişse, bu seçeneğin hiçbir etkisi yoktur. **/FP: except** seçeneğini belirtirseniz, derleyici `fwait` bir bloktaki her kod satırının çevresine bir komut ekler **`try`** . Bu şekilde, derleyici özel durum üreten belirli kod satırını tanımlayabilir. **/Qimprecise_fwaits** iç `fwait` yönergeleri kaldırır ve yalnızca bloğun etrafında bekler **`try`** . Bu, performansı artırır, ancak derleyici yalnızca hangi **`try`** bloğun özel duruma neden olduğunu söyleyebilir, hangi satırı değil.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **C/C++** klasörünü tıklatın.

1. **Komut satırı** Özellik sayfasına tıklayın.

1. **Ek seçenekler** kutusuna derleyici seçeneğini yazın.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[/Q seçenekler (düşük düzey Işlemler)](q-options-low-level-operations.md)<br/>
[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)
