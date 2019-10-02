---
title: /analyze (kod analizi)
ms.date: 10/01/2019
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
ms.openlocfilehash: d647045d76dc32544f8146424b220547890b0943
ms.sourcegitcommit: 4517932a67bbf2db16cfb122d3bef57a43696242
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71816329"
---
# <a name="analyze-code-analysis"></a>/analyze (kod analizi)

Kod analizini ve denetim seçeneklerini sunar.

## <a name="syntax"></a>Sözdizimi

```cmd
/analyze[-][:WX-][:log filename][:quiet][:stacksize number][:max_paths number][:only][:ruleset]
```

## <a name="arguments"></a>Bağımsız Değişkenler

/Analyze varsayılan modda çözümlemeyi etkinleştirir. Analiz çıktısı, diğer hata iletileri gibi **Çıkış** penceresine gider. Analizini açık bir şekilde kapatmak için **/analze-** kullanın.

/Analyze: WX-belirleme **/Analyze: WX-** , **/WX**kullanarak derlerken kod analizi uyarılarının hata olarak değerlendirilmediği anlamına gelir. Daha fazla bilgi için bkz. [/w,/W0,/W1,/W2,/W3,/W4,/W1,/W2,/W3,/W4,/duvar,/WD,/we,/Wo,/WV,/WX (uyarı düzeyi)](compiler-option-warning-level.md).

/Analyze: log `filename` ayrıntılı çözümleyici sonuçları, `filename` tarafından belirtilen dosyaya XML olarak yazılır.

/Analyze: quiet, çözümleyici çıkışını **Çıkış** penceresine kapatır.

/Analyze: stacksize `number` Bu seçenekle kullanılan `number` parametresi, uyarı [C6262](/visualstudio/code-quality/c6262) 'nin oluşturulduğu yığın çerçevesinin boyutunu bayt cinsinden belirtir. @No__t-0 ' dan önceki alan isteğe bağlıdır. Bu parametre belirtilmemişse, yığın çerçeve boyutu varsayılan olarak 16 KB 'tır.

/Analyze: max_paths `number` Bu seçenekle kullanılan `number` parametresi, çözümlenecek en fazla kod yolu sayısını belirtir. Bu parametre belirtilmemişse, sayı varsayılan olarak 256 ' dir. Daha büyük değerler daha kapsamlı denetim gerçekleştirir, ancak analiz daha uzun sürebilir.

/Analyze: yalnızca genellikle derleyici kod oluşturur ve çözümleyici 'yi çalıştırdıktan sonra daha fazla sözdizimi denetimi yapar. **/Analyze: Only** seçeneği bu kod oluşturma geçişini kapatır; Bu, analizini daha hızlı hale getirir ancak derleyicinin kod oluşturma geçişi tarafından bulunmuş olabilecek hataları ve uyarıları derler. Program kod oluşturma hatalarından muaf değilse, analiz sonuçları güvenilir olmayabilir; Bu nedenle, bu seçeneği yalnızca kod oluşturma sözdizimi denetimini hatasız olarak geçerse kullanmanız önerilir.

/Analyze: RuleSet `<file_path>.ruleset`, sizin oluşturabileceğiniz özel kural kümeleri dahil olmak üzere analiz edilecek kural kümelerini belirtmenize olanak sağlar. Bu anahtar ayarlandığında, kural altyapısı, çalıştırılmadan önce belirtilen kural kümesini üye olmayanları dışladığı için daha etkilidir. Anahtar ayarlanmamışsa, motor tüm kuralları denetler.

Visual Studio ile birlikte gelen RuleSets 'ler **%VSInstallDir%\Team Tools\Static Analysis Tools\kural kümelerinde bulunur.**

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

/Analyze: Plugin, kod analizi çalıştırmaları kapsamında belirtilen ön Fast eklentisine Izin vermez.
LocalEspC. dll, C261XX uyarı aralığında eşzamanlılık ile ilgili kod analizi denetimleri uygulayan bir eklentidir. Örneğin, [C26100](/visualstudio/code-quality/c26100), [C26101](/visualstudio/code-quality/c26101),..., [C26167](/visualstudio/code-quality/c26167).

LocalEspC. dll dosyasını çalıştırmak için şu derleyici seçeneğini kullanın: **/Analyze: Plugin LocalEspC. dll**

CppCoreCheck. dll dosyasını çalıştırmak için öncelikle bir geliştirici komut isteminden bu komutu çalıştırın:

```cmd
set Esp.Extensions=CppCoreCheck.dll
```

Sonra bu derleyici seçeneğini kullanın: **/Analyze: Plugin EspXEngine. dll**.

## <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. c/ [C++ Overview için kod analizi](/visualstudio/code-quality/code-analysis-for-c-cpp-overview) ve [c/C++ uyarılar için kod analizi](/visualstudio/code-quality/code-analysis-for-c-cpp-warnings).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamında bu derleyici seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual C++ Studio 'da derleyici ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri** düğümünü genişletin.

1. **Kod Analizi** düğümünü genişletin.

1. **Genel** özellik sayfasını seçin.

1. Bir veya daha fazla **Kod Analizi** özelliğini değiştirin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program aracılığıyla ayarlamak için

1. @No__t-0 ' a bakın.

## <a name="see-also"></a>Ayrıca bkz.

- [MSVC derleyici seçenekleri](compiler-options.md)
- [MSVC derleyici komut satırı sözdizimi](compiler-command-line-syntax.md)
