---
description: Daha fazla bilgi edinin:/Arch (x64)
title: /arch (x64)
ms.date: 10/01/2019
ms.assetid: ecda22bf-5bed-43f4-99fb-88aedd83d9d8
ms.openlocfilehash: 1e9670cdea49c06eda6575fe2cea872072a4e332
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97183080"
---
# <a name="arch-x64"></a>/arch (x64)

X64 üzerinde kod oluşturma mimarisini belirtir. Ayrıca bkz. [/Arch (x86)](arch-x86.md) ve [/Arch (ARM)](arch-arm.md).

## <a name="syntax"></a>Söz dizimi

```
/arch:[AVX|AVX2|AVX512]
```

## <a name="arguments"></a>Bağımsız değişkenler

**/Arch: AVX**<br/>
Intel Gelişmiş vektör Uzantıları yönergelerinin kullanımını sunar.

**/Arch: AVX2**<br/>
Intel Gelişmiş vektör uzantıları 2 yönergelerinin kullanılmasına izin vermez.

**/Arch: AVX512**<br/>
Intel Gelişmiş vektör Uzantıları 512 yönergelerinin kullanımını sunar.

## <a name="remarks"></a>Açıklamalar

**/Arch** seçeneği, özellikle vektör hesaplama Için, ıNTEL ve AMD 'deki işlemcilerde kullanılabilen belirli yönerge kümesi uzantılarının kullanımını mümkün bir şekilde sunar. Genel olarak, en son sunulan işlemciler daha eski işlemciler tarafından desteklenen ek uzantıları destekleyebilir, ancak bir yönerge kümesi uzantısı kullanarak kodu yürütmeden önce [__cpuid](../../intrinsics/cpuid-cpuidex.md) kullanarak belirli bir işlemcinin veya yönerge kümesi uzantısı desteğinin test olması için belgelere danışmanız gerekir.

**/Arch** yalnızca yerel işlevler için kod oluşturmayı etkiler. Derlemek için [/clr](clr-common-language-runtime-compilation.md) kullandığınızda, **/Arch** yönetilen işlevler için kod üretimi üzerinde hiçbir etkiye sahip değildir.

İşlemci uzantıları aşağıdaki özelliklere sahiptir:

- Varsayılan mod, skalar kayan nokta ve vektör hesaplamaları için SSE2 yönergelerini kullanır. Bu yönergeler, tek duyarlıklı, çift duyarlıklı ve 1, 2, 4 veya 8 baytlık tamsayı değerlerinin yanı sıra tek duyarlıklı ve çift duyarlıklı skaler kayan nokta değerlerini 128 bitlik vektörle hesaplamaya izin verir.

- **AVX** , 128 bitin veya 256 bitin vektörlerine izin veren vektör ve kayan nokta skalar yönergeleri için alternatif bir yönerge kodlaması sunmuştur ve tüm vektör sonuçlarını tam vektör boyutuna genişletir. (Eski uyumluluk için, SSE stili vektör yönergeleri, bit 127 ' ün ötesinde tüm bitleri korur.) Çoğu kayan nokta işlemi 256 bite genişletilir.

- **AVX2** , en fazla tamsayı işlemini 256 bitlik vektöre genişletir ve fuse Multiply-Add (FMA) yönergelerinin kullanımını sağlar.

- **AVX-512** , 512 bit vektörlerine ve diğer isteğe bağlı diğer özelliklere izin veren başka bir yönerge kodlama formu sunmuştur. Ek işlemlere yönelik yönergeler de eklenmiştir.

Her **/Arch** seçeneği, bu seçenekle ilişkili diğer vektör olmayan yönergelerin kullanımını da etkinleştirebilir. **/Arch: AVX2** belirtildiğinde bazı bmi yönergelerinin kullanılması örnek olarak kullanılır.

`__AVX__` **/Arch: AVX**, **/Arch: AVX2** veya **/Arch: AVX512** derleyici seçeneği belirtildiğinde Önişlemci sembolü tanımlanmıştır. Ön `__AVX2__` işlemci sembolü, **/Arch: AVX2** veya **/Arch: AVX512** derleyici seçeneği belirtildiğinde tanımlanır. `__AVX512F__` `__AVX512CD__` `__AVX512BW__` `__AVX512DQ__` `__AVX512VL__` **/Arch: AVX512** derleyici seçeneği belirtildiğinde,,, ve önişlemci sembolleri tanımlanmıştır. Daha fazla bilgi için bkz. [önceden tanımlanmış makrolar](../../preprocessor/predefined-macros.md). **/Arch: AVX2** seçeneği Visual Studio 2013 güncelleştirme 2, sürüm 12.0.34567.1 ' de tanıtılmıştır. **/Arch: AVX512** için sınırlı destek visual Studio 2017 ' de eklenmiştir ve visual Studio 2019 ' de genişletilir.

### <a name="to-set-the-archavx-archavx2-or-archavx512-compiler-option-in-visual-studio"></a>Visual Studio 'da/Arch: AVX,/Arch: AVX2 veya/Arch: AVX512 derleyici seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Daha fazla bilgi için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**, **C/C++** klasörünü seçin.

1. **Kod oluşturma** özellik sayfasını seçin.

1. Gelişmiş **yönerge kümesini etkinleştir** açılan kutusunda **Gelişmiş vektör Uzantıları (/Arch: AVX)**, **Gelişmiş vektör uzantıları 2 (/Arch: AVX2)** veya **Gelişmiş vektör Uzantıları 512 (/Arch: AVX512)** seçeneğini belirleyin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableEnhancedInstructionSet%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[/Arch (en düşük CPU mimarisi)](arch-minimum-cpu-architecture.md)<br/>
[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)
