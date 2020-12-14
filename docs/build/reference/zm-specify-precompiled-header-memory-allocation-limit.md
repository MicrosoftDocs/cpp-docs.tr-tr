---
description: Daha fazla bilgi edinin:/ZD (önceden derlenmiş üst bilgi bellek ayırma sınırını belirt)
title: /Zm (Önceden Derlenmiş Üst Bilgi Bellek Ayırma Sınırını Belirt)
ms.date: 03/08/2019
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
ms.openlocfilehash: 624d8926961d9ca3d32ef204b70683c14dc3197f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97224393"
---
# <a name="zm-specify-precompiled-header-memory-allocation-limit"></a>/Zm (Önceden Derlenmiş Üst Bilgi Bellek Ayırma Sınırını Belirt)

Önceden derlenmiş üstbilgileri oluşturmak için derleyicinin ayırdığı bellek miktarını belirler.

## <a name="syntax"></a>Söz dizimi

```
/Zmfactor
```

## <a name="arguments"></a>Bağımsız değişkenler

*çarpan*<br/>
Önceden derlenmiş üstbilgileri oluşturmak için derleyicinin kullandığı bellek miktarını belirleyen bir ölçekleme faktörü.

*Factor* bağımsız değişkeni, derleyici tanımlı bir iş arabelleğinin varsayılan boyutunun yüzdesidir. Varsayılan *faktör* değeri 100 ' dir (yüzde), ancak daha büyük veya daha küçük miktarlar belirtebilirsiniz.

## <a name="remarks"></a>Açıklamalar

Visual Studio 2015 ' den önceki sürümlerde, C++ derleyicisi çeşitli ayrı yığınlar kullanıyordu ve her birinin sınırlı bir limiti vardı. Şu anda derleyici, en fazla bir toplam yığın boyutu sınırına kadar gerekli olan yığınların dinamik olarak büyümesi ve önceden derlenmiş üstbilginin birden çok adres aralığını üstlenebilmesi için izin verir. Sonuç olarak, **/zı** derleyici seçeneği nadiren gereklidir.

Derleyicinin yığın alanı tükeniyor ve **/ZD** derleyici seçeneğini kullandığınızda [C1060](../../error-messages/compiler-errors-1/fatal-error-c1060.md) hata iletisini yayıyorsa, çok fazla bellek ayırmış olabilirsiniz. **/ZD** seçeneğini kaldırmayı düşünün.

Derleyici [C1076](../../error-messages/compiler-errors-1/fatal-error-c1076.md) hata iletisini yayıyorsa, bir [C3859](../../error-messages/compiler-errors-2/compiler-error-c3859.md) iletisi, **/ZD** derleyici seçeneğini kullanarak yeniden derleme yaptığınızda kullanılacak *faktör* bağımsız değişkenini belirtir. Bu ileti yalnızca önceden derlenmiş bir üstbilgi kullandığında önemlidir `#pragma hdrstop` . Diğer durumlarda, Windows sanal bellek baskısı sorunlarından kaynaklanan ve **/zı** seçeneğini kullanma önerisi göz ardı edilebilir bir hatadır. Bunun yerine, CL.EXE için **/MP** seçeneği ile birlikte MSBUILD.EXE için **/maxcpucount** seçeneğini kullanırken paralel işlemlerin sayısını azaltmayı göz önünde bulundurun. Daha fazla bilgi için bkz. [önceden derlenmiş üst bilgi (pch) sorunları ve önerileri](https://devblogs.microsoft.com/cppblog/precompiled-header-pch-issues-and-recommendations/).

Aşağıdaki tabloda, varsayılan ön derlenmiş üstbilgi arabelleğinin boyutunun 75 MB olduğunu varsaydıysanız, *faktör* bağımsız değişkeninin bellek ayırma sınırını nasıl etkilediği gösterilmektedir.

|*Faktör* değeri|Bellek ayırma sınırı|
|-----------------------|-----------------------------|
|10|7,5 MB|
|100|75 MB|
|200|150 MB|
|1000|750 MB|
|2000|1500 MB|

## <a name="other-ways-to-set-the-memory-allocation-limit"></a>Bellek Ayırma Sınırını Ayırmanın Diğer Yolları

### <a name="to-set-the-zm-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamında /Zm derleyici seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. Gezinti bölmesinde, **yapılandırma özellikleri**  >  **C/C++**  >  **komut satırı**' nı seçin.

1. **Ek seçenekler** kutusuna **/ZD** derleyici seçeneğini girin.

### <a name="to-set-the-zm-compiler-option-programmatically"></a>/Zm derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)
