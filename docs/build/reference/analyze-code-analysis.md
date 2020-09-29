---
title: /analyze (Kod analizi)
description: Microsoft C++ derleyicisi, seçenek sözdizimi ve kullanımını/Analyze.
ms.date: 07/27/2020
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
ms.openlocfilehash: e970872e89132aed52190b8688f2cdaccab5ea6f
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91500080"
---
# <a name="analyze-code-analysis"></a>`/analyze` (Kod analizi)

Kod analizini ve denetim seçeneklerini etkinleştirir.

## <a name="syntax"></a>Sözdizimi

::: moniker range=">=vs-2017"

> **`/analyze`**\
> **`/analyze-`**\
> **`/analyze:autolog`**\
> **`/analyze:autolog-`**\
> **`/analyze:autolog:ext`***uzantı*\
> **`/analyze:log`***dosya adı*\
> **`/analyze:max_paths`***sayı*\
> **`/analyze:only`**\
> **`/analyze:plugin`***eklenti-dll*\
> **`/analyze:quiet`**\
> **`/analyze:ruleset`***RuleSet*\
> **`/analyze:stacksize`***sayı*\
> **`/analyze:WX-`**

::: moniker-end
::: moniker range="vs-2015"

> **`/analyze`**\
> **`/analyze-`**\
> **`/analyze:autolog`**\
> **`/analyze:autolog-`**\
> **`/analyze:autolog:ext`***uzantı*\
> **`/analyze:log`***dosya adı*\
> **`/analyze:max_paths`***sayı*\
> **`/analyze:only`**\
> **`/analyze:plugin`***eklenti-dll*\
> **`/analyze:quiet`**\
> **`/analyze:stacksize`***sayı*\
> **`/analyze:WX-`**

::: moniker-end

## <a name="arguments"></a>Arguments

**`/analyze`**\
Varsayılan modda analizini etkinleştirir. Analiz çıktısı konsola veya Visual Studio **çıktı** penceresine diğer hata iletileri gibi gider. **`/analyze-`** Çözümlemeyi açıkça devre dışı bırakmak için kullanın.

**`/analyze:autolog`**\
Ayrıntılı çözümleyici sonuçları, kaynak dosya ve uzantısı ile aynı temel adı taşıyan bir dosyaya XML olarak yazılır *`.pftlog`* . **`/analyze:autolog-`** Bu günlük dosyasını devre dışı bırakır.

**`/analyze:autolog:ext`***uzantı*\
Ayrıntılı çözümleyici sonuçları, kaynak dosya ve *uzantı*uzantısıyla aynı temel ada sahip BIR dosyaya XML olarak yazılır.

**`/analyze:log`***dosya adı*\
Ayrıntılı çözümleyici sonuçları, *dosya adıyla belirtilen*dosyaya XML olarak yazılır.

**`/analyze:max_paths`***sayı*\
Bu seçenekle kullanılan *Number* parametresi, çözümlenecek en fazla kod yolu sayısını belirtir. Bu parametre belirtilmemişse, sayı varsayılan olarak 256 ' dir. Daha büyük değerler daha kapsamlı denetim oluşmasına neden olur, ancak analiz daha uzun sürebilir.

**`/analyze:only`**\
Genellikle, derleyici kod oluşturur ve çözümleyici 'yi çalıştırdıktan sonra daha fazla sözdizimi denetimi yapar. **`/analyze:only`** Seçeneği bu kod oluşturma geçişini kapatır. Analiz daha hızlı hale getirir, ancak derleyicinin kod oluşturma geçişinin bulabileceği derleyici hatalarını ve uyarılarını geçirmez. Program kod oluşturma hatalarından muaf değilse, analiz sonuçları güvenilir olmayabilir. Bu seçeneği yalnızca, kod oluşturma sözdizimi denetimini hatasız olarak geçerse kullanmanız önerilir.

**`/analyze:plugin`***eklenti-dll*\
Kod Analizi çalıştırmalarının bir parçası olarak belirtilen ön Fast eklentisine izin vermez.

::: moniker range="<=vs-2017"

LocalEspC.dll, C261XX uyarı aralığında eşzamanlılık ile ilgili kod analizi denetimleri uygulayan eklentidir. Örneğin, [C26100](../../code-quality/c26100.md), [C26101](../../code-quality/c26101.md),...,  [C26167](../../code-quality/c26167.md).

LocalEspC.dll çalıştırmak için, bu derleyici seçeneğini kullanın: **`/analyze:plugin LocalEspC.dll`**

::: moniker-end
::: moniker range=">=vs-2019"

ConcurrencyCheck.dll, C261XX uyarı aralığında eşzamanlılık ile ilgili kod analizi denetimleri uygular. Örneğin, [C26100](../../code-quality/c26100.md), [C26101](../../code-quality/c26101.md),...,  [C26167](../../code-quality/c26167.md).

ConcurrencyCheck.dll çalıştırmak için öncelikle bu komutu bir geliştirici komut isteminden çalıştırın:

```cmd
set Esp.Extensions=ConcurrencyCheck.dll
```

Sonra bu derleyici seçeneğini kullanın: **`/analyze:plugin EspXEngine.dll`** .

CppCoreCheck.dll çalıştırmak için öncelikle bu komutu bir geliştirici komut isteminden çalıştırın:

```cmd
set Esp.Extensions=CppCoreCheck.dll
```

Sonra bu derleyici seçeneğini kullanın: **`/analyze:plugin EspXEngine.dll`** .

::: moniker-end

**`/analyze:quiet`**\
Çözümleyici çıkışını konsola veya Visual Studio **çıktı** penceresine kapatır.

::: moniker range=">=vs-2017"

**`/analyze:ruleset`***file_path. RuleSet*\
, Sizin oluşturabileceğiniz özel kural kümeleri de dahil olmak üzere hangi kural kümelerinin analiz edeceğinizi belirtmenize izin verir. Bu anahtar ayarlandığında, kural altyapısı daha etkilidir, çünkü çalıştırılmadan önce belirtilen kural kümesini üye olmayanları hariç tutar. Aksi halde, motor tüm kuralları denetler.

Visual Studio ile birlikte gelen RuleSets 'ler içinde bulunur *`%VSINSTALLDIR%\Team Tools\Static Analysis Tools\Rule Sets`* .

Aşağıdaki örnek özel kural kümesi, Rules altyapısından C6001 ve C26494 denetimi yapacağını söyler. Bu dosyayı, uzantısı olduğu sürece herhangi bir yere yerleştirebilirsiniz *`.ruleset`* ve bağımsız değişkende tam yolu sağlarsınız.

```xml
<?xml version="1.0" encoding="utf-8"?>
<RuleSet Name="New Rule Set" Description="New rules to apply." ToolsVersion="15.0">
  <Rules AnalyzerId="Microsoft.Analyzers.NativeCodeAnalysis" RuleNamespace="Microsoft.Rules.Native">
    <Rule Id="C6001" Action="Warning" />
    <Rule Id="C26494" Action="Warning" />
  </Rules>
</RuleSet>
```

::: moniker-end

**`/analyze:stacksize`***sayı*\
Bu seçenekle kullanılan *Number* parametresi, uyarı [C6262](../../code-quality/c6262.md) 'nin oluşturulduğu yığın çerçevesinin boyutunu bayt cinsinden belirtir. *Sayıdan* önceki alan isteğe bağlıdır. Bu parametre belirtilmezse, yığın çerçeve boyutu varsayılan olarak 16 KB 'tır.

**`/analyze:WX-`**\
Kullanarak derlerken kod analizi uyarıları hata olarak değerlendirilmez **`/WX`** . Daha fazla bilgi için bkz. [ `/WX` (uyarı düzeyi)](compiler-option-warning-level.md).

## <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. c [/c++ Için kod analizine genel bakış](../../code-quality/code-analysis-for-c-cpp-overview.md) ve [c/C++ uyarıları için kod analizi](../../code-quality/code-analysis-for-c-cpp-warnings.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **Kod Analizi**  >  **genel** özellik sayfasını seçin.

1. Bir veya daha fazla **Kod Analizi** özelliğini değiştirin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

1. Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnablePREfast%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)\
[MSVC derleyici komut satırı sözdizimi](compiler-command-line-syntax.md)
