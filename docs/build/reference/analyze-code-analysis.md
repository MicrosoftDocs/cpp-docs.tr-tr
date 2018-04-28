---
title: -analyze (kod çözümleme) | Microsoft Docs
ms.custom: ''
ms.date: 04/26/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
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
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0f706c3ff32635384766ac2c028cc0e5096118b8
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2018
---
# <a name="analyze-code-analysis"></a>/analyze (Kod Çözümleme)

Kod analizini ve denetim seçeneklerini etkinleştirir.

## <a name="syntax"></a>Sözdizimi

```cmd
/analyze[-][:WX-][:log filename][:quiet][:stacksize number][:max_paths number][:only][:ruleset]
```

## <a name="arguments"></a>Arguments

 /analyze  
 Varsayılan modda analizi açar. Analiz çıkış gider **çıkış** pencere gibi diğer hata iletileri. Kullanım **/ analyze-** açıkça analiz devre dışı bırakma.

 /analyze:WX-  
 Belirtme **/ analyze: WX -** Kod Analizi uyarıları anlamına gelir değil kabul edilir hata olarak kullanarak derlediğinizde **/WX**. Daha fazla bilgi için bkz: [/w, /W0, /W1, /W2, /W3, /W4, /w1, /w2, /w3, /w4, wln, /wd, / biz, /wo, /Wv, /WX (uyarı düzeyi)](../../build/reference/compiler-option-warning-level.md).

 / analyze: günlük `filename`  
 Ayrıntılı Çözümleyicisi sonuçları tarafından belirtilen dosya için XML olarak yazılır `filename`.

 /analyze:quiet  
 Çözümleyici çıktısına kapatır **çıkış** penceresi.

 / analyze: stacksıze `number`  
 `number` Bu seçenek ile kullanılır parametre yığın çerçevesi hangi uyarı için bayt cinsinden boyutu belirtir [C6262](/visualstudio/code-quality/c6262) oluşturulur. Bu parametre belirtilmezse, yığın çerçevesinin boyutu varsayılan olarak 16 KB olur.

 / analyze: max_paths `number`  
 `number` Bu seçenek ile kullanılan parametre çözümlenecek kod yollarının en fazla sayısını belirtir. Bu parametre belirtilmezse, sayı varsayılan olarak 256 olur. Daha büyük değerler daha kapsamlı denetleme gerçekleştirir ancak çözümleme uzun sürebilir.

 /analyze:only  
 Genellikle, derleyici kodu oluşturur ve çözümleyiciyi çalıştırdıktan sonra biraz daha sözdizimi denetimi yapar. **/ Analyze: yalnızca** seçeneği bu kod oluşturma geçişi devre dışı bırakır; Bu analiz hızlandırır ancak derleme hataları ve kod oluşturma geçişi derleyici tarafından bulunmuş uyarıları yayılan değil. Programda kod oluşturma hataları varsa, analiz sonuçları güvenilir olmayabilir. Bu nedenle, bu seçeneği yalnızca kod oluşturma sözdizimi denetimini hatasız şekilde geçerse kullanmanızı öneririz.

 / analyze: ruleset `<file_path>.ruleset`  
Analiz etmek için hangi kural kümesi belirtme kendiniz oluşturmanız özel kural kümeleri dahil olmak üzere sağlar. Bu anahtarı ayarlandığında, kurallar altyapısı olmayan-üyeleri belirtilen kural çalıştırmadan önce kümesi dışlar olduğundan daha verimli olur. Anahtar ayarlanmadığında altyapısı tüm kuralları denetler.

Visual Studio ile birlikte rulesets bulunan **%VSINSTALLDIR%\Team Tools\Static analiz Tools\Rule ayarlar.**

Aşağıdaki örnek özel bir kural kümesi C6001 ve C26494 denetlemek için kurallar altyapısı söyler. Herhangi bir yere sahip olduğu sürece, bu dosya yerleştirebilirsiniz bir `.ruleset` uzantısı ve bağımsız değişkende tam yolunu sağlayın.

```xml
<?xml version="1.0" encoding="utf-8"?>
<RuleSet Name="New Rule Set" Description=" " ToolsVersion="15.0">
  <Rules AnalyzerId="Microsoft.Analyzers.NativeCodeAnalysis" RuleNamespace="Microsoft.Rules.Native">
    <Rule Id="C6001" Action="Warning" />
    <Rule Id="C26494" Action="Warning" />
  </Rules>
</RuleSet>
```

/ analyze: eklentisi  
Kod çözümleme parçası çalışırken belirtilen PREfast eklentisi sağlar. Eşzamanlılık ile ilgili kod analizi uygulayan eklentisi aralığı C261XX uyarıları denetler LocalEspC.dll olur. Örneğin, [C26100](/visualstudio/code-quality/c26100), [C26101](/visualstudio/code-quality/c26101),..., [C26167](/visualstudio/code-quality/c26167).

LocalEspC.dll çalıştırmak için bu derleyici seçeneği kullanın: **/ analyze: eklentisi LocalEspC.dll**

CppCoreCheck.dll çalıştırmak için önce bir geliştirici komut isteminde bu komutu çalıştırın:

```cmd
set Esp.Extensions=CppCoreCheck.dll
```

Bu derleyici seçeneği kullanın: **/ analyze: eklenti EspXEngine.dll**.

## <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz: [C/C++ genel bakış için Kod Analizi](/visualstudio/code-quality/code-analysis-for-c-cpp-overview) ve [C/C++ uyarıları için Kod Analizi](/visualstudio/code-quality/code-analysis-for-c-cpp-warnings).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).

1. Genişletme **yapılandırma özellikleri** düğümü.

1. Genişletme **Kod Analizi** düğümü.

1. Seçin **genel** özellik sayfası.

1. Bir veya daha fazla değişiklik **Kod Analizi** özellikleri.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

1. Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnablePREfast%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

- [Derleyici Seçenekleri](../../build/reference/compiler-options.md)
- [Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)