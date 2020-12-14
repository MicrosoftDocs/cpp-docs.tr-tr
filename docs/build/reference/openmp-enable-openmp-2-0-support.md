---
description: Daha fazla bilgi edinin:/OpenMP (OpenMP desteğini etkinleştir)
title: /OpenMP (OpenMP desteğini etkinleştir)
ms.date: 04/15/2019
f1_keywords:
- /openmp
- VC.Project.VCCLCompilerTool.OpenMP
helpviewer_keywords:
- /openmp compiler option [C++]
- -openmp compiler option [C++]
ms.assetid: 9082b175-18d3-4378-86a7-c0eb95664e13
ms.openlocfilehash: 818cd6167bf56b9948a3d9f455b0153b4302e8df
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97221988"
---
# <a name="openmp-enable-openmp-support"></a>/OpenMP (OpenMP desteğini etkinleştir)

Derleyicinin, [`#pragma omp`](../../preprocessor/omp.md) OpenMP desteğiyle yönergeleri işlemesini sağlar.

## <a name="syntax"></a>Syntax

::: moniker range=">= msvc-160"

> **/OpenMP** \[ **:**__deneysel__]

::: moniker-end

::: moniker range="<= msvc-150"

> **/OpenMP**

::: moniker-end

## <a name="remarks"></a>Açıklamalar

`#pragma omp`[yönergeleri](../../parallel/openmp/reference/openmp-directives.md) ve [yan tümceleri](../../parallel/openmp/reference/openmp-clauses.md)belirtmek için kullanılır. Derlemede **/OpenMP** belirtilmemişse, derleyici OpenMP yan tümcelerini ve yönergeleri yoksayar. **/OpenMP** belirtilmediği halde [OpenMP işlev](../../parallel/openmp/reference/openmp-functions.md) çağrıları derleyici tarafından işlenir.

::: moniker range=">= msvc-160"

C++ derleyicisi Şu anda OpenMP 2,0 standardını desteklemektedir. Ancak, Visual Studio 2019 artık SıMD işlevselliği de sunmaktadır. SıMD 'yi kullanmak için **/OpenMP: deneysel** seçeneğini kullanarak derleyin. Bu seçenek hem normal OpenMP özelliklerini hem de **/OpenMP** anahtarı kullanılırken ek OPENMP SIMD özelliklerini mümkün değildir.

::: moniker-end

Hem **/OpenMP** hem de **/clr** kullanılarak derlenen uygulamalar yalnızca tek bir uygulama etki alanı işleminde çalıştırılabilir. Birden çok uygulama etki alanı desteklenmez. Diğer bir deyişle, modül Oluşturucusu ( `.cctor` ) çalıştırıldığında, işlemin **/OpenMP** kullanılarak derlendiğini ve uygulamanın varsayılan olmayan bir çalışma zamanına yüklenip yüklenmediğini algılar. Daha fazla bilgi için bkz. [AppDomain](../../cpp/appdomain.md), [/clr (ortak dil çalışma zamanı derlemesi)](clr-common-language-runtime-compilation.md)ve [karma derlemelerin başlatılması](../../dotnet/initialization-of-mixed-assemblies.md).

Varsayılan olmayan bir uygulama etki alanında hem **/OpenMP** hem de **/clr** kullanarak derlenen bir uygulamayı yüklemeye çalışırsanız, <xref:System.TypeInitializationException> hata ayıklayıcı dışında bir özel durum oluşturulur ve `OpenMPWithMultipleAppdomainsException` hata ayıklayıcıda bir özel durum oluşturulur.

Bu özel durumlar aşağıdaki durumlarda da oluşturulabilir:

- Uygulamanız **/clr** kullanılarak derlenirse ancak **/OpenMP** ile derlenmişse ve varsayılan olmayan bir uygulama etki alanına yüklenirse, burada işlemin **/OpenMP** kullanılarak derlenen bir uygulama içermesi gerekir.

- **/Clr** uygulamanızı, hedef derlemelerini varsayılan olmayan bir uygulama etki alanına yükleyen [regasm.exe](/dotnet/framework/tools/regasm-exe-assembly-registration-tool)gibi bir yardımcı programa geçirirseniz.

Ortak dil çalışma zamanının kod erişim güvenliği, OpenMP bölgelerinde çalışmaz. Bir paralel bölge dışında bir CLR kod erişimi güvenlik özniteliği uygularsanız, paralel bölgede etkin olmaz.

Microsoft, kısmen güvenilen çağıranlara izin veren **/OpenMP** uygulamaları yazmanızı önermez. <xref:System.Security.AllowPartiallyTrustedCallersAttribute>Ya da herhangi BIR clr kod erişimi güvenlik özniteliği kullanmayın.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **dil** Özellik sayfası ' nı genişletin.

1. **OpenMP support** özelliğini değiştirin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.OpenMP%2A>.

## <a name="example"></a>Örnek

Aşağıdaki örnek, iş parçacığı havuzu başlatmasının, başlatıldıktan sonra iş parçacığı havuzu kullanımının bazı etkilerini gösterir. Bir x64, tek çekirdekli, Çift işlemcinin olduğu varsayıldığında, iş parçacığı havuzunun başlaması yaklaşık 16 MS sürer. Bundan sonra, iş parçacığı havuzu için çok fazla maliyet vardır.

**/OpenMP** kullanarak derlerken, hiçbir iş parçacığı havuzu başlatma işlemi olmadığından, test2 öğesine yapılan ikinci çağrı, **/OpenMP-** kullanarak derleme yaparsanız daha uzun bir süre çalışmaz. Bir milyon yinelemeyle, **/OpenMP** sürümü, test2 'e yapılan ikinci çağrı için **/OpenMP-** Version değerinden daha hızlıdır. 25 yinelemeden, **/OpenMP-** ve **/OpenMP** sürümleri saat ayrıntı düzeyi 'nden daha az kayıt yaptırın.

Uygulamanızda yalnızca bir döngüdür ve 15 MS 'den az (makinenizde yaklaşık ek yük için ayarlanır) çalıştırıyorsa, **/OpenMP** uygun olmayabilir. Daha yüksekse, **/OpenMP** kullanmayı düşünmek isteyebilirsiniz.

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
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md) \
[MSVC'de OpenMP](../../parallel/openmp/openmp-in-visual-cpp.md)
