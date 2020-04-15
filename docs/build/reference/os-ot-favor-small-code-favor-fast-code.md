---
title: /Os, /Ot (Küçük Koda Ayrıcalık Tanı, Hızlı Koda Ayrıcalık Tanı)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLWCECompilerTool.FavorSizeOrSpeed
- /os
- VC.Project.VCCLCompilerTool.FavorSizeOrSpeed
helpviewer_keywords:
- favor fast code compiler option [C++]
- /Os compiler option [C++]
- Ot compiler option [C++]
- /Ot compiler option [C++]
- small machine code
- -Ot compiler option [C++]
- fast code
- favor small code compiler option [C++]
- Os compiler option [C++]
- -Os compiler option [C++]
ms.assetid: 9a340806-fa15-4308-892c-355d83cac0f2
ms.openlocfilehash: 0eda9461b3ef730e0e0a832aa94a688e03c7e1bb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81336181"
---
# <a name="os-ot-favor-small-code-favor-fast-code"></a>/Os, /Ot (Küçük Koda Ayrıcalık Tanı, Hızlı Koda Ayrıcalık Tanı)

EX'lerin ve DL'lerin boyutunu en aza indirir veya en üst düzeye çıkarır.

## <a name="syntax"></a>Sözdizimi

```
/Os
/Ot
```

## <a name="remarks"></a>Açıklamalar

**/Os** (Favor Small Code), derleyiciye boyutu hızdan daha fazla tercih etmesi için talimat vererek EX'lerin ve DL'lerin boyutunu en aza indirir. Derleyici birçok C ve C++ yapısını işlevsel olarak benzer makine kodu dizilerine indirgeyebilir. Bazen bu farklılıklar boyut karşı hız tradeoffs sunuyoruz. **/Os** ve **/Ot** seçenekleri, biri için bir tercihi diğerinden daha belirtmenize olanak sağlar:

**/Ot** (Favor Fast Code), derleyiciye boyutun üzerindeki hızı tercih etmesini öğreterek EX'lerin ve DL'lerin hızını en üst düzeye çıkarır. (Bu varsayılandır.) Derleyici birçok C ve C++ yapısını işlevsel olarak benzer makine kodu dizilerine indirgeyebilir. Bazen, bu farklılıklar boyut karşı hız tradeoffs sunuyoruz. **/Ot** seçeneği Maksimum Hız ([/O2](o1-o2-minimize-size-maximize-speed.md)) seçeneği ile ima edilir. **/O2** seçeneği, çok hızlı kod üretmek için çeşitli seçenekleri birleştirir.

**/Os** veya **/Ot**kullanıyorsanız, kodu optimize etmek için [/Og'yi](og-global-optimizations.md) de belirtmeniz gerekir.

> [!NOTE]
> Profil oluşturma testi çalıştıran bilgiler, **/Ob**, **/Os**, veya **/Ot**belirtirseniz, aksi takdirde geçerli olacak optimizasyonları geçersiz kılar. Daha fazla bilgi için Profil [Destekli Optimizasyonlar.](../profile-guided-optimizations.md)

**x86 Özel**

Aşağıdaki örnek kod, Favor Small Code (**/Os**) seçenekleri ile Favor Fast Code (**/Ot**) seçeneği arasındaki farkı gösterir:

> [!NOTE]
> /Os veya **/Ot** **/Os** kullanırken beklenen davranışı aşağıda açıklar. Ancak, derleyici davranışı sürüm den serbest bırakılması için aşağıdaki kod için farklı optimizasyonlar neden olabilir.

```
/* differ.c
  This program implements a multiplication operator
  Compile with /Os to implement multiply explicitly as multiply.
  Compile with /Ot to implement as a series of shift and LEA instructions.
*/
int differ(int x)
{
    return x * 71;
}
```

Aşağıdaki makine kodu parçasında gösterildiği gibi, DIFFER.c boyut **(/Os)** için derlendiğinde, derleyici kısa ama daha yavaş bir kod dizisi oluşturmak için dönüş deyimindeki çarpma ifadesini açıkça çarpma olarak uygular:

```
mov    eax, DWORD PTR _x$[ebp]
imul   eax, 71                  ; 00000047H
```

Alternatif olarak, DIFFER.c hız **(/Ot)** için derlendiğinde, derleyici dönüş deyimindeki çarpma ifadesini `LEA` hızlı ama daha uzun bir kod dizisi üretmek için bir dizi kaydırma ve yönerge olarak uygular:

```
mov    eax, DWORD PTR _x$[ebp]
mov    ecx, eax
shl    eax, 3
lea    eax, DWORD PTR [eax+eax*8]
sub    eax, ecx
```

**END x86 Özel**

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik Sayfaları** iletişim kutusunu açın. Ayrıntılar için [Visual Studio'da C++ derleyicisi ayarlanın ve özellikler oluşturun.](../working-with-project-properties.md)

1. **C/C++** klasörünü tıklatın.

1. **Optimizasyon** özelliği sayfasını tıklatın.

1. **İyilik Boyutu veya Hız** özelliğini değiştirin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.FavorSizeOrSpeed%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[/O Seçenekler (Kodu İyileştir)](o-options-optimize-code.md)<br/>
[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)
