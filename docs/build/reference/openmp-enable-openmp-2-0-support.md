---
title: "-openmp (OpenMP 2.0 desteğini etkinleştir) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /openmp
- VC.Project.VCCLCompilerTool.OpenMP
dev_langs:
- C++
helpviewer_keywords:
- /openmp compiler option [C++]
- -openmp compiler option [C++]
ms.assetid: 9082b175-18d3-4378-86a7-c0eb95664e13
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c8217a901f071f50dbd2d7dfcbffccf4014a9444
ms.sourcegitcommit: a5916b48541f804a79891ff04e246628b5f9a24a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="openmp-enable-openmp-20-support"></a>/openmp (OpenMP 2.0 Desteğini Etkinleştir)
İşlenecek derleyici neden `#pragma` [omp](../../preprocessor/omp.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/openmp  
```  
  
## <a name="remarks"></a>Açıklamalar  
 `#pragma omp`belirtmek için kullanılan [yönergeleri](../../parallel/openmp/reference/openmp-directives.md) ve [yan tümceleri](../../parallel/openmp/reference/openmp-clauses.md). Varsa **/OpenMP** belirtilmemiş bir derlemede derleyici OpenMP yan tümceleri ve yönergeleri göz ardı eder. [OpenMP işlevi](../../parallel/openmp/reference/openmp-functions.md) çağrıları derleyici olsa bile tarafından işlenen **/OpenMP** belirtilmedi.  
  
 Uygulamaları derlenmiş ile **/OpenMP** ve **/CLR** yalnızca bir tek bir uygulama etki alanı işlemde çalıştırılabilir; birden çok uygulama etki alanları desteklenmez. Modül Oluşturucusu (.cctor) çalıştırdığınızda, diğer bir deyişle, bu işlem ile derlenmiş algılar **/OpenMP** ve uygulama varsayılan olmayan çalışma zamanına yüklüyse. Daha fazla bilgi için bkz: [appdomain](../../cpp/appdomain.md), [/CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md), ve [karışık derlemeleri başlatma](../../dotnet/initialization-of-mixed-assemblies.md).  
  
 İle derlenmiş bir uygulamanın yüklemeye çalışırsanız **/OpenMP** ve **/CLR** varsayılan olmayan uygulama etki alanına bir <xref:System.TypeInitializationException> özel hata ayıklayıcı dışında durum ve bir Hata ayıklayıcıda OpenMPWithMultipleAppdomainsException durum.  
  
 Bu özel durumlar da aşağıdaki durumlarda yükseltilebilir:  
  
-   Uygulamanız ile derlenmiş ise **/CLR**, bilgisayardı **/OpenMP**, varsayılan olmayan uygulama etki alanına ancak burada işlemi ile derlenen bir uygulama içeren yüklenir **/ OpenMP**.  
  
-   Geçirirseniz, **/CLR** regasm.exe gibi bir yardımcı uygulamaya ([Regasm.exe (derleme kayıt aracı)](/dotnet/framework/tools/regasm-exe-assembly-registration-tool)), varsayılan olmayan uygulama etki alanına hedef derlemeleri yükler.  
  
 Ortak dil çalışma zamanı 's kod erişim güvenliği OpenMP bölgelerde işe yaramaz. Bir CLR kod erişim güvenliği özniteliği bir paralel bölgesi dışında uygularsanız, paralel bölgede etkin olmayacaktır.  
  
 Microsoft öneren, yazma, **/OpenMP** kısmen sağlayan uygulamalar güvenilen arayanlara kullanarak, <xref:System.Security.AllowPartiallyTrustedCallersAttribute>, veya CLR kod erişim güvenliği öznitelikleri.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Genişletme **yapılandırma özellikleri** düğümü.  
  
3.  Genişletme **C/C++** düğümü.  
  
4.  Seçin **dil** özellik sayfası.  
  
5.  Değiştirme **OpenMP Destek** özelliği.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.OpenMP%2A>.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek iş parçacığı havuzu başlangıç çalışmaya başladıktan sonra iş parçacığı havuzu kullanma karşılaştırması etkilerini bazılarını gösterir. Tek çekirdekli x x64 varsayılarak çift işlemci iş parçacığı havuzu hakkında 16ms başlangıç olarak alır. Bundan sonra ancak var. iş parçacığı havuzu için çok az maliyet  
  
 İle derleme zaman **/OpenMP**, test2 için ikinci çağrı hiçbir zaman ile derleme daha artık çalışır **/openmp-**, hiçbir iş parçacığı havuzu başlangıç olarak. Bir milyon yineleme adresindeki **/OpenMP** sürümüdür daha hızlı bir şekilde **/openmp-** 25 yineleme ve test2 için ikinci çağrı için sürüm **/openmp-** ve **/OpenMP** saati ayrıntı düzeyi'den sürümleri kayıt.  
  
 Bunu yalnızca bir döngü, uygulamanızda varsa ve küçüktür (yaklaşık yükünü makinenizde için ayarlanmış), 15ms içinde çalışan **/OpenMP** uygun olmayabilir ancak fazlasını herhangi bir şey olması durumunda kullanmayıisteyebilirsiniz**/OpenMP**.  
  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)