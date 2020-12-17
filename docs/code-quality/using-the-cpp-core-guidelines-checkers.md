---
title: C++ Temel Yönergeleri denetleyicilerini kullanma
description: C++ Temel Yönergeleri için Microsoft C++ kod analizi kurallarını ayarlama ve kullanma.
ms.date: 12/16/2020
ms.topic: conceptual
dev_langs:
- CPP
ms.openlocfilehash: 93b69839bc9e5ffd45a08da12e84028eea10aef4
ms.sourcegitcommit: 387ce22a3b0137f99cbb856a772b5a910c9eba99
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/17/2020
ms.locfileid: "97645169"
---
# <a name="use-the-c-core-guidelines-checkers"></a>C++ Temel Yönergeleri denetleyicilerini kullanma

C++ Temel Yönergeleri, C++ uzmanları ve tasarımcıları tarafından oluşturulan C++ ' da kodlama hakkında taşınabilir bir yönergeler, kurallar ve en iyi uygulamalar kümesidir. Visual Studio şu anda, C++ için kod çözümleme araçlarının bir parçası olarak bu kuralların bir alt kümesini desteklemektedir. Temel kılavuz dama, Visual Studio 2017 ve Visual Studio 2019 ' de varsayılan olarak yüklenir. [Visual Studio 2015 için bir NuGet paketi olarak kullanılabilir](#vs2015_corecheck).

## <a name="the-c-core-guidelines-project"></a>C++ Temel Yönergeleri projesi

Bjarne Stroustrup ve diğerleri tarafından oluşturulan C++ Temel Yönergeleri, modern C++ ' ı güvenli ve etkili bir şekilde kullanmaya yönelik bir kılavuzdur. Yönergeler statik tür güvenliğini ve kaynak güvenliğini vurgular. Bu, dilin en fazla hata olasılığı olan kısımlarını ortadan kaldırmaya veya en aza indirmenize yönelik yolları belirler. Ayrıca, kodunuzun daha basit, daha güvenilir ve daha iyi performansa sahip olmasını da öneririz. Bu yönergeler standart C++ temeli tarafından korunur. Daha fazla bilgi edinmek için bkz. belge, [C++ temel yönergeleri](https://isocpp.github.io/CppCoreGuidelines/CppCoreGuidelines)ve C++ temel yönergeleri belge proje dosyalarına [GitHub](https://github.com/isocpp/CppCoreGuidelines)'da erişin.

## <a name="enable-the-c-core-check-guidelines-in-code-analysis"></a>Kod çözümlemede C++ Temel Denetimi yönergeleri etkinleştirme

::: moniker range="<=msvc-150"

C++ Temel Denetimi kuralların bir alt kümesi, Microsoft yerel olarak önerilen kural kümesine dahildir. Bu, kod analizi etkinleştirildiğinde varsayılan olarak çalışan RuleSet ' dir.

### <a name="to-enable-code-analysis-on-your-project"></a>Projenizde kod analizini etkinleştirmek için

1. Projeniz için  **Özellik sayfaları** iletişim kutusunu açın.

1. **Yapılandırma özellikleri** > **Kod Analizi** özellik sayfasını seçin.

1. **Derleme üzerinde Kod analizini etkinleştir** onay kutusunu seçin.

![Kod Analizi genel ayarları için özellik sayfası](media/cppcorecheck_codeanalysis_general.png)

Ek çekirdek denetimi kurallarını etkinleştirmek için, açılan listeyi açın ve hangi kural kümelerini dahil etmek istediğinizi seçin:

![Ek C++ Temel Denetimi kural kümeleri için açılan menü](media/cppcorecheck_codeanalysis_extensions.png)

::: moniker-end
::: moniker range=">=msvc-160"

C++ Temel Denetimi kuralların bir alt kümesi, Microsoft yerel olarak önerilen kural kümesine dahildir. Bu, Microsoft Kod Analizi etkinleştirildiğinde varsayılan olarak çalışan RuleSet ' dir.

### <a name="to-enable-code-analysis-on-your-project"></a>Projenizde kod analizini etkinleştirmek için:

1. Projeniz için  **Özellik sayfaları** iletişim kutusunu açın.

1. **Yapılandırma özellikleri** > **Kod Analizi** özellik sayfasını seçin.

1. **Derlemede Kod analizini etkinleştir** ' i ayarlayın ve **Microsoft Kod Analizi özelliklerini etkinleştirin** .

Ayrıca, desteklenen tüm C++ Temel Denetimi kurallarını çalıştırmayı seçebilir veya çalıştırmak için kendi alt kümeinizi seçebilirsiniz:

### <a name="to-enable-additional-core-check-rules"></a>Ek çekirdek denetimi kurallarını etkinleştirmek için

1. Projeniz için  **Özellik sayfaları** iletişim kutusunu açın.

1. **Yapılandırma özellikleri** > **Kod Analizi** > **Microsoft** özellik sayfasını seçin.

1. **Etkin kurallar** açılan listesini açın ve **birden çok kural kümesi Seç**' i seçin.

1. **Kural kümeleri Ekle veya Kaldır** iletişim kutusunda hangi kural kümelerini dahil etmek istediğinizi seçin.

::: moniker-end

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

C++ Temel Denetimi kod analizi kural kümelerini yükleyip etkinleştirin ve sonra bu kodu derleyin. Kod Analizi ilk iki uyarıyı çıkarır ve üçüncüsü bastırır. Visual Studio 2015 'de örnek koddan derleme çıktısı aşağıda verilmiştir:

```Output
1>------ Build started: Project: CoreCheckExample, Configuration: Debug Win32 ------
1>  CoreCheckExample.cpp
1>  CoreCheckExample.vcxproj -> C:\Users\username\documents\visual studio 2015\Projects\CoreCheckExample\Debug\CoreCheckExample.exe
1>  CoreCheckExample.vcxproj -> C:\Users\username\documents\visual studio 2015\Projects\CoreCheckExample\Debug\CoreCheckExample.pdb (Full PDB)
c:\users\username\documents\visual studio 2015\projects\corecheckexample\corecheckexample\corecheckexample.cpp(6): warning C26494: Variable 'arr' is uninitialized. Always initialize an object. (type.5: http://go.microsoft.com/fwlink/p/?LinkID=620421)
c:\users\username\documents\visual studio 2015\projects\corecheckexample\corecheckexample\corecheckexample.cpp(7): warning C26485: Expression 'arr': No array to pointer decay. (bounds.3: http://go.microsoft.com/fwlink/p/?LinkID=620415)
========== Build: 1 succeeded, 0 failed, 0 up-to-date, 0 skipped ==========
```

C++ Temel Yönergeleri daha iyi ve daha güvenli bir kod yazmanıza yardımcı olur. Ancak, bir kuralın veya profilin uygulanmaması gereken bir örnek bulabilirsiniz. Doğrudan kodda bastırmak kolaydır. `[[gsl::suppress]]`Aşağıdaki kod bloğunda bir kuralın ihlal edildiğini ve raporlanmasını C++ temel denetimi önlemek için özniteliğini kullanabilirsiniz. Belirli kuralları bastırmak için tek tek deyimleri işaretleyebilirsiniz. `[[gsl::suppress(bounds)]]`Belirli bir kural numarası dahil etmeden yazarak tüm sınır profilini de gizleyebilirsiniz.

## <a name="supported-rule-sets"></a>Desteklenen kural kümeleri

C++ Temel Yönergeleri denetleyicisi 'ne yeni kurallar eklendikçe, önceden var olan kod için üretilen uyarı sayısı artmayabilir. Etkinleştirilecek kural türlerini filtrelemek için, önceden tanımlanmış kural kümelerini kullanabilirsiniz. [Visual Studio C++ temel denetimi Reference](code-analysis-for-cpp-corecheck.md)' ın altındaki kurallara ilişkin başvuru makalelerini bulacaksınız.

- **Aritmetik kurallar**: aritmetik [taşma](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Res-overflow), [imzalanmış imzasız işlemler](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Res-unsigned)ve [bit işlemesini](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Res-nonnegative)algılamaya yönelik kurallar. <sup>15,6</sup>

- **Sınır kuralları**: [C++ temel yönergeleri sınır profilini](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#probounds-bounds-safety-profile)zorlar. <sup>15,3</sup>

- **Sınıf kuralları**: özel üye işlevlerinin ve sanal belirtimlerinin uygun kullanımına odaklanabilecek birkaç kural. [Sınıflar ve sınıf hiyerarşileri](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#S-class)için önerilen denetimlerin bir alt kümesidir. <sup>15,5</sup>

- **Eşzamanlılık kuralları**: Hatalı koruyucu nesne bildirimlerini yakalayan tek bir kural. Daha fazla bilgi için bkz. [eşzamanlılık ile ilgili yönergeler](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#S-concurrency). <sup>15,5</sup>

- **Const kuralları**: [C++ temel yönergeleri const ile ilgili denetimleri](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#con-constants-and-immutability)zorla. <sup>15,3</sup>

- **Bildirim kuralları**: genel değişkenlerin nasıl [bildiribileceğine odaklanarak arabirimler yönergelerinden](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#S-interfaces) oluşan birkaç kural. <sup>15,5</sup>

- **Numaralandırma kuralları**: Bu kurallar [, C++ temel yönergeleri Enum ile ilgili denetimleri](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#S-enum)uygular. <sup>16,3</sup>

- **Deneysel kurallar** Bunlar, çok yararlı olan ancak günlük kullanıma yönelik olmayan C++ Temel Denetimi kurallardır. Bunları deneyin ve [geri bildirim sağlayın](https://aka.ms/feedback/suggest?space=62). <sup>16,0</sup>

- **Işlev kuralları**: belirticinin benimsenmesine yardımcı olan iki denetim **`noexcept`** . [Açık işlev tasarımı ve uygulamasıyla](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#S-functions)ilgili yönergelerin bir parçasıdır. <sup>15,5</sup>

- **GSL kuralları**: Bu kurallar, [C++ temel yönergeleri kılavuz destek kitaplığıyla](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#S-gsl)ilgili denetimleri uygular. <sup>15,7</sup>

- **Ömür kuralları**: bu kurallar [C++ temel yönergeleri ömür profilini](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#prolifetime-lifetime-safety-profile)uygular. <sup>15,7</sup>

- **Sahip Işaretçisi kuralları**: [ \<T> C++ temel yönergeleri sahip ile ilgili kaynak yönetimi denetimlerini](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#r-resource-management)zorlayın.<sup> 15,3</sup>

- **Ham Işaretçi kuralları**: [C++ temel yönergeleri ham işaretçilerle ilgili kaynak yönetimi denetimlerini](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#r-resource-management)zorlayın. <sup>15,3</sup>

- **Paylaşılan Işaretçi kuralları**: [kaynak yönetimi](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#S-resource) yönergeleri zorlaması 'nın bir parçasıdır. <sup>15,5</sup> paylaşılan işaretçilerin işlevlere nasıl geçirildiğine veya yerel olarak nasıl kullanıldığına özgü birkaç kural ekledik.

- **STL kuralları**: Bu kurallar, [C++ temel yönergeleri C++ standart kitaplığı (STL)](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#S-stdlib)ile ilgili denetimleri uygular. <sup>15,7</sup>

- **Stil kuralları**: [goto](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Res-goto)'in kullanıldığı basit ancak önemli bir denetim. <sup>15,5</sup> , kodlama stilinizi ve C++ ' da ifadelerin ve deyimlerin kullanımını geliştirmenin ilk adımıdır.

- **Tür kuralları**: [C++ temel yönergeleri tür profilini](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#prosafety-type-safety-profile)zorla. <sup>15,3</sup>

- **Benzersiz Işaretçi kuralları**: [C++ temel yönergeleri benzersiz işaretçi semantiğine sahip türlerle ilgili kaynak yönetimi denetimlerini](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#r-resource-management)zorlayın. <sup>15,3</sup>

- **C++ temel denetimi kuralları**: Bu kural kümesi, deneysel kurallar dışında, şu anda uygulanmış olan tüm denetimleri içerir [C++ temel yönergeleri](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#c-core-guidelines).

<sup>15,3</sup> bu kurallar Ilk olarak Visual Studio 2017 sürüm 15,3 \ ' de görüntülendi.
<sup>15,5</sup> bu kurallar Ilk olarak Visual Studio 2017 sürüm 15,5 \ ' de görüntülendi.
<sup>15,6</sup> bu kurallar Ilk olarak Visual Studio 2017 sürüm 15,6 \ ' de görüntülendi.
<sup>15,7</sup> bu kurallar Ilk olarak Visual Studio 2017 sürüm 15,7 \ ' de görüntülendi.
<sup>16,0</sup> bu kurallar Ilk olarak Visual Studio 2019 sürüm 16,0 \ ' de görüntülendi.
<sup>16,3</sup> bu kurallar Ilk olarak Visual Studio 2019 sürüm 16,3 ' de görüntülendi

Uyarıları yalnızca bir veya birkaç gruptan sınırlandırmayı seçebilirsiniz. **Yerel en düşük** ve **Yerel önerilen** kural kümeleri C++ temel denetimi kuralları ve diğer ön hızlı denetimleri içerir.

::: moniker range="<=msvc-150"

Kullanılabilir kural kümelerini görmek için, **Proje özellikleri** iletişim kutusunu açın. **Özellik sayfaları** iletişim kutusunda **yapılandırma özellikleri**  >  **Kod Analizi**  >  **genel** özellik sayfasını seçin. Ardından, kullanılabilir kural kümelerini görmek için, **kural kümeleri** açılan kutusunda açılan menüyü açın. Kural kümelerinin özel bir birleşimini oluşturmak için, **birden çok kural kümesi Seç**' i seçin. **Kural kümeleri Ekle veya Kaldır** iletişim kutusu, aralarından seçim yapabileceğiniz kuralları listeler. Visual Studio 'da kural kümeleri kullanma hakkında daha fazla bilgi için bkz. [çalıştırılacak C++ kurallarını belirtmek için kural kümelerini kullanma](using-rule-sets-to-specify-the-cpp-rules-to-run.md).

::: moniker-end
::: moniker range=">=msvc-160"

Kullanılabilir kural kümelerini görmek için, **Proje özellikleri** iletişim kutusunu açın. **Özellik sayfaları** iletişim kutusunda **yapılandırma özellikleri**  >  **Kod Analizi**  >  **Microsoft** özellik sayfasını seçin. Ardından, kullanılabilir kural kümelerini görmek için **etkin kurallar** açılan kutusunda açılan menüyü açın. Kural kümelerinin özel bir birleşimini oluşturmak için, **birden çok kural kümesi Seç**' i seçin. **Kural kümeleri Ekle veya Kaldır** iletişim kutusu, aralarından seçim yapabileceğiniz kuralları listeler. Visual Studio 'da kural kümeleri kullanma hakkında daha fazla bilgi için bkz. [çalıştırılacak C++ kurallarını belirtmek için kural kümelerini kullanma](using-rule-sets-to-specify-the-cpp-rules-to-run.md).

::: moniker-end

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

Microsoft C++ derleyicisinin özniteliği için sınırlı desteği vardır `[[gsl::suppress]]` . Deyim ve işlev içindeki blok deyimlerindeki uyarıları bastırmak için kullanılabilir.

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

1. **Çözüm Gezgini** dosyasında dosyaya sağ tıklayın ve **Özellikler**' i seçin.

1. **Özellik sayfaları** iletişim kutusunda, **yapılandırma özellikleri**  >  **C/C++**  >  **komut satırı** Özellik sayfası ' nı seçin.

1. **Ek seçenekler** düzenleme kutusunda, ekleyin *`/wd26400`* .

Komut satırı seçeneğini belirterek, bir dosyanın tüm kod analizini geçici olarak devre dışı bırakabilirsiniz **`/analyze-`** . Daha sonra kod analizini yeniden etkinleştirmenizi hatırlatır, ' */analiz ze-' ile '/Analyze ' öğesini geçersiz kılmayı* bildiren bir uyarı D9025 görürsünüz.

## <a name="enable-the-c-core-guidelines-checker-on-specific-project-files"></a><a name="corecheck_per_file"></a> Belirli proje dosyalarında C++ Temel Yönergeleri denetleyiciyi etkinleştirin

Bazen odaklanmış kod analizi yapmak ve Visual Studio IDE 'yi kullanmaya devam etmek faydalı olabilir. Büyük projeler için aşağıdaki örnek senaryoyu deneyin. Derleme süresini kaydedebilir ve sonuçların filtrelemesine daha kolay hale getirebilirsiniz:

1. Komut kabuğu 'nda `esp.extension` ve `esp.annotationbuildlevel` ortam değişkenlerini ayarlayın.

1. Bu değişkenleri devralması için komut kabuğundan Visual Studio 'Yu açın.

1. Projenizi yükleyin ve özelliklerini açın.

1. Kod analizini etkinleştirin, uygun kural kümelerini seçin, ancak kod analizi uzantılarını etkinleştirmeyin.

1. C++ Temel Yönergeleri denetleyicisi ile çözümlemek istediğiniz dosyaya gidin ve özelliklerini açın.

1. **Yapılandırma özelliklerini** seçin  >  **C/C++**  >  **komut satırı**  >  **ek seçenekler** ve Ekle *`/analyze:plugin EspXEngine.dll`*

1. Önceden derlenmiş üstbilginin kullanımını devre dışı bırakın (**yapılandırma özellikleri**  >  **C/C++**  >  **önceden derlenmiş üst bilgiler**). Uzantı altyapısı, ön derlenmiş üst bilgiden (PCH) iç bilgilerini okumaya çalışabileceğinden, gereklidir. PCH varsayılan proje seçenekleriyle derlenmişse uyumlu olmaz.

1. Projeyi yeniden derleyin. Ortak önceden denetim denetimleri tüm dosyalarda çalıştırılmalıdır. C++ Temel Yönergeleri denetleyicisi varsayılan olarak etkin olmadığından, yalnızca onu kullanmak üzere yapılandırılmış dosya üzerinde çalışmalıdır.

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

Dosya içeri aktarmadan önce bu özellikleri eklediğinizden emin olun *`Microsoft.Cpp.targets`* . Belirli kural kümelerini seçebilir veya özel bir kural kümesi oluşturabilirsiniz. Ya da, diğer ön denetimleri içeren varsayılan kural kümesini kullanın.

C++ Core Checker 'ı yalnızca belirtilen dosyalarda çalıştırabilirsiniz. [Daha önce açıklandığı](#corecheck_per_file)gibi aynı yaklaşımı kullanın, ancak MSBuild dosyalarını kullanın. Ortam değişkenleri şu öğe kullanılarak ayarlanabilir `BuildMacro` :

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

MSBuild üzerinde olmayan bir yapı sistemi kullanıyorsanız, denetleyiciyi çalışmaya devam edebilirsiniz. Bunu kullanmak için, kod analizi altyapısı yapılandırmasının bazı iç kodlarını tanımanız gerekir. Visual Studio 'nun gelecek sürümlerinde bu iç yapılar için destek garantisi vermeyiz.

Kod analizi için birkaç ortam değişkeni ve derleyici komut satırı seçeneği gereklidir. Derleyici, dizin ekleme vb. için belirli yolları aramanız gerekmiyorsa **Yerel araçlar komut istemi** ortamını kullanmanızı öneririz.

- **Ortam değişkenleri**
  - `set esp.extensions=cppcorecheck.dll` Bu, altyapıya C++ Temel Yönergeleri modülünü yüklemesini söyler.
  - `set esp.annotationbuildlevel=ignore` Bu, SAL ek açıklamalarını işleyen mantığı devre dışı bırakır. Ek açıklamalar C++ Temel Yönergeleri denetleyicisi 'nde Kod analizini etkilemez, ancak işlemleri zaman alır (bazen uzun zaman). Bu ayar isteğe bağlıdır, ancak önemle önerilir.
  - `set caexcludepath=%include%` Standart üstbilgiler üzerinde başlatılan uyarıları devre dışı bırakmanızı kesinlikle öneririz. Buraya daha fazla yol ekleyebilirsiniz. Örneğin, projenizdeki ortak üst bilgilerin yolu.

- **Komut satırı seçenekleri**
  - **`/analyze`**  Kod analizini etkinleştirilir (ve kullanmayı da **`/analyze:only`** düşünün **`/analyze:quiet`** ).
  - **`/analyze:plugin EspXEngine.dll`** Bu seçenek, kod analizi uzantıları altyapısını önceden hızlı yükler. Bu altyapı, sırasıyla C++ Temel Yönergeleri denetleyiciyi yükler.

## <a name="use-the-guideline-support-library"></a>Kılavuz desteği kitaplığını kullanma

Kılavuz Desteği kitaplığı (GSL), temel yönergeleri takip etmenize yardımcı olmak için tasarlanmıştır. GSL, hataya açık olan yapıları daha güvenli alternatifler ile değiştirmenize olanak tanıyan tanımlar içerir. Örneğin, bir `T*, length` parametre çiftini `span<T>` türüyle değiştirebilirsiniz. GSL projesi, tarihinde GitHub 'da kullanılabilir [https://github.com/Microsoft/GSL](https://github.com/Microsoft/GSL) . Kitaplık açık kaynağıdır, bu sayede kaynakları görüntüleyebilir, yorum yapabilir veya katkıda bulunabilirsiniz. Ayrıca, Kitaplığı yerel olarak indirip yüklemek için [vcpkg](../build/vcpkg.md) paket yöneticisini da kullanabilirsiniz.

::: moniker range="msvc-140"

## <a name="use-the-c-core-check-guidelines-in-visual-studio-2015-projects"></a><a name="vs2015_corecheck"></a> Visual Studio 2015 projelerinde C++ Temel Denetimi yönergeleri kullanma

Visual Studio 2015 kullanıyorsanız, C++ Temel Denetimi Code Analysis kural kümeleri varsayılan olarak yüklenmez. Visual Studio 2015 ' de C++ Temel Denetimi Code Analysis araçlarını etkinleştirebilmeniz için ek adımlar gerekir. Microsoft, bir NuGet paketi kullanarak Visual Studio 2015 projeleri için destek sağlar. Paket Microsoft. CppCoreCheck olarak adlandırılmıştır ve ' de mevcuttur [http://www.nuget.org/packages/Microsoft.CppCoreCheck](https://www.nuget.org/packages/Microsoft.CppCoreCheck) . Bu paket, güncelleştirme 1 ile en az Visual Studio 2015 yüklü olmasını gerektirir.

Paket, yalnızca üst bilgi kılavuz Desteği kitaplığı (GSL) olarak başka bir paket de bir bağımlılık olarak yüklenir. GSL, konumundaki GitHub 'da da kullanılabilir [https://github.com/Microsoft/GSL](https://github.com/Microsoft/GSL) .

Kod Analizi kurallarının Visual Studio 2015 içinde yüklenme biçimi nedeniyle, `Microsoft.CppCoreCheck` denetlemek istediğiniz her C++ projesine NuGet paketini yüklemelisiniz.

### <a name="to-add-the-microsoftcppcorecheck-package-to-your-project-in-visual-studio-2015"></a>Visual Studio 2015 ' de projenize Microsoft. CppCoreCheck paketini eklemek için

1. **Çözüm Gezgini**' de, paketi eklemek istediğiniz çözümde projenizin bağlam menüsünü açmak için sağ tıklayın. NuGet **paket yöneticisini** açmak Için **NuGet Paketlerini Yönet** ' i seçin.

1. **NuGet Paket Yöneticisi** penceresinde Microsoft. CppCoreCheck öğesini arayın.

    ![NuGet Paket Yöneticisi penceresi CppCoreCheck paketini gösterir](../code-quality/media/cppcorecheck_nuget_window.png)

1. Microsoft. CppCoreCheck paketini seçin ve ardından, kuralları projenize eklemek için **yükler** düğmesini seçin.

   NuGet paketi projenize *`.targets`* Kod analizini etkinleştirdiğinizde çağrılan ek bir MSBuild dosyası ekler. *`.targets`* Dosya, C++ temel denetimi kurallarını Visual Studio Code Analysis aracına ek bir uzantı olarak ekler. Paket yüklendiğinde, yayınlanan ve deneysel kuralları etkinleştirmek veya devre dışı bırakmak için özellik sayfaları iletişim kutusunu kullanabilirsiniz.

::: moniker-end

## <a name="see-also"></a>Ayrıca bkz.

- [Visual Studio C++ Temel Denetimi başvurusu](code-analysis-for-cpp-corecheck.md)
