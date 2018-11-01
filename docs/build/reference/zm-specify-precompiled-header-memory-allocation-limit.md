---
title: /Zm (Önceden Derlenmiş Üst Bilgi Bellek Ayırma Sınırını Belirt)
ms.date: 11/04/2016
f1_keywords:
- /zm
helpviewer_keywords:
- PCH files, memory allocation limit
- Zm compiler option [C++]
- /Zm compiler option [C++]
- precompiled header files, memory allocation limit
- Specify Precompiled Header Memory Allocation Limit compiler option
- cl.exe compiler, memory allocation limit
- .pch files, memory allocation limit
- memory allocation, Memory Allocation Limit compiler option
- -Zm compiler option [C++]
ms.assetid: 94c77d5e-6672-46a7-92e0-3f69e277727d
ms.openlocfilehash: ee42fc2d1065a755fa816a99563ccc9f0108e847
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50634804"
---
# <a name="zm-specify-precompiled-header-memory-allocation-limit"></a>/Zm (Önceden Derlenmiş Üst Bilgi Bellek Ayırma Sınırını Belirt)

Önceden derlenmiş üstbilgileri oluşturmak için derleyicinin ayırdığı bellek miktarını belirler.

## <a name="syntax"></a>Sözdizimi

```
/Zmfactor
```

## <a name="arguments"></a>Arguments

*faktörü*<br/>
Önceden derlenmiş üstbilgileri oluşturmak için derleyicinin kullandığı bellek miktarını belirleyen bir ölçekleme faktörü.

*Faktörü* bağımsız değişken derleyici tarafından tanımlanan iş arabelleğinin varsayılan boyutunun yüzdesidir. Varsayılan değer olan *faktörü* 100 (yüzde) olmakla birlikte daha büyük veya daha küçük miktarları belirtebilirsiniz.

## <a name="remarks"></a>Açıklamalar

Visual C++'ın önceki sürümlerinde, derleyici çeşitli ayrı yığınlar kullanıyordu ve her birinin sınırı sonsuzdu. Şu anda ise, derleyici yığınları toplam yığın boyutu sınırına doğru gerekli oldukça dinamik olarak yükseltir ve yalnızca önceden işlenmiş üstbilgileri oluşturmak için sabit boyutlu bir arabellek gerektirir. Sonuç olarak, **/Zm** derleyici seçeneği nadiren gereklidir.

Derleyicinin yığın alanı kalmadı ve [C1060](../../error-messages/compiler-errors-1/fatal-error-c1060.md) kullanırken bir hata iletisi **/Zm** derleyici seçeneği, çok fazla bellek ayırmış olabilirsiniz. Kaldırmayı düşünün **/Zm** seçeneği. Derleyici [C1076](../../error-messages/compiler-errors-1/fatal-error-c1076.md) hata iletisini yayarsa, [C3859](../../error-messages/compiler-errors-2/compiler-error-c3859.md) iletiyi belirtir *faktörü* kullanarakyenidenderlemeyaptığınızdakullanılmakiçinbağımsızdeğişken **/Zm** derleyici seçeneği.

Aşağıdaki tabloda nasıl *faktörü* bağımsız değişkeni varsayılan Ön derlenmiş üstbilgi arabelleğinin boyut olan 75 MB olduğunu varsayarsanız bellek ayırma sınırını etkiler.

|Değeri *faktörü*|Bellek ayırma sınırı|
|-----------------------|-----------------------------|
|10|7.5 MB|
|100|75 MB|
|200|150 MB|
|1000|750 MB|
|2000|1500 MB|

## <a name="other-ways-to-set-the-memory-allocation-limit"></a>Bellek Ayırma Sınırını Ayırmanın Diğer Yolları

#### <a name="to-set-the-zm-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamında /Zm derleyici seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Gezinti bölmesinde seçin **yapılandırma özellikleri**, **C/C++**, **komut satırı**.

1. Girin **/Zm** derleyici seçeneğini **ek seçenekler** kutusu.

#### <a name="to-set-the-zm-compiler-option-programmatically"></a>/Zm derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)