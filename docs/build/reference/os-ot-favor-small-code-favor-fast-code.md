---
title: /Os, /Ot (Küçük Koda Ayrıcalık Tanı, Hızlı Koda Ayrıcalık Tanı)
description: MSVC derleyici seçenekleri/OS ve/ot kodu iyileştirirken boyut veya hız için kullanılıp kullanılmayacağını belirtir.
ms.date: 07/08/2020
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
ms.openlocfilehash: 384019ddf7b80b8dd4e00197d73d1e4ac536634c
ms.sourcegitcommit: 80c8a512b361bd84e38958beb1a1bf6db7434021
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/09/2020
ms.locfileid: "86180831"
---
# <a name="os-ot-favor-small-code-favor-fast-code"></a>`/Os`, `/Ot` (Küçük koda öncelik ver, hızlı koda tercih et)

EXEs ve DLL 'Lerin boyutunu en aza indirir veya en üst düzeye çıkarır.

## <a name="syntax"></a>Sözdizimi

> **`/Os`**\
> **`/Ot`**

## <a name="remarks"></a>Açıklamalar

**`/Os`**(Küçük koda öncelik ver), derleyicisini hız üzerinden kullanmayı tercih etmek üzere karşılaştırarak, EXEs ve DLL 'Lerin boyutunu en aza indirir. Derleyici, çok sayıda C ve C++ yapısını işlevsel bir makine kodu sırası ile azaltabilir. Bu farklılıklar bazen boyut ve hız açısından bir denge sağlar. **`/Os`** Ve seçenekleri, diğerinin **`/Ot`** yerine bir tercih belirtmenizi sağlar:

**`/Ot`**(Hızlı kodu tercih et), derleyicisini boyut hızının hızını tercih etmek üzere karşılaştırarak, EXEs ve DLL 'Lerin hızını en üst düzeye çıkarır. **`/Ot`**, iyileştirmeler etkinleştirildiğinde varsayılandır. Derleyici, çok sayıda C ve C++ yapısını işlevsel bir makine kodu sırası ile azaltabilir. Bazen, bu farklılıklar boyut ve hız açısından avantajları sunar. **`/Ot`** Seçeneği [`/O2`](o1-o2-minimize-size-maximize-speed.md) (en yüksek hız) seçeneği tarafından kapsanır. **`/O2`** Seçeneği, daha hızlı kod oluşturmak için birkaç seçeneği birleştirir.

> [!NOTE]
> Profil oluşturma test çalıştırmalarından toplanan bilgiler,, veya belirtirseniz, aksi takdirde geçerli olacak tüm iyileştirmeleri geçersiz kılar **`/Ob`** **`/Os`** **`/Ot`** . Daha fazla bilgi için bkz. [Profil temelli iyileştirmeler](../profile-guided-optimizations.md).

### <a name="x86-specific-example"></a>x86 özgü örnek

Aşağıdaki örnek kod, **`/Os`** (küçük koda öncelik ver) seçeneği ve **`/Ot`** (hızlı kodu tercih et) seçeneği arasındaki farkı gösterir:

> [!NOTE]
> Bu örnek, veya kullanırken beklenen davranışı açıklar **`/Os`** **`/Ot`** . Ancak, sürümden sürüme olan derleyici davranışı aşağıdaki koda yönelik farklı iyileştirmelere neden olabilir.

```c
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

Aşağıdaki makine kodu parçasında gösterildiği gibi, *`differ.c`* size () için derlendiği zaman **`/Os`** , derleyici kısa ancak daha yavaş bir kod dizisi oluşturmak için dönüş deyimindeki çarpma ifadesini bir çarpma olarak uygular:

```asm
mov    eax, DWORD PTR _x$[ebp]
imul   eax, 71                  ; 00000047H
```

Alternatif olarak, *`differ.c`* Hız () için derlendiğinde **`/Ot`** , derleyici, dönüş deyimindeki çarpma ifadesini, `LEA` hızlı ancak daha uzun bir kod sırası oluşturmak için bir dizi SHIFT ve yönergeler olarak uygular:

```asm
mov    eax, DWORD PTR _x$[ebp]
mov    ecx, eax
shl    eax, 3
lea    eax, DWORD PTR [eax+eax*8]
sub    eax, ecx
```

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **iyileştirme** özellik sayfasını seçin.

1. **Tercih boyutu veya hız** özelliğini değiştirin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.FavorSizeOrSpeed%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[/O seçenekler (Kodu iyileştir)](o-options-optimize-code.md)<br/>
[MSVC derleyicisi seçenekleri](compiler-options.md)<br/>
[MSVC derleyicisi komut satırı söz dizimi](compiler-command-line-syntax.md)
