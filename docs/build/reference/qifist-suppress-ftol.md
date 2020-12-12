---
description: Daha fazla bilgi edinin:/QIfist (_ftol gösterme)
title: /QIfist (Suppress _ftol)
ms.date: 11/04/2016
f1_keywords:
- /qifist
helpviewer_keywords:
- QIfist compiler option [C++]
- -QIfist compiler option [C++]
- /QIfist compiler option [C++]
ms.assetid: 1afd32a5-f658-4b66-85f4-e0ce4cb955bd
ms.openlocfilehash: 79e9242d66b532f558307d05b222b2fd8cfd43ab
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225654"
---
# <a name="qifist-suppress-_ftol"></a>/QIfist (Suppress _ftol)

Kullanım dışı. `_ftol`Bir kayan nokta türünden integral türüne dönüştürme gerektiğinde yardımcı işlevin çağrısını bastırır.

## <a name="syntax"></a>Syntax

```
/QIfist
```

## <a name="remarks"></a>Açıklamalar

> [!NOTE]
> **/Qifist** yalnızca x86 'yi hedefleyen derleyicide kullanılabilir; Bu derleyici seçeneği, x64 orARM 'yi hedefleyen derleyicilerde kullanılamaz.

Bir kayan nokta türünden integral türüne dönüştürmenin yanı sıra, `_ftol` işlevi, denetim sözcüğünün bit 10 ve 11 ' i ayarlanarak kayan nokta biriminin (FPU) yuvarlama modunun sıfıra (Truncate) doğru olmasını sağlar. Bu, ANSI C standardı tarafından açıklandığı şekilde bir kayan nokta türünden integral türüne dönüştürmenin (sayının kesirli kısmı atılır) meydana gelir. **/QIfist** kullanılırken, bu garanti artık geçerli değildir. Yuvarlama modu, Intel Başvuru Kılavuzu ' nda belgelenen dört bir tane olacaktır:

- En yakın (eşif ise eşit sayı)

- Negatif sonsuza doğru yuvarla

- Pozitif sonsuza yuvarla

- Sıfıra yuvarla

FPU 'nin yuvarlama davranışını değiştirmek için [_control87, _controlfp, \_ _control87_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md) C Run-Time işlevini kullanabilirsiniz. FPU 'nın varsayılan yuvarlama modu "en yakına yuvarlanır". **/Qifist** kullanmak uygulamanızın performansını iyileştirebilir, ancak risk olmadan kullanılamaz. Üretim ortamlarında **/Qifist** ile oluşturulan koda bağlı olmadan önce, kodunuzun, yuvarlama modlarında hassas olan kısımlarını kapsamlı bir şekilde test etmelisiniz.

[/Arch (x86)](arch-x86.md) ve **/qifist** aynı compiland üzerinde kullanılamaz.

> [!NOTE]
> Varsayılan olarak, yuvarlama bitleri kayan nokta yuvarlama (her hesaplamadan sonra meydana gelir) olarak kayan nokta yuvarlama için de etkilediği için **/Qifist** varsayılan olarak etkin değildir, bu nedenle, C stili için bayrakları ayarladığınızda (sıfıra doğru), kayan nokta hesaplamalarınız farklı olabilir. Kodunuz, kayan noktalı sayının kesirli kısmını kesilmesinin beklenen davranışına bağımlıysa, **/Qifist** kullanılmamalıdır. Emin değilseniz, **/Qifist** kullanmayın.

**/Qifist** seçeneği, Visual Studio 2005 ' den itibaren kullanımdan kaldırılmıştır. Derleyici, kayan nokta dönüştürme hızına göre önemli geliştirmeler yaptı. Kullanım dışı bırakılan derleyici seçeneklerinin bir listesi için, bkz. [kategoriye göre listelenen derleyici seçeneklerinde](compiler-options-listed-by-category.md) **kullanım dışı ve kaldırılmış derleyici seçenekleri** .

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
