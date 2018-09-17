---
title: -Qıfist (_ftol gösterme) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /qifist
dev_langs:
- C++
helpviewer_keywords:
- QIfist compiler option [C++]
- -QIfist compiler option [C++]
- /QIfist compiler option [C++]
ms.assetid: 1afd32a5-f658-4b66-85f4-e0ce4cb955bd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1d7c4bacec9da22e8c8ba9fd6330637a1fb25893
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45714746"
---
# <a name="qifist-suppress-ftol"></a>/QIfist (Suppress _ftol)

Kullanım dışı. Yardımcı işlevini çağrısının bastırır `_ftol` bir kayan nokta türünden bir tamsayı türüne dönüştürme zaman gereklidir.

## <a name="syntax"></a>Sözdizimi

```
/QIfist
```

## <a name="remarks"></a>Açıklamalar

> [!NOTE]
>  **/ Qıfist** yalnızca kullanılabilir x86; hedefleyen derleyicide Bu derleyici seçeneğini x64 hedefleyen derleyicilerde kullanılabilir değil orARM.

Kayan nokta türünden integral türüne dönüştürme yanı sıra `_ftol` işlevi sağlar (FPU) kayan nokta birimi yuvarlama modu sıfıra yakınsayarak (kesme), Denetim sözcüğü bit 10 ve 11 ayarlayarak. Bu, bir kayan nokta türünden bir tamsayı türüne dönüştürme (sayının kesirli kısmını göz ardı edilir) ANSI C standardına göre açıklandığı oluştuğunu garanti eder. Kullanırken **/QIfist**, artık bu garanti geçerlidir. Yuvarlama modu dört biri Intel başvuru kılavuzlarına içinde açıklandığı gibi olacaktır:

- En yakın (çift sayı doğru equidistant varsa) yuvarlar

- Eksi sonsuza doğru yuvarlama

- Pozitif sonsuza doğru yuvarlama

- Sıfıra doğru yuvarlar

Kullanabileceğiniz [_control87, _controlfp, \__control87_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md) FPU yuvarlama davranışını değiştirmek için C çalışma zamanı işlevi. Yuvarlama modu FPU, varsayılan olan "Hepsini doğru en yakın." Kullanarak **/QIfist** riski olmadan değil ancak uygulamanızın performansını iyileştirebilir. Bağlı olan kod ile oluşturulmuş önce modları yuvarlama duyarlıdır kod bölümlerini sınamanız **/QIfist** üretim ortamlarında.

[/ arch (x86)](../../build/reference/arch-x86.md) ve **/QIfist** aynı derlenecek üzerinde kullanılamaz.

> [!NOTE]
>  **/ Qıfist** olan uygulamada varsayılan olarak yuvarlama da bit kayan nokta integralden etkiler çünkü göstermiyor yuvarlama (sonra her hesaplama oluştuğu), C stili (sıfır doğru) yuvarlama bayrakları ayarladığınızda, kayan noktası için hesaplamaları farklı olabilir. **/ Qıfist** kodunuzu kayan noktalı sayının kesirli kısmını kesilmesi, beklenen davranışı bağlıysa kullanılmamalıdır. Emin değilseniz, kullanmayın **/QIfist**.

**/QIfist** seçeneği Visual Studio 2005'ten başlayarak kullanım dışı. Derleyici, float int dönüştürme hızını önemli geliştirmeler yapılmıştır. Kullanım dışı derleyici seçeneklerinin bir listesi için bkz. **kullanım dışı ve derleyici seçenekleri kaldırıldı** içinde [kategoriye göre listelenmiş derleyici seçenekleri](../../build/reference/compiler-options-listed-by-category.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Tıklayın **C/C++** klasör.

1. Tıklayın **komut satırı** özellik sayfası.

1. Derleyici seçeneğini yazın **ek seçenekler** kutusu.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[/Q Seçenekler (düşük düzey işlemler)](../../build/reference/q-options-low-level-operations.md)
[derleyici seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)