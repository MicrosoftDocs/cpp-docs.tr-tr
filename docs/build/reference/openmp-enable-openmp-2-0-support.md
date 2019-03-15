---
title: /openmp (OpenMP 2.0 Desteğini Etkinleştir)
ms.date: 11/04/2016
f1_keywords:
- /openmp
- VC.Project.VCCLCompilerTool.OpenMP
helpviewer_keywords:
- /openmp compiler option [C++]
- -openmp compiler option [C++]
ms.assetid: 9082b175-18d3-4378-86a7-c0eb95664e13
ms.openlocfilehash: f1edcc6d29a5b84106b3a5fd91d2446c34e0f7b9
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57807474"
---
# <a name="openmp-enable-openmp-20-support"></a>/openmp (OpenMP 2.0 Desteğini Etkinleştir)

İşlenecek derleyicinin `#pragma` [omp](../../preprocessor/omp.md).

## <a name="syntax"></a>Sözdizimi

```
/openmp
```

## <a name="remarks"></a>Açıklamalar

`#pragma omp` belirtmek için kullanılan [yönergeleri](../../parallel/openmp/reference/openmp-directives.md) ve [yan tümceleri](../../parallel/openmp/reference/openmp-clauses.md). Varsa **/OpenMP** belirtilmemiş bir derlemede derleyicinin yoksaydığı OpenMP yan tümceleri ve yönergeleri. [OpenMP işlevi](../../parallel/openmp/reference/openmp-functions.md) çağrılar derleyici bile tarafından işlenen **/OpenMP** belirtilmedi.

İle derlenmiş uygulamaları **/OpenMP** ve **/CLR** yalnızca tek bir uygulama etki alanı işlemi içinde çalıştırılabilir; birden çok uygulama etki alanları desteklenmez. Jeden konstruktor (.cctor) çalıştırdığınızda, diğer bir deyişle, bu işlem ile derlendiğinde algılar **/OpenMP** ve uygulamanın varsayılan olmayan çalışma zamanına yüklüyse. Daha fazla bilgi için [appdomain](../../cpp/appdomain.md), [/CLR (ortak dil çalışma zamanı derlemesi)](clr-common-language-runtime-compilation.md), ve [karışık derlemeleri başlatma](../../dotnet/initialization-of-mixed-assemblies.md).

İle derlenmiş bir uygulamanın yüklemeye çalışırsanız **/OpenMP** ve **/CLR** varsayılan olmayan uygulama etki alanına bir <xref:System.TypeInitializationException> dışında hata ayıklayıcı özel durum oluşturulur ve Hata ayıklayıcıda OpenMPWithMultipleAppdomainsException özel durum oluşturulur.

Bu özel durumları, aşağıdaki durumlarda da yükseltilebilir:

- Uygulamanız ile derlenmişse **/CLR**, ancak **/OpenMP**, varsayılan olmayan uygulama etki alanına ancak işlemi ile derlenen uygulamanın bulunduğu içerdiği yüklü olduğu **/ OpenMP**.

- Geçirirseniz, **/CLR** regasm.exe gibi bir yardımcı uygulama ([Regasm.exe (derleme kayıt aracı)](/dotnet/framework/tools/regasm-exe-assembly-registration-tool)), varsayılan olmayan uygulama etki alanına, hedef bütünleştirilmiş kodları yükler.

Ortak dil çalışma zamanının kod erişim güvenliği OpenMP bölgelerde çalışmaz. CLR kod erişim güvenlik özniteliği bir paralel bölgenin dışında uygularsanız, paralel bölgenin içinde etkin olmayacaktır.

Microsoft, siz değil yazma arşivlemenin **/OpenMP** kısmen sağlayan uygulamalar güvenilen arayanlar, kullanarak <xref:System.Security.AllowPartiallyTrustedCallersAttribute>, ya da herhangi bir CLR kod erişim güvenlik özniteliği.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Genişletin **yapılandırma özellikleri** düğümü.

1. Genişletin **C/C++** düğümü.

1. Seçin **dil** özellik sayfası.

1. Değiştirme **OpenMP desteği** özelliği.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.OpenMP%2A>.

## <a name="example"></a>Örnek

Aşağıdaki örnek çalışmaya başladıktan sonra iş parçacığı havuzu kullanma ve iş parçacığı havuzu başlangıç etkilerini bazıları gösterilmektedir. Tek çekirdekli bir x64 varsayılarak çift işlemci işten hakkında 16ms başlangıç olarak alır. Bundan sonra yine de çok az maliyet yoktur işten için.

Derleme yaptığınızda **/OpenMP**, hiçbir zaman test2 için yapılan ikinci çağrı ile derleme daha artık çalışır **/openmp-**, hiçbir iş parçacığı havuzu başlangıç olduğundan. Bir milyon yineleme sırasında **/OpenMP** sürümüdür daha hızlı bir şekilde **/openmp-** test2 ve 25 yineleme sırasında yapılan ikinci çağrı için sürüm **/openmp-** ve **/OpenMP** sürümleri kayıt saat ayrıntı düzeyi küçüktür.

Bunu yalnızca bir döngü, uygulamanızda sahip olduğunuz ve küçüktür (makinenizde yaklaşık yükü için ayarlanmış), 15ms içinde çalıştırıyorsa **/OpenMP** uygun olmayabilir ancak daha fazla şey olması durumunda, gözönündebulundurmakisteyebilirsiniz **/OpenMP**.

```
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

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici komut satırı sözdizimi](compiler-command-line-syntax.md)
