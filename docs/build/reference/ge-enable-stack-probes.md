---
title: -Ge (yığın yoklamalarını etkinleştir) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /ge
dev_langs:
- C++
helpviewer_keywords:
- -Ge compiler option [C++]
- enable stack probes
- /Ge compiler option [C++]
- stack, stack probes
- stack probes
- stack checking calls
- Ge compiler option [C++]
ms.assetid: 4b54deae-4e3c-4bfa-95f3-ba23590f7258
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f1819e3e8aa5f48c36b8fc48641f13ac6059043e
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45720934"
---
# <a name="ge-enable-stack-probes"></a>/Ge (Yığın Yoklamalarını Etkinleştir)

Yerel değişkenler için depolama gerektiren her işlev çağrısının yığın araştırmaları etkinleştirir.

## <a name="syntax"></a>Sözdizimi

```
/Ge
```

## <a name="remarks"></a>Açıklamalar

Bu mekanizma, yığın araştırma işlevselliğini yeniden yararlıdır. Kullanmanız önerilir [/Gh (_penter kanca işlevini etkinleştir)](../../build/reference/gh-enable-penter-hook-function.md) yığın araştırma yeniden yazma yerine.

[/GS (Denetim yığını denetleme çağrı)](../../build/reference/gs-control-stack-checking-calls.md) aynı etkiye sahiptir.

**/Ge** olan; Visual Studio 2005'te başlayarak kullanım dışı derleyici otomatik olarak yığın denetimi oluşturur. Kullanım dışı derleyici seçeneklerinin bir listesi için bkz. **kullanım dışı ve derleyici seçenekleri kaldırıldı** içinde [kategoriye göre listelenmiş derleyici seçenekleri](../../build/reference/compiler-options-listed-by-category.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Tıklayın **C/C++** klasör.

1. Tıklayın **komut satırı** özellik sayfası.

1. Derleyici seçeneğini yazın **ek seçenekler** kutusu.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)