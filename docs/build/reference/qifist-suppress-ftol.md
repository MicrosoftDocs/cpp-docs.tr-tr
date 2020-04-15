---
title: /QIfist (Suppress _ftol)
ms.date: 11/04/2016
f1_keywords:
- /qifist
helpviewer_keywords:
- QIfist compiler option [C++]
- -QIfist compiler option [C++]
- /QIfist compiler option [C++]
ms.assetid: 1afd32a5-f658-4b66-85f4-e0ce4cb955bd
ms.openlocfilehash: 5d6e12a1003ea125b0da4bfef580d8096e97553a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81336097"
---
# <a name="qifist-suppress-_ftol"></a>/QIfist (Suppress _ftol)

Kullanım dışı. Kayan nokta türünden integral `_ftol` türüne dönüştürme gerektiğinde yardımcı işlevin çağrısını bastırır.

## <a name="syntax"></a>Sözdizimi

```
/QIfist
```

## <a name="remarks"></a>Açıklamalar

> [!NOTE]
> **/QIfist** sadece x86'yı hedefleyen derleyicide mevcuttur; bu derleyici seçeneği x64 veyaARM hedefleyen derleyicilerde kullanılamaz.

`_ftol` İşlev, kayan nokta türünden integral türüne dönüştürmenin yanı sıra, denetim sözcüğünün 10 ve 11 bitlerini ayarlayarak kayan nokta biriminin (FPU) yuvarlama modunun sıfıra (budanma) doğru olmasını sağlar. Bu, kayan nokta türünden integral türüne dönüştürmenin ANSI C standardında açıklandığı gibi oluştuğunu garanti eder (sayının kesirli kısmı atılır). **/QIfist**kullanırken, bu garanti artık geçerli değildir. Yuvarlama modu, Intel başvuru kılavuzlarında belgelenen dört moddan biri olacaktır:

- En yakına doğru yuvarlama (eşit uzaklıktaysa çift sayı)

- Negatif sonsuzluğa doğru yuvarlama

- Pozitif sonsuzluğa doğru yuvarlama

- Sıfıra doğru yuvarlama

FPU'nun yuvarlama davranışını değiştirmek için [_control87, _controlfp _control87_2 \_](../../c-runtime-library/reference/control87-controlfp-control87-2.md) C Çalışma Zamanı işlevini kullanabilirsiniz. FPU'nun varsayılan yuvarlama modu "En yakına doğru yuvarlama" olur. **/QIfist** kullanmak uygulamanızın performansını artırabilir, ancak risk olmadan değil. Üretim ortamlarında **/QIfist** ile oluşturulmuş koda güvenmeden önce, kodunuzun yuvarlama modlarına duyarlı bölümlerini iyice test etmelisiniz.

[/arch (x86)](arch-x86.md) ve **/QIfist** aynı derlemede kullanılamaz.

> [!NOTE]
> **/QIfist** varsayılan olarak geçerli değildir, çünkü yuvarlama uçları kayan nokta yuvarlama noktasını da etkiler (her hesaplamadan sonra oluşur), bu nedenle C stili (sıfıra doğru) yuvarlama için bayrakları ayarladığınızda, kayan nokta hesaplamalarınız farklı olabilir. **/QIfist,** kodunuz kayan nokta sayısının kesirli kısmını keserek beklenen davranışa bağlıysa kullanılmamalıdır. Emin değilseniz, **/QIfist**kullanmayın.

**/QIfist** seçeneği Visual Studio 2005'ten itibaren amortismana hazırdır. Derleyici int dönüşüm hızı float önemli iyileştirmeler yaptı. Azalan derleyici seçenekleri listesi için, [Kategoriye Göre Listelenen Derleyici Seçenekleri'nde](compiler-options-listed-by-category.md) **Azalan ve Kaldırılan Derleyici Seçenekleri'ne** bakın.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik Sayfaları** iletişim kutusunu açın. Ayrıntılar için [Visual Studio'da C++ derleyicisi ayarlanın ve özellikler oluşturun.](../working-with-project-properties.md)

1. **C/C++** klasörünü tıklatın.

1. Komut **Satırı** özelliği sayfasını tıklatın.

1. **Ek Seçenekler** kutusuna derleyici seçeneğini yazın.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[/Q Seçenekler (Düşük Düzey İşlemler)](q-options-low-level-operations.md)<br/>
[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)
