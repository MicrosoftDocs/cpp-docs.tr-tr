---
title: C++ Temel Yönergeleri denetleyicilerini kullanma
ms.date: 08/14/2018
ms.topic: conceptual
dev_langs:
- CPP
ms.openlocfilehash: 9c36c17e819e954d66833f059fe794ac14898e75
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227731"
---
# <a name="use-the-c-core-guidelines-checkers"></a>C++ Temel Yönergeleri denetleyicilerini kullanma

C++ Temel Yönergeleri, C++ uzmanları ve tasarımcıları tarafından oluşturulan C++ ' da kodlama hakkında taşınabilir bir yönergeler, kurallar ve en iyi uygulamalar kümesidir. Visual Studio şu anda, C++ için kod çözümleme araçlarının bir parçası olarak bu kuralların bir alt kümesini desteklemektedir. Temel kılavuz dama, Visual Studio 2017 ve Visual Studio 2019 ' de varsayılan olarak yüklenir ve [Visual studio 2015 için bir NuGet paketi olarak kullanılabilir](#vs2015_corecheck).

## <a name="the-c-core-guidelines-project"></a>C++ Temel Yönergeleri projesi

Bjarne Stroustrup ve diğerleri tarafından oluşturulan C++ Temel Yönergeleri, modern C++ ' ı güvenli ve etkili bir şekilde kullanmaya yönelik bir kılavuzdur. Yönergeler statik tür güvenliğini ve kaynak güvenliğini vurgular. Bu, dilin hata olasılığı olan kısımlarını ortadan kaldırmaya veya en aza indirmenin yollarını belirler ve kodunuzun daha basit ve daha iyi performans sağlamak için güvenilir bir yol sunar. Bu yönergeler standart C++ temeli tarafından korunur. Daha fazla bilgi edinmek için bkz. belge, [C++ temel yönergeleri](https://isocpp.github.io/CppCoreGuidelines/CppCoreGuidelines)ve C++ temel yönergeleri belge proje dosyalarına [GitHub](https://github.com/isocpp/CppCoreGuidelines)'da erişin.

## <a name="enable-the-c-core-check-guidelines-in-code-analysis"></a>Kod çözümlemede C++ Temel Denetimi yönergeleri etkinleştirme

Projeniz için **Özellik sayfaları** Iletişim kutusunun **Kod Analizi** bölümünde **derleme üzerinde Kod analizini etkinleştir** onay kutusunu seçerek projenizde kod analizini etkinleştirebilirsiniz.

![Kod Analizi genel ayarları için özellik sayfası](media/cppcorecheck_codeanalysis_general.png)

C++ Temel Denetimi kuralların bir alt kümesi, kod analizi etkinleştirildiğinde varsayılan olarak çalışan Microsoft yerel önerilen kural kümesine dahildir. Ek çekirdek denetimi kurallarını etkinleştirmek için, aşağı açılan listeye tıklayın ve hangi kural kümelerini dahil etmek istediğinizi seçin:

![Ek C++ Temel Denetimi kural kümeleri için açılan menü](media/cppcorecheck_codeanalysis_extensions.png)

## <a name="examples"></a>Örnekler

C++ Temel Denetimi kuralların bulabileceği bazı sorunlar hakkında bir örnek aşağıda verilmiştir:

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

Bu örnek C++ Temel Denetimi kuralların bulabileceği uyarıların birkaçını gösterir:

- C26494, kural türü. 5: her zaman bir nesne başlatın.

- C26485, kural sınırlardır. 3: bir dizi işaretçiden işaretçiye sınır yok.

- C26481 kural sınırları. 1: işaretçi aritmetiği kullanmayın. Bunun yerine `span` kullanın.

Bu kodu derlerken C++ Temel Denetimi Code Analysis kural kümeleri yüklenip etkinleştirilirse, ilk iki uyarı çıkışlardır, ancak üçüncüsü bastırılır. Örnek koddan derleme çıktısı aşağıda verilmiştir:

```Output
1>------ Build started: Project: CoreCheckExample, Configuration: Debug Win32 ------
1>  CoreCheckExample.cpp
1>  CoreCheckExample.vcxproj -> C:\Users\username\documents\visual studio 2015\Projects\CoreCheckExample\Debug\CoreCheckExample.exe
1>  CoreCheckExample.vcxproj -> C:\Users\username\documents\visual studio 2015\Projects\CoreCheckExample\Debug\CoreCheckExample.pdb (Full PDB)
c:\users\username\documents\visual studio 2015\projects\corecheckexample\corecheckexample\corecheckexample.cpp(6): warning C26494: Variable 'arr' is uninitialized. Always initialize an object. (type.5: http://go.microsoft.com/fwlink/p/?LinkID=620421)
c:\users\username\documents\visual studio 2015\projects\corecheckexample\corecheckexample\corecheckexample.cpp(7): warning C26485: Expression 'arr': No array to pointer decay. (bounds.3: http://go.microsoft.com/fwlink/p/?LinkID=620415)
========== Build: 1 succeeded, 0 failed, 0 up-to-date, 0 skipped ==========
```

C++ Temel Yönergeleri daha iyi ve daha güvenli bir kod yazmanıza yardımcı olur. Ancak, bir kuralın veya profilin uygulanmaması gereken bir örneğiniz varsa, doğrudan kodda görüntülenmesini kolaydır. `gsl::suppress`Aşağıdaki kod bloğunda bir kuralın ihlal edildiğini ve raporlanmasını C++ temel denetimi önlemek için özniteliğini kullanabilirsiniz. Belirli kuralları bastırmak için tek tek deyimleri işaretleyebilirsiniz. `[[gsl::suppress(bounds)]]`Belirli bir kural numarası dahil etmeden yazarak tüm sınır profilini de gizleyebilirsiniz.

## <a name="supported-rule-sets"></a>Desteklenen kural kümeleri

C++ Temel Yönergeleri denetleyicisi 'ne yeni kurallar eklendikçe, önceden var olan kod için üretilen uyarı sayısı artmayabilir. Etkinleştirilecek kural türlerini filtrelemek için, önceden tanımlanmış kural kümelerini kullanabilirsiniz.
Kuralların çoğu için başvuru konuları [Visual Studio C++ temel denetimi Reference](code-analysis-for-cpp-corecheck.md)altındadır.

Visual Studio 2017 sürüm 15,3 itibariyle desteklenen kural kümeleri şunlardır:

- **Sahip Işaretçisi kuralları** [ \<T> C++ temel yönergeleri sahip ile ilgili kaynak yönetimi denetimlerini](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#r-resource-management)uygular.

- **Const kuralları** [C++ temel yönergeleri const ile ilgili denetimleri](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#con-constants-and-immutability)uygular.

- **Ham Işaretçi kuralları** [C++ temel yönergeleri ham işaretçilerle ilgili kaynak yönetimi denetimlerini](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#r-resource-management)uygular.

- **Benzersiz Işaretçi kuralları** [C++ temel yönergeleri benzersiz işaretçi semantiğine sahip türlerle ilgili kaynak yönetimi denetimlerini](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#r-resource-management)uygular.

- **Sınır kuralları** [C++ temel yönergeleri sınır profilini](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#probounds-bounds-safety-profile)zorlar.

- **Tür kuralları** [C++ temel yönergeleri tür profilini](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#prosafety-type-safety-profile)zorlar.

**Visual Studio 2017 sürüm 15,5**:

- **Sınıf kuralları** Özel üye işlevlerinin ve sanal belirtimlerinin uygun kullanımına odaklanarak birkaç kural. Bu, [sınıflar ve sınıf hiyerarşileri](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#S-class)için önerilen denetimlerin bir alt kümesidir.
- **Eşzamanlılık kuralları** Kötü olarak tanımlanmış koruyucu nesnelerini yakalayan tek bir kural. Daha fazla bilgi için bkz. [eşzamanlılık ile ilgili yönergeler](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#S-concurrency).
- **Bildirim kuralları** [Arabirimler yönergelerinden](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#S-interfaces) gelen ve genel değişkenlerin nasıl bildirildiği üzerinde odaklanılmış olan birkaç kural.
- **Işlev kuralları** Belirleyici benimseme konusunda yardımcı olan iki denetim **`noexcept`** . Bu, [clear işlevi tasarımı ve uygulamasıyla](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#S-functions)ilgili yönergelerin bir parçasıdır.
- **Paylaşılan Işaretçi kuralları** [Kaynak yönetimi](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#S-resource) yönergeleri zorlaması kapsamında, paylaşılan işaretçilerin işlevlere nasıl geçirildiğine veya yerel olarak nasıl kullanıldığına özgü birkaç kural ekledik.
- **Stil kuralları** [Goto](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Res-goto)'in kullanıldığı basit ancak önemli bir denetim. Bu, C++ ' da kodlama stili ve ifadelerin ve deyimlerin geliştirmesinde ilk adımdır.

**Visual Studio 2017 sürüm 15,6**:

- **Aritmetik kurallar** Aritmetik [taşma](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Res-overflow), [imzalanmış imzasız işlemleri](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Res-unsigned) ve [bit işlemesini](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Res-nonnegative)algılamaya yönelik kurallar.

Uyarıları yalnızca bir veya birkaç gruptan sınırlandırmayı seçebilirsiniz. **Yerel en düşük** ve **Yerel önerilen** kural kümeleri, diğer ön hızlı denetimlerin yanı sıra C++ temel denetimi kuralları içerir. Kullanılabilir kural kümelerini görmek için, proje özellikleri iletişim kutusunu açın, **kod Analysis\genel**' i seçin, **kural kümeleri** açılan kutusunda açılan menüyü açın ve **birden çok kural kümesi seçin**. Visual Studio 'da kural kümeleri kullanma hakkında daha fazla bilgi için bkz. [çalıştırılacak C++ kurallarını belirtmek için kural kümelerini kullanma](using-rule-sets-to-specify-the-cpp-rules-to-run.md).

## <a name="macros"></a>Makrolar

C++ Temel Yönergeleri denetleyicisi, koddaki uyarı kategorilerinin tamamını bastırmayı kolaylaştıran makroları tanımlayan bir üst bilgi dosyası ile birlikte gelir:

```cpp
ALL_CPPCORECHECK_WARNINGS
CPPCORECHECK_TYPE_WARNINGS
CPPCORECHECK_RAW_POINTER_WARNINGS
CPPCORECHECK_CONST_WARNINGS
CPPCORECHECK_OWNER_POINTER_WARNINGS
CPPCORECHECK_UNIQUE_POINTER_WARNINGS
CPPCORECHECK_BOUNDS_WARNINGS
```

Bu makrolar, kural kümelerine karşılık gelir ve uyarı numaralarının boşlukla ayrılmış bir listesine genişletilir. Uygun pragma yapılarını kullanarak, bir proje veya kod bölümü için ilginç olan geçerli kurallar kümesini yapılandırabilirsiniz. Aşağıdaki örnekte, kod analizi yalnızca eksik sabit değiştiriciler hakkında sizi uyarır:

```cpp
#include <CppCoreCheck\Warnings.h>
#pragma warning(disable: ALL_CPPCORECHECK_WARNINGS)
#pragma warning(default: CPPCORECHECK_CONST_WARNINGS)
```

## <a name="attributes"></a>Öznitelikler

Microsoft C++ derleyicisinin GSL gösterme özniteliği için sınırlı bir desteği vardır. Bu, bir işlev içindeki ifade ve blok deyimlerindeki uyarıları gizlemek için kullanılabilir.

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

## <a name="suppress-analysis-by-using-command-line-options"></a>Komut satırı seçeneklerini kullanarak çözümlemeyi gösterme

#Pragmas yerine, bir proje veya tek bir dosya için uyarıları bastırmak üzere dosyanın özellik sayfasında komut satırı seçeneklerini kullanabilirsiniz. Örneğin, bir dosya için uyarı C26400 devre dışı bırakmak için:

1. **Çözüm Gezgini** dosyaya sağ tıklayın

1. **Özellikleri Seç | C/C++ | Komut satırı**

1. **Ek seçenekler** penceresinde, ekleyin `/wd26400` .

Komut satırı seçeneğini belirterek, bir dosyanın tüm kod analizini geçici olarak devre dışı bırakabilirsiniz `/analyze-` . Bu, Kod analizini daha sonra yeniden etkinleştirmenizi hatırlatır ve ' */analiz ze-' ile '/Analyze ' değerini geçersiz kılan*bir uyarı oluşturur.

## <a name="enable-the-c-core-guidelines-checker-on-specific-project-files"></a><a name="corecheck_per_file"></a>Belirli proje dosyalarında C++ Temel Yönergeleri denetleyiciyi etkinleştirin

Bazen odaklanmış kod analizi yapmak ve Visual Studio IDE 'yi kullanmaya devam etmek faydalı olabilir. Aşağıdaki örnek senaryo, derleme süresini kaydetmek ve sonuçların filtrelanmasını kolaylaştırmak için büyük projeler için kullanılabilir:

1. Komut kabuğu 'nda `esp.extension` ve `esp.annotationbuildlevel` ortam değişkenlerini ayarlayın.
1. Bu değişkenleri devralması için komut kabuğundan Visual Studio 'Yu açın.
1. Projenizi yükleyin ve özelliklerini açın.
1. Kod analizini etkinleştirin, uygun kural kümelerini seçin, ancak kod analizi uzantılarını etkinleştirmeyin.
1. C++ Temel Yönergeleri denetleyicisi ile çözümlemek istediğiniz dosyaya gidin ve özelliklerini açın.
1. **C/C++ \ komut satırı seçeneklerini** belirleyin ve Ekle`/analyze:plugin EspXEngine.dll`
1. Önceden derlenmiş üstbilginin kullanımını devre dışı bırakın (**C/C++ \ önceden derlenmiş üstbilgiler**). Uzantı altyapısı, ön derlenmiş üst bilgiden (PCH) iç bilgilerini okumaya çalışabileceğinden bu gereklidir; PCH varsayılan proje seçenekleriyle derlenirse, uyumlu olmaz.
1. Projeyi yeniden derleyin. Ortak önceden denetim denetimleri tüm dosyalarda çalıştırılmalıdır. C++ Temel Yönergeleri denetleyicisi varsayılan olarak etkinleştirilmediğinden, yalnızca onu kullanmak üzere yapılandırılmış dosya üzerinde çalışmalıdır.

## <a name="how-to-use-the-c-core-guidelines-checker-outside-of-visual-studio"></a>C++ Temel Yönergeleri denetleyiciyi Visual Studio dışında kullanma

Otomatikleştirilmiş derlemelerde C++ Temel Yönergeleri denetimleri kullanabilirsiniz.

### <a name="msbuild"></a>MSBuild

Yerel kod analizi denetleyicisi (PREfast), MSBuild ortamıyla özel hedef dosyaları tarafından tümleşiktir. Projeyi etkinleştirmek için proje özelliklerini kullanabilir ve C++ Temel Yönergeleri denetleyiciyi ekleyebilirsiniz (önceden hızlı temel alan):

```xml
  <PropertyGroup>
    <EnableCppCoreCheck>true</EnableCppCoreCheck>
    <CodeAnalysisRuleSet>CppCoreCheckRules.ruleset</CodeAnalysisRuleSet>
    <RunCodeAnalysis>true</RunCodeAnalysis>
  </PropertyGroup>
```

Microsoft. cpp. targets dosyasını içeri aktarmadan önce bu özellikleri eklediğinizden emin olun. Belirli kural kümelerini seçebilir veya özel bir kural kümesi oluşturabilir veya diğer ön denetimleri içeren varsayılan kural kümesini kullanabilirsiniz.

C++ Core Checker 'ı yalnızca, [daha önce açıklanan](#corecheck_per_file)yaklaşımı kullanarak ve MSBuild dosyalarını kullanarak yalnızca belirtilen dosyalarda çalıştırabilirsiniz. Ortam değişkenleri şu öğe kullanılarak ayarlanabilir `BuildMacro` :

```xml
<ItemGroup>
    <BuildMacro Include="Esp_AnnotationBuildLevel">
      <EnvironmentVariable>true</EnvironmentVariable>
      <Value>Ignore</Value>
    </BuildMacro>
    <BuildMacro Include="Esp_Extensions">
      <EnvironmentVariable>true</EnvironmentVariable>
      <Value>CppCoreCheck.dll</Value>
    </BuildMacro>
</ItemGroup>
```

Proje dosyasını değiştirmek istemiyorsanız, özellikleri komut satırına geçirebilirsiniz:

```cmd
msbuild /p:EnableCppCoreCheck=true /p:RunCodeAnalysis=true /p:CodeAnalysisRuleSet=CppCoreCheckRules.ruleset ...
```

### <a name="non-msbuild-projects"></a>MSBuild olmayan projeler

MSBuild 'e bağlı olmayan bir yapı sistemi kullanıyorsanız, denetleyiciyi yine de çalıştırabilirsiniz, ancak kod çözümleme altyapısı yapılandırmasının bazı iç kodlarını tanımanız gerekir. Gelecekte bu iç yapıları desteklenecek garanti edilmez.

Birkaç ortam değişkeni ayarlamanız ve derleyici için uygun komut satırı seçeneklerini kullanmanız gerekir. Derleyici, dizin ekleme vb. için belirli yolları aramanız gerekmiyorsa, "yerel araçlar komut Istemi" ortamı altında çalışmak daha iyidir.

- **Ortam değişkenleri**
  - `set esp.extensions=cppcorecheck.dll`Bu, altyapıya C++ Temel Yönergeleri modülünü yüklemesini söyler.
  - `set esp.annotationbuildlevel=ignore`Bu, SAL ek açıklamalarını işleyen mantığı devre dışı bırakır. Ek açıklamalar C++ Temel Yönergeleri denetleyicisi 'nde Kod analizini etkilemez, ancak işlemleri zaman alır (bazen uzun zaman). Bu ayar isteğe bağlıdır, ancak önemle önerilir.
  - `set caexcludepath=%include%`Standart üstbilgiler üzerinde harekete çıkabilecek uyarıları devre dışı bırakmanızı kesinlikle öneririz. Buraya daha fazla yol ekleyebilirsiniz. Örneğin, projenizdeki ortak üst bilgilerin yolu.

- **Komut satırı seçenekleri**
  - `/analyze`Kod analizini etkinleştirilir (yalnızca/Analyze: Only ve/Analyze: quiet) kullanmayı düşünün.
  - `/analyze:plugin EspXEngine.dll`Bu seçenek, kod analizi uzantıları altyapısını önceden hızlı yükler. Bu altyapı, sırasıyla C++ Temel Yönergeleri denetleyiciyi yükler.

## <a name="use-the-guideline-support-library"></a>Kılavuz desteği kitaplığını kullanma

Kılavuz Desteği kitaplığı, temel yönergeleri takip etmenize yardımcı olmak için tasarlanmıştır. GSL, hataya açık olan yapıları daha güvenli alternatifler ile değiştirmenize olanak tanıyan tanımlar içerir. Örneğin, bir `T*, length` parametre çiftini `span<T>` türüyle değiştirebilirsiniz. GSL, adresinde bulunabilir [http://www.nuget.org/packages/Microsoft.Gsl](https://www.nuget.org/packages/Microsoft.Gsl) . Kitaplık açık kaynağıdır, bu sayede kaynakları görüntüleyebilir, yorum yapabilir veya katkıda bulunabilirsiniz. Proje adresinde bulunabilir [https://github.com/Microsoft/GSL](https://github.com/Microsoft/GSL) .

## <a name="use-the-c-core-check-guidelines-in-visual-studio-2015-projects"></a><a name="vs2015_corecheck"></a>Visual Studio 2015 projelerinde C++ Temel Denetimi yönergeleri kullanma

Visual Studio 2015 kullanıyorsanız, C++ Temel Denetimi Code Analysis kural kümeleri varsayılan olarak yüklenmez. Visual Studio 2015 ' de C++ Temel Denetimi Code Analysis araçlarını etkinleştirebilmeniz için bazı ek adımlar gerçekleştirmeniz gerekir. Microsoft, bir NuGet paketi kullanarak Visual Studio 2015 projeleri için destek sağlar. Paket Microsoft. CppCoreCheck olarak adlandırılmıştır ve ' de mevcuttur [http://www.nuget.org/packages/Microsoft.CppCoreCheck](https://www.nuget.org/packages/Microsoft.CppCoreCheck) . Bu paket, güncelleştirme 1 ile en az Visual Studio 2015 yüklü olmasını gerektirir.

Paket, yalnızca üst bilgi kılavuz destek kitaplığı (GSL) olan bir bağımlılık olarak başka bir paket de yüklüyor. GSL, konumundaki GitHub 'da da kullanılabilir [https://github.com/Microsoft/GSL](https://github.com/Microsoft/GSL) .

Kod Analizi kurallarının yüklenme biçimi nedeniyle, Visual Studio 2015 içinde denetlemek istediğiniz her C++ projesine Microsoft. CppCoreCheck NuGet paketini yüklemelisiniz.

### <a name="to-add-the-microsoftcppcorecheck-package-to-your-project-in-visual-studio-2015"></a>Visual Studio 2015 ' de projenize Microsoft. CppCoreCheck paketini eklemek için

1. **Çözüm Gezgini**' de, paketi eklemek istediğiniz çözümde projenizin bağlam menüsünü açmak için sağ tıklayın. NuGet **paket yöneticisini**açmak Için **NuGet Paketlerini Yönet** ' i seçin.

1. **NuGet Paket Yöneticisi** penceresinde Microsoft. CppCoreCheck öğesini arayın.

    ![NuGet Paket Yöneticisi penceresi CppCoreCheck paketini gösterir](../code-quality/media/cppcorecheck_nuget_window.png)

1. Microsoft. CppCoreCheck paketini seçin ve ardından, kuralları projenize eklemek için **yükler** düğmesini seçin.

   NuGet paketi projenize kod analizini etkinleştirdiğinizde çağrılan, projenize ek bir MSBuild *. targets* dosyası ekler. Bu *. targets* dosyası, C++ temel denetimi kurallarını Visual Studio Code Analysis aracına ek bir uzantı olarak ekler. Paket yüklendiğinde, yayınlanan ve deneysel kuralları etkinleştirmek veya devre dışı bırakmak için özellik sayfaları iletişim kutusunu kullanabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

- [Visual Studio C++ Temel Denetimi başvurusu](code-analysis-for-cpp-corecheck.md)
