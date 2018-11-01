---
title: /arch (x86)
ms.date: 11/04/2016
ms.assetid: 9dd5a75d-06e4-4674-aade-33228486078d
ms.openlocfilehash: fb115d564ca24ff29e120e0d8c25e0dbe28024cb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50549714"
---
# <a name="arch-x86"></a>/arch (x86)

X86 kod oluşturma mimarisini belirtir. Ayrıca bkz: [/arch (x64)](../../build/reference/arch-x64.md) ve [/arch (ARM)](../../build/reference/arch-arm.md).

## <a name="syntax"></a>Sözdizimi

```
/arch:[IA32|SSE|SSE2|AVX|AVX2]
```

## <a name="arguments"></a>Arguments

**/arch:IA32**<br/>
Gelişmiş yönerge yok ve kayan nokta hesaplamalarının için x87 da belirtir.

**/arch:SSE**<br/>
SSE yönergeleri kullanımını etkinleştirir.

**/ arch: SSE2**<br/>
SSE2 yönergelerinin kullanımını etkinleştirir. Varsayılan yönerge x86 budur platformları hiçbir **/arch** seçeneği belirtildi.

**/ arch:**<br/>
Intel Gelişmiş vektör uzantıları yönergelerinin kullanımını etkinleştirir.

**/arch:AVX2**<br/>
Intel Gelişmiş vektör uzantıları 2 yönergeleri kullanımını etkinleştirir.

## <a name="remarks"></a>Açıklamalar

SSE ve SSE2 yönergelerini çeşitli Intel ve AMD işlemciler üzerinde yok. AVX yönerge Kumlu köprüsü Intel işlemcileri ve Bulldozer AMD işlemciler üzerinde yok. AVX2 yönerge, Intel Haswell ve Broadwell işlemciler ve AMD Excavator tabanlı işlemciler tarafından desteklenir.

`_M_IX86_FP`, `__AVX__` Ve `__AVX2__` makroları, belirtmek, varsa, **/arch** derleyici seçeneği kullanıldı. Daha fazla bilgi için [önceden tanımlanmış makrolar](../../preprocessor/predefined-macros.md). **/Arch:AVX2** seçeneği ve `__AVX2__` makrosu, Visual Studio 2013 Update 2 ', sürüm 12.0.34567.1 sunulmuştur.

İyileştirici ne zaman ve nasıl SSE ve SSE2 yönergelerini kullanın seçtiği zaman **/arch** belirtilir. SSE kullanır ve SSE2 yönergelerini kayan nokta x87 yerine SSE/SSE2 yönergelerini ve kayıtları kullanmak daha hızlıdır olduğunu belirlediğinde, skaler bazı kayan nokta hesaplamalar için yığın kaydedin. Sonuç olarak, kodunuzu kayan nokta hesaplamaları için gerçekten bir karışımını x87 hem SSE/SSE2 kullanabilir. Ayrıca, ile **/arch: SSE2**, SSE2 yönergelerini bazı 64-bit tamsayı işlemler için kullanılabilir.

SSE ve SSE2 yönergelerini kullanmaya ek olarak, derleyici, SSE ve SSE2 desteği işlemci sürümlerini mevcut olan diğer yönergeleri de kullanır. İlk Pentium Pro düzeltme Intel işlemci üzerinde görünen CMOV yönerge buna bir örnektir.

Derleyici oluşturur x86 varsayılan olarak SSE2 yönergeleri kullanan kod olduğundan, belirtmelisiniz **/arch:IA32** x86 için SSE ve SSE2 yönergelerine nesil devre dışı bırakmak için işlemci.

**/ arch** yalnızca kod oluşturma için yerel işlevleri etkiler. Kullanırken [/CLR](../../build/reference/clr-common-language-runtime-compilation.md) derlemek için **/arch** kod oluşturma için yönetilen işlevler üzerinde etkisi yoktur.

**/ arch** ve [/QIfist](../../build/reference/qifist-suppress-ftol.md) aynı derlenecek üzerinde kullanılamaz. Kullanmıyorsanız, özellikle `_controlfp` FP denetim sözcüğünü ve ardından 53-bit çalışma zamanı başlatma kümeleri x87 FPU denetimi kod word duyarlık denetimi alanı değiştirmek için. Bu nedenle, her bir float ve bir ifadede çift işlemi 53-bit anlam ve 15-bit üs kullanır. Ancak, her SSE tek duyarlıklı işlemi 24 bit anlam ve 8-bit üs kullanır ve SSE2 çift duyarlıklı işlemleri 53-bit anlam ve 11 bit üs kullanır. Daha fazla bilgi için [_control87, _controlfp, \__control87_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md). Bu farklılıklar, bir ifade ağacı, ancak burada bir kullanıcı atama sonra her bir alt ifade söz konusu değil durumlarda mümkündür. Aşağıdakileri göz önünde bulundurun:

```cpp
r = f1 * f2 + d;  // Different results are possible on SSE/SSE2.
```

Karşılaştırma:

```cpp
t = f1 * f2;   // Do f1 * f2, round to the type of t.
r = t + d;     // This should produce the same overall result
               // whether x87 stack is used or SSE/SSE2 is used.
```

### <a name="to-set-this-compiler-option-for-avx-avx2-ia32-sse-or-sse2-in-visual-studio"></a>Visual Studio'da AVX, AVX2, IA32, SSE veya SSE2 için bu derleyici seçeneğini ayarlamak için

1. Açık **özellik sayfaları** iletişim kutusu için proje. Daha fazla bilgi için [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri**, **C/C++** klasör.

1. Seçin **kod oluşturma** özellik sayfası.

1. Değiştirme **etkinleştirme gelişmiş yönerge kümesi** özelliği.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableEnhancedInstructionSet%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[/arch (En Düşük CPU Mimarisi)](../../build/reference/arch-minimum-cpu-architecture.md)<br/>
[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)