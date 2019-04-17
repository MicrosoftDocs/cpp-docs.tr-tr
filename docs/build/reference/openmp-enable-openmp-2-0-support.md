---
title: / OpenMP (OpenMP desteğini etkinleştir)
ms.date: 04/15/2019
f1_keywords:
- /openmp
- VC.Project.VCCLCompilerTool.OpenMP
helpviewer_keywords:
- /openmp compiler option [C++]
- -openmp compiler option [C++]
ms.assetid: 9082b175-18d3-4378-86a7-c0eb95664e13
ms.openlocfilehash: caa06d89c590abd2b3a74a5a6b118d6ba4acd910
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/17/2019
ms.locfileid: "59674272"
---
# <a name="openmp-enable-openmp-support"></a>/ OpenMP (OpenMP desteğini etkinleştir)

İşlenecek derleyicinin [ `#pragma omp` ](../../preprocessor/omp.md) OpenMP desteklemek üzere yönergeleri.

## <a name="syntax"></a>Sözdizimi

::: moniker range=">= vs-2019"

> **/ openmp**\[**:**__Deneysel__]

::: moniker-end

::: moniker range="<= vs-2017"

> **/ OpenMP**

::: moniker-end

## <a name="remarks"></a>Açıklamalar

`#pragma omp` belirtmek için kullanılan [yönergeleri](../../parallel/openmp/reference/openmp-directives.md) ve [yan tümceleri](../../parallel/openmp/reference/openmp-clauses.md). Varsa **/OpenMP** belirtilmediyse bir derlemede derleyicinin yoksaydığı OpenMP yan tümceleri ve yönergeleri. [OpenMP işlevi](../../parallel/openmp/reference/openmp-functions.md) çağrılar derleyici bile tarafından işlenen **/OpenMP** belirtilmemiş.

::: moniker range=">= vs-2019"

C++ Derleyici OpenMP 2.0 standart şu anda destekler. Ancak, Visual Studio 2019 artık SIMD işlevsellik sunar. Kullanarak SIMD kullanmak için derleme **/OpenMP: Deneysel** seçeneği. Bu seçenek hem normal OpenMP özelliklerini etkinleştirir ve ek OpenMP SIMD kullanılamıyor kullanırken özellikleri **/OpenMP** geçin.

::: moniker-end

Her ikisi de kullanılarak derlenmiş uygulamalar **/OpenMP** ve **/CLR** yalnızca tek bir uygulama etki alanı işlemi çalıştırılabilir. Birden çok uygulama etki alanları desteklenmez. Diğer bir deyişle, jeden konstruktor (`.cctor`) olan Çalıştır işlemi kullanılarak derlenir algıladığı **/OpenMP**, ve uygulamanın varsayılan olmayan çalışma zamanına yüklenir. Daha fazla bilgi için [appdomain](../../cpp/appdomain.md), [/CLR (ortak dil çalışma zamanı derlemesi)](clr-common-language-runtime-compilation.md), ve [karışık derlemeleri başlatma](../../dotnet/initialization-of-mixed-assemblies.md).

Her ikisi de kullanılarak derlenmiş bir uygulamayı yüklemeye çalışırsanız **/OpenMP** ve **/CLR** varsayılan olmayan uygulama etki alanına bir <xref:System.TypeInitializationException> özel hata ayıklayıcı dışında durum ve `OpenMPWithMultipleAppdomainsException` özel durumu hata ayıklayıcıda oluşturulur.

Bu özel durumları, aşağıdaki durumlarda da yükseltilebilir:

- Uygulamanızı kullanarak derlenirse **/CLR** ama **/OpenMP**ve bulunduğu işlem içerdiği kullanılarak derlenmiş bir uygulama bir varsayılan olmayan uygulama etki alanına yüklenen   **/OpenMP**.

- Geçirirseniz, **/CLR** bir yardımcı uygulama gibi [regasm.exe](/dotnet/framework/tools/regasm-exe-assembly-registration-tool), varsayılan olmayan uygulama etki alanına, hedef bütünleştirilmiş kodları yükler.

Ortak dil çalışma zamanının kod erişim güvenliği OpenMP bölgelerde çalışmaz. CLR kod erişim güvenlik özniteliği bir paralel bölgenin dışında uygularsanız, paralel bölgenin içinde etkin olmayacaktır.

Microsoft olmayan öneririz, yazdığınız **/OpenMP** kısmen izin uygulamaları güvenilen arayanlar. Kullanmayın <xref:System.Security.AllowPartiallyTrustedCallersAttribute>, ya da herhangi bir CLR kod erişim güvenlik özniteliği.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Genişletin **yapılandırma özellikleri** > **C /C++** > **dil** özellik sayfası.

1. Değiştirme **OpenMP desteği** özelliği.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.OpenMP%2A>.

## <a name="example"></a>Örnek

Aşağıdaki örnek başlatıldıktan sonra iş parçacığı havuzu kullanma ve iş parçacığı havuzu başlangıç etkilerini bazıları gösterilmektedir. İş parçacığı havuzu x x64, tek çekirdekli, çift işlemci, varsayılarak başlatılması yaklaşık 16 ms alır. Bundan sonra çok az iş parçacığı havuzu için bir maliyeti yoktur.

Kullanarak derleme yaptığınızda **/OpenMP**, test2 için yapılan ikinci çağrı hiçbir zaman kullanarak derlerseniz daha artık çalışır **/openmp-**, hiçbir iş parçacığı havuzu başlangıç olduğundan. Bir milyon yineleme sırasında **/OpenMP** sürümüdür daha hızlı bir şekilde **/openmp-** test2 için yapılan ikinci çağrı için sürüm. 25 yinelemeler, her ikisi de **/openmp-** ve **/OpenMP** sürümleri kayıt saat ayrıntı düzeyi küçüktür.

Yalnızca bir döngü, uygulamanızda sahip olduğunuz ve 15 (makinenizde yaklaşık yükü için ayarlanmış), MS'den içinde çalıştırıyorsa **/OpenMP** uygun olmayabilir. Yüksek olması durumunda, göz önünde bulundurmak isteyebilirsiniz **/OpenMP**.

```cpp
// cpp_compiler_options_openmp.cpp
#include <omp.h>
#include <stdio.h>
#include <stdlib.h>
#include <windows.h>

volatile DWORD dwStart;
volatile int global = 0;

double test2(int num_steps) {
   int i;
   global++;
   double x, pi, sum = 0.0, step;

   step = 1.0 / (double) num_steps;

   #pragma omp parallel for reduction(+:sum) private(x)
   for (i = 1; i <= num_steps; i++) {
      x = (i - 0.5) * step;
      sum = sum + 4.0 / (1.0 + x*x);
   }

   pi = step * sum;
   return pi;
}

int main(int argc, char* argv[]) {
   double   d;
   int n = 1000000;

   if (argc > 1)
      n = atoi(argv[1]);

   dwStart = GetTickCount();
   d = test2(n);
   printf_s("For %d steps, pi = %.15f, %d milliseconds\n", n, d, GetTickCount() - dwStart);

   dwStart = GetTickCount();
   d = test2(n);
   printf_s("For %d steps, pi = %.15f, %d milliseconds\n", n, d, GetTickCount() - dwStart);
}
```

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md) \
[MSVC derleyici komut satırı sözdizimi](compiler-command-line-syntax.md) \
[MSVC'da OpenMP](../../parallel/openmp/openmp-in-visual-cpp.md)
