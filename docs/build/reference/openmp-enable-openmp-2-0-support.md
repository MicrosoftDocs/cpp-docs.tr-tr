---
title: /openmp (OpenMP Desteğini Etkinleştir)
ms.date: 04/15/2019
f1_keywords:
- /openmp
- VC.Project.VCCLCompilerTool.OpenMP
helpviewer_keywords:
- /openmp compiler option [C++]
- -openmp compiler option [C++]
ms.assetid: 9082b175-18d3-4378-86a7-c0eb95664e13
ms.openlocfilehash: d3454650bfaaacd756e5cfc73df056441a39f5ac
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81336201"
---
# <a name="openmp-enable-openmp-support"></a>/openmp (OpenMP Desteğini Etkinleştir)

Derleyicinin OpenMP'ı destekleyen yönergeleri işlemesine [`#pragma omp`](../../preprocessor/omp.md) neden olur.

## <a name="syntax"></a>Sözdizimi

::: moniker range=">= vs-2019"

> **/openmp**\[**:**__deneysel__]

::: moniker-end

::: moniker range="<= vs-2017"

> **/openmp**

::: moniker-end

## <a name="remarks"></a>Açıklamalar

`#pragma omp`[Direktifleri](../../parallel/openmp/reference/openmp-directives.md) ve Yan [tümcelerini](../../parallel/openmp/reference/openmp-clauses.md)belirtmek için kullanılır. **/openmp** bir derlemede belirtilmemişse, derleyici OpenMP yan tümcelerini ve yönergeleri yok sayar. [OpenMP Fonksiyon](../../parallel/openmp/reference/openmp-functions.md) çağrıları **/openmp** belirtilmemiş olsa bile derleyici tarafından işlenir.

::: moniker range=">= vs-2019"

C++ derleyicisi şu anda OpenMP 2.0 standardını desteklemektedir. Ancak Visual Studio 2019 artık SIMD işlevselliği de sunuyor. SIMD kullanmak için **/openmp:experimental** seçeneğini kullanarak derleyin. Bu seçenek, **/openmp** anahtarını kullanırken hem normal OpenMP özelliklerini hem de diğer OpenMP SIMD özelliklerini kullanılamaz hale sağlar.

::: moniker-end

**/openmp** ve **/clr** kullanılarak derlenen uygulamalar yalnızca tek bir uygulama etki alanı işleminde çalıştırılabilir. Birden çok uygulama etki alanı desteklenmez. Diğer bir nokta, modül`.cctor`oluşturucu ( ) çalıştırıldığında, işlemin **/openmp**kullanılarak derlenip derlenmediğini ve uygulamanın varsayılan olmayan bir çalışma süresine yüklenip yüklenmediğini algılar. Daha fazla bilgi için [bkz: appdomain](../../cpp/appdomain.md), [/clr (Ortak Dil Çalışma Zamanı Derlemesi)](clr-common-language-runtime-compilation.md)ve [Karma Derlemelerin Başlatılması](../../dotnet/initialization-of-mixed-assemblies.md).

/openmp ve <xref:System.TypeInitializationException> **/clr** kullanarak **/openmp** derlenen bir uygulamayı varsayılan olmayan bir uygulama etki alanına yüklemeyi denerseniz, `OpenMPWithMultipleAppdomainsException` hata ayıklayıcının dışına bir özel durum atılır ve hata ayıklayıcıya bir özel durum atılır.

Bu özel durumlar aşağıdaki durumlarda da gündeme getirilebilir:

- Uygulamanız **/clr** ile derleniyorsa ancak **/openmp**değil , ve varsayılan olmayan bir uygulama etki alanına yükleniyorsa, işlem **/openmp**kullanılarak derlenmiş bir uygulama içerir.

- **/clr** uygulamanızı, hedef derlemelerini varsayılan olmayan bir uygulama etki alanına yükleyen [regasm.exe](/dotnet/framework/tools/regasm-exe-assembly-registration-tool)gibi bir yardımcı programa geçirirseniz.

Ortak dil runtime kod erişim güvenliği OpenMP bölgelerinde çalışmıyor. Bir CLR kodu erişim güvenlik özniteliği paralel bir bölge dışında uygularsanız, paralel bölgede geçerli olmayacaktır.

Microsoft, kısmen güvenilen arayanlara izin veren **/openmp** uygulamaları yazmanızı önermez. CLR kodu <xref:System.Security.AllowPartiallyTrustedCallersAttribute>erişim güvenlik özniteliklerini kullanmayın.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik Sayfaları** iletişim kutusunu açın. Ayrıntılar için [Visual Studio'da C++ derleyicisi ayarlanın ve özellikler oluşturun.](../working-with-project-properties.md)

1. Yapılandırma **Özellikleri** > **C/C++** > **Dil** özelliği sayfasını genişletin.

1. **OpenMP Destek** özelliğini değiştirin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.OpenMP%2A>.

## <a name="example"></a>Örnek

Aşağıdaki örnek, iş parçacığı havuzu başlatmanın bazı etkilerini ve iş parçacığı havuzunu başladıktan sonra kullanmanın bazı etkilerini gösterir. Bir x64, tek çekirdekli, çift işlemci varsayarsak, iş parçacığı havuzu başlatmak için yaklaşık 16 ms sürer. Bundan sonra, iş parçacığı havuzu için çok az ekstra maliyet var.

**/openmp**kullanarak derlediğinizde, test2 için ikinci çağrı hiçbir zaman / openmp kullanarak derlemek eğer daha uzun çalışır asla **/ openmp-**, hiçbir iş parçacığı havuzu başlangıç var gibi. Bir milyon yinelemede, **/openmp** sürümü test2 için ikinci çağrı için **/ openmp-** sürümü daha hızlıdır. 25 yinelemede, hem **/openmp-** hem de **/openmp** sürümleri saat parçalı ndan daha az dır.

Uygulamanızda yalnızca bir döngü varsa ve 15 ms'den daha az bir alanda çalışıyorsa (makinenizdeki yaklaşık ek yüküne göre ayarlanmışsa), **/openmp** uygun olmayabilir. Daha yüksekse, **/openmp**kullanmayı düşünebilirsiniz.

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

[MSVC Derleyici Seçenekleri](compiler-options.md) \
[MSVC Derleyici Komut Satırı Sözdizimi](compiler-command-line-syntax.md) \
[MSVC'de OpenMP](../../parallel/openmp/openmp-in-visual-cpp.md)
