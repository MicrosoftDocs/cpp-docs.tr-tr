---
title: /Arch (x86)
ms.date: 10/01/2019
ms.assetid: 9dd5a75d-06e4-4674-aade-33228486078d
ms.openlocfilehash: b1e5501f6edd3eb016395380ff476250c0c388b9
ms.sourcegitcommit: 4517932a67bbf2db16cfb122d3bef57a43696242
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71816313"
---
# <a name="arch-x86"></a>/Arch (x86)

X86 üzerinde kod oluşturma mimarisini belirtir. Ayrıca bkz. [/Arch (x64)](arch-x64.md) ve [/Arch (ARM)](arch-arm.md).

## <a name="syntax"></a>Sözdizimi

```
/arch:[IA32|SSE|SSE2|AVX|AVX2|AVX512]
```

## <a name="arguments"></a>Bağımsız Değişkenler

**/Arch: ıA32**<br/>
Gelişmiş yönergeler ve ayrıca kayan nokta hesaplamaları için x87 belirtir.

**/Arch: SSE**<br/>
SSE yönergelerinin kullanımını izin vermez.

**/Arch: SSE2**<br/>
SSE2 yönergelerinin kullanımına izin vermez. Bu, **/Arch** seçeneği belirtilmemişse x86 platformlarındaki varsayılan yönergedir.

**/Arch: AVX**<br/>
Intel Gelişmiş vektör Uzantıları yönergelerinin kullanımını sunar.

**/Arch: AVX2**<br/>
Intel Gelişmiş vektör uzantıları 2 yönergelerinin kullanılmasına izin vermez.

**/Arch: AVX512**<br/>
Intel Gelişmiş vektör Uzantıları 512 yönergelerinin kullanımını sunar.

## <a name="remarks"></a>Açıklamalar

**/Arch** seçeneği, özellikle vektör hesaplama Için, ıNTEL ve AMD 'deki işlemcilerde kullanılabilen belirli yönerge kümesi uzantılarının kullanımını mümkün veya devre dışı bırakır. Genel olarak, en son sunulan işlemciler, daha eski işlemciler tarafından desteklenen ek uzantıları destekleyebilir, ancak belirli bir işlemci için veya __ kullanarak yönerge kümesi uzantısı desteği için test için belgelere danışmanız gerekir. [ ](../../intrinsics/cpuid-cpuidex.md)bir yönerge kümesi uzantısı kullanarak kodu yürütmeden önce CPUID.

**/Arch** yalnızca yerel işlevler için kod oluşturmayı etkiler. Derlemek için [/clr](clr-common-language-runtime-compilation.md) kullandığınızda, **/Arch** yönetilen işlevler için kod üretimi üzerinde hiçbir etkiye sahip değildir.

**/Arch** seçenekleri, aşağıdaki özelliklerle birlikte yönerge kümesi uzantılarına başvurur:

- **IA32** , vektör işlemleri olmadan ve kayan nokta hesaplamaları için x87 kullanarak eski 32 bit x86 yönerge kümesidir.

- **SSE** , dört adet tek duyarlıklı kayan nokta değeri vektörlerine sahip hesaplamaya izin verir. Karşılık gelen skaler kayan nokta yönergeleri de eklenmiştir.

- **SSE2** , tek duyarlıklı, çift duyarlıklı ve 1, 2, 4 veya 8 baytlık tamsayı değerlerinin 128 bitlik vektörlerine hesaplamaya izin verir. Çift duyarlıklı skaler yönergeler de eklenmiştir.

- **AVX** , 128 bitin veya 256 bitin vektörlerine izin veren vektör ve kayan nokta skalar yönergeleri için alternatif bir yönerge kodlaması sunmuştur ve tüm vektör sonuçlarını tam vektör boyutuna genişletir. (Eski uyumluluk için, SSE stili vektör yönergeleri, bit 127 ' ün ötesinde tüm bitleri korur.) Çoğu kayan nokta işlemi 256 bite genişletilir.

- **AVX2** , en fazla tamsayı işlemini 256 bitlik vektöre genişletir ve Fuse çarpma-Add (FMA) yönergelerinin kullanımını sağlar.

- **AVX512** , 512 bit vektörlerine ve diğer isteğe bağlı diğer özelliklere izin veren başka bir yönerge kodlama formu sunmuştur. Ek işlemlere yönelik yönergeler de eklenmiştir.

İyileştiricinin ne zaman ve nasıl kullanılacağı, hangi **/Arch** ' ın belirtildiğine bağlı olarak tercih edilir. Skalar kayan nokta hesaplamaları, kullanılabilir olduğunda SSE veya AVX yönergeleriyle gerçekleştirilir. Bazı çağırma kuralları, kayan nokta bağımsız değişkenlerini x87 yığınında geçirmeyi belirtir ve sonuç olarak, kodunuz kayan nokta hesaplamaları için hem x87 hem de SSE/AVX yönergelerinden oluşan bir karışımı kullanabilir. Tamsayı vektör yönergeleri, kullanılabilir olduğunda bazı 64 bit tamsayı işlemleri için de kullanılabilir.

Vektör ve kayan nokta skaler talimatlarına ek olarak, her **/Arch** seçeneği bu seçenekle ilişkili diğer vektör olmayan yönergelerin kullanımını da etkinleştirebilir. Bu örnek, ilk olarak Intel Pentium Pro işlemcilerde görülen CMOVcc yönerge ailesidir. SSE yönergeleri sonraki Intel Pentium III işlemciyle tanıtıldığı için, **/Arch: IA32** belirtildiğinde CMOVcc yönergeleri oluşturulabilir.

Kayan nokta işlemleri normalde x87 kodunda çift duyarlığa (64-bit) yuvarlanır, ancak duyarlık denetimini genişletilmiş duyarlık (80-bit) veya tek duyarlıklı (32-bit) olarak ayarlama dahil olmak üzere FP denetim sözcüğünü değiştirmek için `_controlfp` kullanabilirsiniz. Daha fazla bilgi için bkz. [_control87, _controlfp, @no__t -1 _control87_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md). SSE ve AVX her işlem için ayrı tek duyarlıklı ve çift duyarlıklı yönergelere sahiptir, bu nedenle SSE/AVX kodu için eşdeğer değildir. Bu, kayan nokta işleminin sonucu bir Kullanıcı değişkenine atamak yerine doğrudan daha fazla hesaplamada kullanıldığında sonuçların nasıl yuvarlanacağını değiştirebilir. Aşağıdaki topluluklara bir göz atın:

```cpp
r = f1 * f2 + d;  // Different results are possible on SSE/SSE2.
```

Açık atama ile:

```cpp
t = f1 * f2;   // Do f1 * f2, round to the type of t.
r = t + d;     // This should produce the same overall result
               // whether x87 stack is used or SSE/SSE2 is used.
```

**/Arch** ve [/qifist](qifist-suppress-ftol.md) aynı compiland üzerinde kullanılamaz. **/Qifist** seçeneği, kayan noktanın yuvarlama davranışını tamsayı dönüştürmesi olarak değiştirir. Varsayılan davranış kesin (sıfıra yuvarlanır), ancak **/Qifist** seçeneği kayan nokta ortamı yuvarlama modunun kullanımını belirtir. Bu, tüm kayan noktanın davranışını tamsayı dönüşümlere değiştirdiği için, bu bayrak kullanım dışıdır. SSE veya AVX için derleme yaparken, bir kayan nokta değerini, kayan nokta ortamı yuvarlama modunu kullanarak, bir iç işlev sırası kullanarak bir tamsayıya yuvarlayabilirler:

```cpp
int convert_float_to_int(float x) {
    return _mm_cvtss_si32(_mm_set_ss(x));
}

int convert_double_to_int(double x) {
    return _mm_cvtsd_si32(_mm_set_sd(x));
}
```

@No__t-0, `__AVX__`, `__AVX2__`, `__AVX512F__`, `__AVX512CD__`, `__AVX512BW__`, `__AVX512DQ__` ve `__AVX512VL__` makroları hangisinin varsa **/Arch** derleyici seçeneğinin kullanıldığını gösterir. Daha fazla bilgi için bkz. [önceden tanımlanmış makrolar](../../preprocessor/predefined-macros.md). **/Arch: AVX2** seçeneği ve `__AVX2__` makrosu, Visual Studio 2013 güncelleştirme 2, sürüm 12.0.34567.1 ' de tanıtılmıştı. **/Arch: AVX512** için sınırlı destek visual Studio 2017 ' de eklenmiştir ve visual Studio 2019 ' de genişletilir.

### <a name="to-set-this-compiler-option-for-avx-avx2-avx512-ia32-sse-or-sse2-in-visual-studio"></a>Visual Studio 'da AVX, AVX2, AVX512, ıA32, SSE veya SSE2 için bu derleyici seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Daha fazla bilgi için bkz [. C++ Visual Studio 'da derleyici ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**, **C/C++**  klasör ' i seçin.

1. **Kod oluşturma** özellik sayfasını seçin.

1. **Gelişmiş yönerge kümesini etkinleştir** özelliğini değiştirin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program aracılığıyla ayarlamak için

- @No__t-0 ' a bakın.

## <a name="see-also"></a>Ayrıca bkz.

[/Arch (en düşük CPU mimarisi)](arch-minimum-cpu-architecture.md)<br/>
[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici komut satırı sözdizimi](compiler-command-line-syntax.md)
