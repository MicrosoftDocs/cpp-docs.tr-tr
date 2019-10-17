---
title: /analyze (Kod analizi)
ms.date: 10/15/2019
f1_keywords:
- VC.Project.VCCLCompilerTool.EnablePREfast
- /analyze
- VC.Project.VCCLCompilerTool.PREfastAdditionalOptions
- VC.Project.VCCLCompilerTool.PREfastAdditionalPlugins
helpviewer_keywords:
- /analyze compiler option [C++]
- -analyze compiler option [C++]
- analyze compiler option [C++]
ms.assetid: 81da536a-e030-4bd4-be18-383927597d08
ms.openlocfilehash: f537fdea2703805c7ab1c57ba0d4429f6b683ae4
ms.sourcegitcommit: 9aab425662a66825772f091112986952f341f7c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72444893"
---
# <a name="analyze-code-analysis"></a>/analyze (Kod analizi)

Kod analizini ve denetim seçeneklerini etkinleştirir.

## <a name="syntax"></a>Sözdizimi

> **/Analyze**[-] [ **: WX-** ] [ **: günlük** *dosya adı*] [:**quiet**] [ **: stacksize** *Number*] [:**max_paths** *sayı*] [ **: yalnızca**] [ **: RuleSet** *RuleSet*] [ **:p Lugin**  *eklenti-dll*]

## <a name="arguments"></a>Arguments

**/analyze**\
Varsayılan modda analizi açar. Analiz çıktısı, diğer hata iletileri gibi **Çıkış** penceresine gider. Analizini açık bir şekilde kapatmak için **/analze-** kullanın.

**/Analyze: WX-** \
**/WX**kullanarak derlerken kod analizi uyarıları hata olarak değerlendirilmez. Daha fazla bilgi için bkz. [/WX (uyarı düzeyi)](compiler-option-warning-level.md).

**/Analyze: günlük** *dosya adı*\
Ayrıntılı çözümleyici sonuçları, *dosya adıyla belirtilen*dosyaya XML olarak yazılır.

**/Analyze: quiet**\
Çözümleyici çıkışını **Çıkış** penceresine kapatır.

**/Analyze: stacksize** *Number*\
Bu seçenekle kullanılan *Number* parametresi, uyarı [C6262](/visualstudio/code-quality/c6262) 'nin oluşturulduğu yığın çerçevesinin boyutunu bayt cinsinden belirtir. *Sayıdan* önceki alan isteğe bağlıdır. Bu parametre belirtilmezse, yığın çerçeve boyutu varsayılan olarak 16 KB 'tır.

**/Analyze: max_paths** *Number*\
Bu seçenekle kullanılan *Number* parametresi, çözümlenecek en fazla kod yolu sayısını belirtir. Bu parametre belirtilmemişse, sayı varsayılan olarak 256 ' dir. Daha büyük değerler daha kapsamlı denetim oluşmasına neden olur, ancak analiz daha uzun sürebilir.

**/Analyze: yalnızca**\
Genellikle, derleyici kodu oluşturur ve çözümleyiciyi çalıştırdıktan sonra biraz daha sözdizimi denetimi yapar. **/Analyze: Only** seçeneği bu kod oluşturma geçişini kapatır. Analiz daha hızlı hale getirir, ancak derleyicinin kod oluşturma geçişinin bulabileceği hataları ve uyarıları derler. Program kod oluşturma hatalarından muaf değilse, analiz sonuçları güvenilir olmayabilir. Bu seçeneği yalnızca, kod oluşturma sözdizimi denetimini hatasız olarak geçerse kullanmanız önerilir.

**/Analyze: RuleSet** bir *. RuleSet*\
, Sizin oluşturabileceğiniz özel kural kümeleri de dahil olmak üzere hangi kural kümelerinin analiz edeceğinizi belirtmenize izin verir. Bu anahtar ayarlandığında, kural altyapısı daha etkilidir, çünkü çalıştırılmadan önce belirtilen kural kümesini üye olmayanları hariç tutar. Aksi halde, motor tüm kuralları denetler.

Visual Studio ile birlikte gelen RuleSets 'ler *%VSInstallDir%\Team Tools\Static Analysis Tools\kural kümelerinde bulunur.*

Aşağıdaki örnek özel kural kümesi, Rules altyapısından C6001 ve C26494 denetimi yapacağını söyler. Bu dosyayı `.ruleset` uzantısı olduğu sürece herhangi bir yere yerleştirebilirsiniz ve bağımsız değişkende tam yolu sağlarsınız.

```xml
<?xml version="1.0" encoding="utf-8"?>
<RuleSet Name="New Rule Set" Description=" " ToolsVersion="15.0">
  <Rules AnalyzerId="Microsoft.Analyzers.NativeCodeAnalysis" RuleNamespace="Microsoft.Rules.Native">
    <Rule Id="C6001" Action="Warning" />
    <Rule Id="C26494" Action="Warning" />
  </Rules>
</RuleSet>
```

**/Analyze: Plugin** *eklentisi-dll*\
Kod Analizi çalıştırmalarının bir parçası olarak belirtilen ön Fast eklentisine izin vermez.

::: moniker range="<=vs-2017"

LocalEspC. dll, C261XX uyarı aralığında eşzamanlılık ile ilgili kod analizi denetimleri uygulayan bir eklentidir. Örneğin, [C26100](/visualstudio/code-quality/c26100), [C26101](/visualstudio/code-quality/c26101),..., [C26167](/visualstudio/code-quality/c26167).

LocalEspC. dll dosyasını çalıştırmak için şu derleyici seçeneğini kullanın: **/Analyze: Plugin LocalEspC. dll**

::: moniker-end
::: moniker range=">=vs-2019"

ConcurrencyCheck. dll, C261XX uyarıları aralığında eşzamanlılık ile ilgili kod analizi denetimleri uygular. Örneğin, [C26100](/visualstudio/code-quality/c26100), [C26101](/visualstudio/code-quality/c26101),..., [C26167](/visualstudio/code-quality/c26167).

ConcurrencyCheck. dll dosyasını çalıştırmak için önce bir geliştirici komut isteminden bu komutu çalıştırın:

```cmd
set Esp.Extensions=ConcurrencyCheck.dll
```

Sonra bu derleyici seçeneğini kullanın: **/Analyze: Plugin EspXEngine. dll**.

::: moniker-end

CppCoreCheck. dll dosyasını çalıştırmak için öncelikle bir geliştirici komut isteminden bu komutu çalıştırın:

```cmd
set Esp.Extensions=CppCoreCheck.dll
```

Sonra bu derleyici seçeneğini kullanın: **/Analyze: Plugin EspXEngine. dll**.

## <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. c/ [C++ Overview için kod analizi](/visualstudio/code-quality/code-analysis-for-c-cpp-overview) ve [c/C++ uyarılar için kod analizi](/visualstudio/code-quality/code-analysis-for-c-cpp-warnings).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual C++ Studio 'da derleyici ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. @No__t-1**kod analizi** > **genel** özellik sayfasını **yapılandırma özellikleri**' ni seçin.

1. Bir veya daha fazla **Kod Analizi** özelliğini değiştirin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

1. Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnablePREfast%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)\
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)
