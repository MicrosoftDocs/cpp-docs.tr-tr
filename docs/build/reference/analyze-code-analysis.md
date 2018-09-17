---
title: -analyze (kod çözümleme) | Microsoft Docs
ms.custom: ''
ms.date: 04/26/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.EnablePREfast
- /analyze
- VC.Project.VCCLCompilerTool.PREfastAdditionalOptions
- VC.Project.VCCLCompilerTool.PREfastAdditionalPlugins
dev_langs:
- C++
helpviewer_keywords:
- /analyze compiler option [C++]
- -analyze compiler option [C++]
- analyze compiler option [C++]
ms.assetid: 81da536a-e030-4bd4-be18-383927597d08
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 89f0402eedbe6e49d6ce4095dc8c91ec69e15447
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45723612"
---
# <a name="analyze-code-analysis"></a>/analyze (Kod Çözümleme)

Kod analizini ve denetim seçeneklerini etkinleştirir.

## <a name="syntax"></a>Sözdizimi

```cmd
/analyze[-][:WX-][:log filename][:quiet][:stacksize number][:max_paths number][:only][:ruleset]
```

## <a name="arguments"></a>Arguments

/ Varsayılan modda analizi açar analiz edin. Analiz çıktısı gider **çıkış** penceresi gibi diğer hata iletileri. Kullanım **/ analyze-** analizi açıkça etkinleştirmek için.

/ analyze: WX-belirtme **/ analyze: WX -** kullanarak derleme yaptığınızda Kod Analizi uyarılarının anlamına gelir hata olarak işlenmeyeceği **wx**. Daha fazla bilgi için [/w, /W0, / W1, / w2, / W3, / W4, / W1, / w2, / W3, / W4, /Wall, WD, / we Wo, wv, /WX (uyarı düzeyi)](../../build/reference/compiler-option-warning-level.md).

/ analyze: log `filename` ayrıntılı çözümleyici sonuçları tarafından belirtilen dosyaya XML olarak yazılır `filename`.

/ analyze: quiet kapatır çözümleyici çıktısını kapatmak **çıkış** penceresi.

/ analyze: stacksize `number` `number` bu seçenekle kullanılan parametresi, yığın çerçevesinin bayt cinsinden boyutunu belirtir [C6262](/visualstudio/code-quality/c6262) oluşturulur. Bu parametre belirtilmezse, yığın çerçevesinin boyutu varsayılan olarak 16 KB olur.

/ analyze: max_paths `number` `number` bu seçenekle kullanılan parametre kod yollar, çözümlenecek maksimum sayısını belirtir. Bu parametre belirtilmezse, sayı varsayılan olarak 256 olur. Daha büyük değerler daha kapsamlı denetleme gerçekleştirir ancak çözümleme uzun sürebilir.

/ analyze: yalnızca genel olarak, derleyici kodu oluşturur ve çözümleyiciyi çalıştırdıktan sonra biraz daha sözdizimi denetimi yapar. **/ Analyze: yalnızca** seçeneği bu kod oluşturma geçişini kapatır açar; bu analiz daha hızlı sağlar ancak derleme hataları ve derleyicinin kod oluşturma geçişi tarafından keşfedilebilecek uyarıları yayılmaz. Programda kod oluşturma hataları varsa, analiz sonuçları güvenilir olmayabilir. Bu nedenle, bu seçeneği yalnızca kod oluşturma sözdizimi denetimini hatasız şekilde geçerse kullanmanızı öneririz.

/ analyze: ruleset `<file_path>.ruleset` , analiz etmek için hangi kural kümesi belirtme kendiniz oluşturabileceğiniz özel kural kümeleri dahil olmak üzere sağlar. Bu anahtar ayarlandığında, kural altyapısı üyeleri olmayan çalıştırmadan önce kümesi belirtilen kural içermez çünkü daha verimli olur. Anahtar ayarlandığında, tüm kurallar altyapısı denetler.

Visual Studio ile birlikte gelen rulesets bulunan **%VSINSTALLDIR%\Team Tools\Static analizi Tools\Rule kümeleri.**

Aşağıdaki örnek özel kural kümesi C6001 ve C26494 denetlemek için kurallar altyapısı söyler. Herhangi bir yere sahip olduğu sürece, bu dosya yerleştirebilirsiniz bir `.ruleset` uzantısı ve bağımsız değişkende tam yolunu sağlayın.

```xml
<?xml version="1.0" encoding="utf-8"?>
<RuleSet Name="New Rule Set" Description=" " ToolsVersion="15.0">
  <Rules AnalyzerId="Microsoft.Analyzers.NativeCodeAnalysis" RuleNamespace="Microsoft.Rules.Native">
    <Rule Id="C6001" Action="Warning" />
    <Rule Id="C26494" Action="Warning" />
  </Rules>
</RuleSet>
```

/ analyze: eklenti çalışan kod analizi bir parçası olarak belirtilen PREfast eklenti sağlar.
Eşzamanlılık ile ilgili kod analizi uygulayan eklenti aralık C261XX uyarıları denetler LocalEspC.dll olur. Örneğin, [C26100](/visualstudio/code-quality/c26100), [C26101](/visualstudio/code-quality/c26101),..., [C26167](/visualstudio/code-quality/c26167).

LocalEspC.dll çalıştırmak için bu derleyici seçeneğini kullanın: **/ analyze: LocalEspC.dll eklentisi**

CppCoreCheck.dll çalıştırmak için önce bir geliştirici komut isteminden şu komutu çalıştırın:

```cmd
set Esp.Extensions=CppCoreCheck.dll
```

Ardından bu derleyici seçeneğini kullanın: **/ analyze: eklenti EspXEngine.dll**.

## <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [C/C++ genel bakış için Kod Analizi](/visualstudio/code-quality/code-analysis-for-c-cpp-overview) ve [C/C++ uyarıları için Kod Analizi](/visualstudio/code-quality/code-analysis-for-c-cpp-warnings).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Genişletin **yapılandırma özellikleri** düğümü.

1. Genişletin **Kod Analizi** düğümü.

1. Seçin **genel** özellik sayfası.

1. Bir veya daha fazla değişiklik **Kod Analizi** özellikleri.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

1. Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnablePREfast%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

- [Derleyici Seçenekleri](../../build/reference/compiler-options.md)
- [Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)