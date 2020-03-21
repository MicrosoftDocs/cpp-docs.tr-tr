---
title: C++Temel kılavuz uyarıları
ms.date: 10/16/2019
ms.topic: conceptual
ms.assetid: 7c83814a-f21d-4323-ad5f-13bac40d3e38
ms.openlocfilehash: 544c737470a6578e65e82bb3c8cf1824ec93895f
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80079962"
---
# <a name="using-the-c-core-guidelines-checkers"></a>C++ Temel Yönergeleri denetleyicilerini kullanma

C++ Temel yönergeler, uzmanlar ve tasarımcılar tarafından C++ C++ oluşturulan kodlama hakkında taşınabilir bir yönergeler, kurallar ve en iyi uygulamalar kümesidir. Visual Studio şu anda için C++kod çözümleme araçlarının bir parçası olarak bu kuralların bir alt kümesini desteklemektedir. Temel kılavuz dama, Visual Studio 2017 ve Visual Studio 2019 ' de varsayılan olarak yüklenir ve [Visual studio 2015 için bir NuGet paketi olarak kullanılabilir](#vs2015_corecheck).

## <a name="the-c-core-guidelines-project"></a>C++ Temel yönergeler projesi

Bjarne Stroustrup ve diğerleri tarafından oluşturulan C++ temel yönergeler, modern C++ bir şekilde güvenli ve etkili bir şekilde kullanılması için bir kılavuzdur. Yönergeler statik tür güvenliğini ve kaynak güvenliğini vurgular. Bu, dilin hata olasılığı olan kısımlarını ortadan kaldırmaya veya en aza indirmenin yollarını belirler ve kodunuzun daha basit ve daha iyi performans sağlamak için güvenilir bir yol sunar. Bu yönergeler standart C++ temel tarafından korunur. Daha fazla bilgi edinmek için, bkz. belge, [ C++ temel yönergeler](https://isocpp.github.io/CppCoreGuidelines/CppCoreGuidelines)ve GitHub C++ 'daki temel yönergeler belge proje dosyalarına [GitHub](https://github.com/isocpp/CppCoreGuidelines)erişin.

## <a name="enable-the-c-core-check-guidelines-in-code-analysis"></a>Kod çözümlemede C++ çekirdek denetim yönergelerini etkinleştirme

Projeniz için **Özellik sayfaları** Iletişim kutusunun **Kod Analizi** bölümünde **derleme üzerinde Kod analizini etkinleştir** onay kutusunu seçerek projenizde kod analizini etkinleştirebilirsiniz.

![Kod Analizi genel ayarları için özellik sayfası](../code-quality/media/cppcorecheck_codeanalysis_general.png)

C++ Çekirdek denetim kuralları, kod analizi etkinleştirildiğinde çalışan varsayılan kural kümelerine yönelik uzantılardır. C++ Çekirdek denetim kuralları geliştirme aşamasındadır, bazı kurallar iyi oluşturulmuştur ve bazıları tüm kodda kullanıma hazırlanmayabilir, ancak yine de bilgilendirici olabilir. Kurallar iki gruba ayrılmıştır: yayınlandı ve deneysel. Yayınlanan veya deneysel kuralların projenizin özelliklerinde çalıştırılıp çalıştırılmayacağını seçebilirsiniz.

![Kod Analizi uzantıları ayarları için özellik sayfası](../code-quality/media/cppcorecheck_codeanalysis_extensions.png)

C++ Çekirdek denetimi kural kümelerini etkinleştirmek veya devre dışı bırakmak için, projeniz Için **Özellik sayfaları** iletişim kutusunu açın. **Yapılandırma özellikleri**altında, **Kod Analizi**, **Uzantılar**' ı genişletin. **Çekirdek C++ denetimini etkinleştir (serbest bırakıldı)** veya **çekirdek denetimini etkinleştir C++ (deneysel)** seçeneğinin yanındaki aşağı açılan denetimde **Evet** veya **Hayır**' ı seçin. Değişikliklerinizi kaydetmek için **Tamam ' ı** veya **Uygula** ' yı seçin.

## <a name="examples"></a>Örnekler

C++ Temel denetim kurallarının bulabileceği bazı sorunların bir örneği aşağıda verilmiştir:

```cpp
// CoreCheckExample.cpp
// Add CppCoreCheck package and enable code analysis in build for warnings.

int main()
{
    int arr[10];           // warning C26494
    int* p = arr;          // warning C26485

    [[gsl::suppress(bounds.1)]] // This attribute suppresses Bounds rule #1
    {
        int* q = p + 1;    // warning C26481 (suppressed)
        p = q++;           // warning C26481 (suppressed)
    }

    return 0;
}
```

Bu örnek, C++ çekirdek denetim kurallarının bulabileceği bazı uyarıları gösterir:

- C26494, kural türü. 5: her zaman bir nesne başlatın.

- C26485, kural sınırlardır. 3: bir dizi işaretçiden işaretçiye sınır yok.

- C26481 kural sınırları. 1: işaretçi aritmetiği kullanmayın. Bunun yerine `span` kullanın.

Bu kodu C++ derlerken çekirdek denetim kodu analizi RuleSets 'ler yüklenip etkinleştirildiyse, ilk iki uyarı çıkışlardır, ancak üçüncüsü bastırılır. Örnek koddan derleme çıktısı aşağıda verilmiştir:

```Output
1>------ Build started: Project: CoreCheckExample, Configuration: Debug Win32 ------
1>  CoreCheckExample.cpp
1>  CoreCheckExample.vcxproj -> C:\Users\username\documents\visual studio 2015\Projects\CoreCheckExample\Debug\CoreCheckExample.exe
1>  CoreCheckExample.vcxproj -> C:\Users\username\documents\visual studio 2015\Projects\CoreCheckExample\Debug\CoreCheckExample.pdb (Full PDB)
c:\users\username\documents\visual studio 2015\projects\corecheckexample\corecheckexample\corecheckexample.cpp(6): warning C26494: Variable 'arr' is uninitialized. Always initialize an object. (type.5: http://go.microsoft.com/fwlink/p/?LinkID=620421)
c:\users\username\documents\visual studio 2015\projects\corecheckexample\corecheckexample\corecheckexample.cpp(7): warning C26485: Expression 'arr': No array to pointer decay. (bounds.3: http://go.microsoft.com/fwlink/p/?LinkID=620415)
========== Build: 1 succeeded, 0 failed, 0 up-to-date, 0 skipped ==========
```

Temel C++ yönergeler, daha iyi ve daha güvenli bir kod yazmanıza yardımcı olur. Ancak, bir kuralın veya profilin uygulanmaması gereken bir örneğiniz varsa, doğrudan kodda görüntülenmesini kolaydır. Aşağıdaki kod bloğunda bir kuralın ihlalini algılamasını C++ ve raporlanmasını önlemek için `gsl::suppress` özniteliğini kullanabilirsiniz. Belirli kuralları bastırmak için tek tek deyimleri işaretleyebilirsiniz. Belirli bir kural numarası dahil etmeden `[[gsl::suppress(bounds)]]` yazarak tüm sınır profillerinin de görüntülenmesini sağlayabilirsiniz.

## <a name="supported-rule-sets"></a>Desteklenen kural kümeleri

C++ Temel yönergeler denetleyicisi 'ne yeni kurallar eklendikçe, önceden var olan kod için üretilen uyarı sayısı artabilir. Etkinleştirilecek kural türlerini filtrelemek için, önceden tanımlanmış kural kümelerini kullanabilirsiniz. Visual Studio 2017 sürüm 15,3 itibariyle desteklenen kural kümeleri şunlardır:

- **Sahip Işaretçisi kuralları** [, C++ çekirdek yönergelerinden sahip\<t > ile ilgili kaynak yönetimi denetimlerini](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#r-resource-management)uygular.

- **Const kuralları** [, C++ çekirdek yönergelerinden const ile ilgili denetimleri](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#con-constants-and-immutability)uygular.

- **Ham Işaretçi kuralları** [, C++ çekirdek yönergelerinden gelen ham işaretçilerle ilgili kaynak yönetimi denetimlerini](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#r-resource-management)uygular.

- **Benzersiz Işaretçi kuralları** [, C++ temel yönergelerinden benzersiz işaretçi semantiğine sahip türlerle ilgili kaynak yönetimi denetimlerini](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#r-resource-management)uygular.

- **Sınır kuralları** [ C++ temel yönergelerin sınır profilini](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#probounds-bounds-safety-profile)uygular.

- **Tür kuralları** [ C++ temel yönergelerin tür profilini](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#prosafety-type-safety-profile)zorlar.

Uyarıları yalnızca bir veya birkaç gruptan sınırlandırmayı seçebilirsiniz. **Yerel en düşük** ve **Yerel önerilen** kural kümeleri, C++ diğer ön kontrol denetimlerine ek olarak çekirdek denetim kuralları içerir. Kullanılabilir kural kümelerini görmek için, proje özellikleri iletişim kutusunu açın, **kod Analysis\genel**' i seçin, **kural kümeleri** açılan kutusunda açılan menüyü açın ve **birden çok kural kümesi seçin**. Visual Studio 'da kural kümeleri kullanma hakkında daha fazla bilgi için, bkz. kural kümelerini kullanarak [çalıştırılacak C++ kuralları](using-rule-sets-to-specify-the-cpp-rules-to-run.md) ve [kod analizi kurallarını gruplandırmak için kural kümeleri kullanmayı](/visualstudio/code-quality/using-rule-sets-to-group-code-analysis-rules)seçin.

## <a name="macros"></a>Makrolar

Temel C++ yönergeler denetçisi, koddaki uyarı kategorilerinin tamamını bastırmayı kolaylaştıran makroları tanımlayan bir üstbilgi dosyası ile birlikte gelir:

```cpp
ALL_CPPCORECHECK_WARNINGS
CPPCORECHECK_TYPE_WARNINGS
CPPCORECHECK_RAW_POINTER_WARNINGS
CPPCORECHECK_CONST_WARNINGS
CPPCORECHECK_OWNER_POINTER_WARNINGS
CPPCORECHECK_UNIQUE_POINTER_WARNINGS
CPPCORECHECK_BOUNDS_WARNINGS
```

Bu makrolar, kural kümelerine karşılık gelir ve uyarı numaralarının boşlukla ayrılmış listelerine genişletilir. Uygun pragma yapılarını kullanarak, bir proje veya kod bölümü için ilginç olan geçerli kurallar kümesini yapılandırabilirsiniz. Aşağıdaki örnekte, kod analizi yalnızca eksik sabit değiştiriciler hakkında uyarı alacak:

```cpp
#include <CppCoreCheck\Warnings.h>
#pragma warning(disable: ALL_CPPCORECHECK_WARNINGS)
#pragma warning(default: CPPCORECHECK_CONST_WARNINGS)
```

## <a name="attributes"></a>Öznitelikler

Microsoft C++ DERLEYICISININ GSL gösterme özniteliği için sınırlı bir desteği vardır. Bu, bir işlev içindeki ifade ve blok deyimlerindeki uyarıları gizlemek için kullanılabilir.

```cpp
// Suppress only warnings from the 'r.11' rule in expression.
[[gsl::suppress(r.11)]] new int;

// Suppress all warnings from the 'r' rule group (resource management) in block.
[[gsl::suppress(r)]]
{
    new int;
}

// Suppress only one specific warning number.
// For declarations, you may need to use the surrounding block.
// Macros are not expanded inside of attributes.
// Use plain numbers instead of macros from the warnings.h.
[[gsl::suppress(26400)]]
{
    int *p = new int;
}
```

## <a name="suppressing-analysis-by-using-command-line-options"></a>Komut satırı seçeneklerini kullanarak çözümlemeyi gizleme

#Pragmas yerine, bir proje veya tek bir dosya için uyarıları bastırmak üzere dosyanın özellik sayfasında komut satırı seçeneklerini kullanabilirsiniz. Örneğin, bir dosya için uyarı C26400 devre dışı bırakmak için:

1. **Çözüm Gezgini** dosyaya sağ tıklayın

1. **Özellikleri Seç | C/C++| Komut satırı**

1. **Ek seçenekler** penceresinde `/wd26400`ekleyin.

`/analyze-`belirterek, bir dosyanın tüm kod analizini geçici olarak devre dışı bırakmak için komut satırı seçeneğini kullanabilirsiniz. Bu, daha sonra kod analizini yeniden etkinleştirmenizi hatırlatan ' */analiz ze-' ile '/Analyze ' öğesini geçersiz kılan*bir uyarı oluşturur D9025.

## <a name="enabling-the-c-core-guidelines-checker-on-specific-project-files"></a><a name="corecheck_per_file"></a>Belirli proje C++ dosyalarında temel yönergeler denetleyicisi 'ni etkinleştirme

Bazen odaklanmış kod analizi yapmak ve yine de Visual Studio IDE 'den yararlanmak yararlı olabilir. Aşağıda, derleme süresini kaydetmek ve sonuçların filtrelemesine kolaylaştırmak için büyük projeler için kullanılabilen örnek bir senaryo verilmiştir.

1. Komut kabuğu 'nda `esp.extension` ve `esp.annotationbuildlevel` ortam değişkenlerini ayarlayın.
1. Bu değişkenleri devralması için komut kabuğundan Visual Studio 'Yu açın.
1. Projenizi yükleyin ve özelliklerini açın.
1. Kod analizini etkinleştirin, uygun kural kümelerini seçin, ancak kod analizi uzantılarını etkinleştirmeyin.
1. C++ Temel kılavuz denetleyicisi ile çözümlemek istediğiniz dosyaya gidin ve özelliklerini açın.
1. **C/C++\ komut satırı seçeneklerini** belirleyin ve `/analyze:plugin EspXEngine.dll` ekleyin
1. Önceden derlenmiş üstbilginin kullanımını devre dışı bırakın (**CC++/\ önceden derlenmiş üstbilgiler**). Bu gereklidir çünkü uzantılar altyapısı, ön derlenmiş üstbilginin iç bilgilerini okumaya çalışabilir ve ikincisi varsayılan proje seçenekleriyle derlenmişse uyumlu olmayacaktır.
1. Projeyi yeniden derleyin. Ortak önceden denetim denetimleri tüm dosyalarda çalıştırılmalıdır. C++ Temel kılavuz denetleyicisi varsayılan olarak etkinleştirilmediğinden, yalnızca onu kullanmak üzere yapılandırılmış dosya üzerinde çalışmalıdır.

## <a name="how-to-use-the-c-core-guidelines-checker-outside-of-visual-studio"></a>Visual Studio dışında C++ temel yönergeler denetleyicisi 'ni kullanma

Otomatik derlemelerde C++ temel kılavuz denetimleri ' ni kullanabilirsiniz.

### <a name="msbuild"></a>MSBuild

Yerel kod analizi denetleyicisi (PREfast), MSBuild ortamıyla özel hedef dosyaları tarafından tümleşiktir. Projeyi etkinleştirmek için proje özelliklerini kullanabilir ve C++ temel kılavuz denetleyicisini ekleyebilirsiniz (genel kullanıma dayalıdır):

```xml
<PropertyGroup>
  <EnableCppCoreCheck>true</EnableCppCoreCheck>
  <CodeAnalysisRuleSet>CppCoreCheckRules.ruleset</CodeAnalysisRuleSet>
  <RunCodeAnalysis>true</RunCodeAnalysis>
</PropertyGroup>
```

Microsoft. cpp. targets dosyasını içeri aktarmadan önce bu özellikleri eklediğinizden emin olun. Belirli kural kümelerini seçebilir veya özel bir kural kümesi oluşturabilir veya diğer ön denetimleri içeren varsayılan kural kümesini kullanabilirsiniz.

C++ Çekirdek denetleyiciyi yalnızca, [daha önce açıklanan](#corecheck_per_file)yaklaşımı kullanarak ve MSBuild dosyalarını kullanarak yalnızca belirtilen dosyalarda çalıştırabilirsiniz. Ortam değişkenleri `BuildMacro` öğesi kullanılarak ayarlanabilir:

```xml
<ItemGroup>
    <BuildMacro Include="Esp_AnnotationBuildLevel">
      <EnvironmentVariable>true</EnvironmentVariable>
      <Value>Ignore</Value>
    </BuildMacro>
    <BuildMacro Include="Esp_Extensions">
      <EnvironmentVariable>true</EnvironmentVariable>
      <ValueCppCoreCheck.dll</Value>
    </BuildMacro>
</ItemGroup>
```

Proje dosyasını değiştirmek istemiyorsanız, özellikleri komut satırına geçirebilirsiniz:

```cmd
msbuild /p:EnableCppCoreCheck=true /p:RunCodeAnalysis=true /p:CodeAnalysisRuleSet=CppCoreCheckRules.ruleset ...
```

### <a name="non-msbuild-projects"></a>MSBuild olmayan projeler

MSBuild 'e bağlı olmayan bir yapı sistemi kullanıyorsanız, denetleyiciyi yine de çalıştırabilirsiniz, ancak kod çözümleme altyapısı yapılandırmasının bazı iç işlevleri hakkında bilgi sahibi olmanız gerekir (gelecekte desteklenmeye garanti edilmez).

Birkaç ortam değişkeni ayarlamanız ve derleyici için uygun komut satırı seçeneklerini kullanmanız gerekir. Derleyici, dizin ekleme vb. için belirli yolları aramanız gerekmiyorsa, "yerel araçlar komut Istemi" ortamı altında çalışmak daha iyidir.

1. **Ortam değişkenleri**
   - `set esp.extensions=cppcorecheck.dll` bu, altyapıya C++ temel kılavuz modülünü yüklemesini söyler.
   - `set esp.annotationbuildlevel=ignore` bu, SAL ek açıklamalarını işleyen mantığı devre dışı bırakır. Ek açıklamalar, C++ temel yönergeler denetleyicisi 'nde Kod analizini etkilemez, ancak işlemleri zaman alır (bazen çok zaman). Bu ayar isteğe bağlıdır, ancak önemle önerilir.
   - `set caexcludepath=%include%`, standart üstbilgiler üzerinde harekete çıkabilecek uyarıları devre dışı bırakmanızı kesinlikle öneririz. Buraya daha fazla yol ekleyebilirsiniz. Örneğin, projenizdeki ortak üst bilgilerin yolu.
1. **Komut satırı seçenekleri**
   - `/analyze` Kod analizini mümkün (yalnızca/Analyze: Only ve/Analyze: quiet) kullanmayı düşünün.
   - `/analyze:plugin EspXEngine.dll` Bu seçenek, kod analizi uzantıları altyapısını önceden hızlı yükler. Bu altyapı, sırasıyla C++ temel kılavuz denetleyicisini yükler.

## <a name="use-the-guideline-support-library"></a>Kılavuz desteği kitaplığını kullanma

Kılavuz Desteği kitaplığı, temel yönergeleri takip etmenize yardımcı olmak için tasarlanmıştır. GSL, hataya açık olan yapıları daha güvenli alternatifler ile değiştirmenize olanak tanıyan tanımlar içerir. Örneğin, parametrelerin `T*, length` çiftini `span<T>` türüyle değiştirebilirsiniz. GSL [https://www.nuget.org/packages/Microsoft.Gsl](https://www.nuget.org/packages/Microsoft.Gsl)adresinden kullanılabilir. Kitaplık açık kaynaktır, bu sayede kaynakları görüntüleyebilir, yorum yapabilir veya katkıda bulunabilirsiniz. Proje [https://github.com/Microsoft/GSL](https://github.com/Microsoft/GSL)bulunabilir.

## <a name="use-the-c-core-check-guidelines-in-visual-studio-2015-projects"></a><a name="vs2015_corecheck"></a>Visual Studio C++ 2015 projelerinde çekirdek denetim yönergelerini kullanma

Visual Studio 2015 kullanıyorsanız, C++ çekirdek denetimi kod analizi kural kümeleri varsayılan olarak yüklenmez. Visual Studio 2015 ' de çekirdek denetimi kod analizi araçlarını etkinleştirebilmeniz C++ için bazı ek adımlar gerçekleştirmeniz gerekir. Microsoft, bir NuGet paketi kullanarak Visual Studio 2015 projeleri için destek sağlar. Paketin adı Microsoft. CppCoreCheck olarak adlandırılmıştır ve [http://www.nuget.org/packages/Microsoft.CppCoreCheck](https://www.nuget.org/packages/Microsoft.CppCoreCheck)adresinden kullanılabilir. Bu paket, güncelleştirme 1 ile en az Visual Studio 2015 yüklü olmasını gerektirir.

Paket, yalnızca üst bilgi kılavuz destek kitaplığı (GSL) olan bir bağımlılık olarak başka bir paket de yüklüyor. GSL, [https://github.com/Microsoft/GSL](https://github.com/Microsoft/GSL)'de GitHub 'da da kullanılabilir.

Kod Analizi kurallarının yüklenme biçimi nedeniyle, Visual Studio 2015 içinde denetlemek istediğiniz her C++ bir projeye Microsoft. CppCoreCheck NuGet paketini yüklemelisiniz.

### <a name="to-add-the-microsoftcppcorecheck-package-to-your-project-in-visual-studio-2015"></a>Visual Studio 2015 ' de projenize Microsoft. CppCoreCheck paketini eklemek için

1. **Çözüm Gezgini**' de, paketi eklemek istediğiniz çözümde projenizin bağlam menüsünü açmak için sağ tıklayın. NuGet **paket yöneticisini**açmak Için **NuGet Paketlerini Yönet** ' i seçin.

1. **NuGet Paket Yöneticisi** penceresinde Microsoft. CppCoreCheck öğesini arayın.

    ![NuGet Paket Yöneticisi penceresi CppCoreCheck paketini gösterir](../code-quality/media/cppcorecheck_nuget_window.png)

1. Microsoft. CppCoreCheck paketini seçin ve ardından, kuralları projenize eklemek için **yükler** düğmesini seçin.

   NuGet paketi projenize kod analizini etkinleştirdiğinizde çağrılan, projenize ek bir MSBuild. targets dosyası ekler. Bu. targets dosyası, Visual C++ Studio kod analizi aracına ek bir uzantı olarak çekirdek denetim kuralları ekler. Paket yüklendiğinde, yayınlanan ve deneysel kuralları etkinleştirmek veya devre dışı bırakmak için özellik sayfaları iletişim kutusunu kullanabilirsiniz.
