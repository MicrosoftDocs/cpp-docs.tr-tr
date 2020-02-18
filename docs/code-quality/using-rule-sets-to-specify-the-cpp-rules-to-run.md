---
title: Çalıştırılacak C++ Kurallarını Belirtmek için Kural Kümeleri Kullanma
ms.date: 04/28/2018
ms.topic: conceptual
f1_keywords:
- vs.codeanalysis.rulesets.native
ms.openlocfilehash: 5cf0f88c6937f4c1609a29fd618af0fdadad4437
ms.sourcegitcommit: 7bea0420d0e476287641edeb33a9d5689a98cb98
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/17/2020
ms.locfileid: "77418720"
---
# <a name="use-rule-sets-to-specify-the-c-rules-to-run"></a>Çalıştırılacak C++ kuralları belirtmek Için kural kümelerini kullanma

Visual Studio 'da, kod analizi ile ilişkili belirli proje ihtiyaçlarını karşılamak için özel bir *kural kümesi* oluşturabilir ve değiştirebilirsiniz. Varsayılan kural kümeleri `%VSINSTALLDIR%\Team Tools\Static Analysis Tools\Rule Sets`depolanır.

**Visual Studio 2017 sürüm 15,7 ve üzeri:** Herhangi bir metin düzenleyicisini kullanarak özel kural kümeleri oluşturabilir ve bunları, hangi yapı sistemini kullandığınıza bağımsız olarak komut satırı yapılarına uygulayabilirsiniz. Daha fazla bilgi için bkz. [/Analyze: RuleSet](/cpp/build/reference/analyze-code-analysis).

Visual Studio 'da özel C++ bir kural kümesi oluşturmak Için VISUAL Studio IDE 'deC++ bir C/Project açık olmalıdır. Daha sonra kural kümesi düzenleyicisinde bir standart kural kümesi açıp, belirli kuralları ekleyip kaldırarak ve isteğe bağlı olarak, kod analizi bir kuralın ihlal edildiğini belirlediğinde oluşan eylemi değiştirirsiniz.

Yeni bir özel kural kümesi oluşturmak için yeni bir dosya adı kullanarak bu dosyayı kaydedersiniz. Özel kural kümesi projeye otomatik olarak atanır.

## <a name="to-create-a-custom-rule-from-a-single-existing-rule-set"></a>Tek bir var olan kural kümesinden özel bir kural oluşturmak için

1. Çözüm Gezgini, proje için kısayol menüsünü açın ve ardından **Özellikler**' i seçin.

1. **Özellikler** sekmesinde, **Kod Analizi**' ni seçin.

1. **Kural kümesi** açılan listesinde aşağıdakilerden birini yapın:

   - Özelleştirmek istediğiniz kural kümesini seçin.

     \- veya-

   - **\<gözatmaya seç...** listede olmayan var olan bir kural kümesini belirtmek için >.

1. Kural kümesi düzenleyicisinde kuralları göstermek için **Aç** ' ı seçin.

## <a name="to-modify-a-rule-set-in-the-rule-set-editor"></a>Kural kümesi düzenleyicisinde bir kural kümesini değiştirmek için

- Kural kümesinin görünen adını değiştirmek için, **Görünüm** menüsünde **Özellikler penceresi**' ni seçin. **Ad** kutusuna görünen adı girin. Görünen adın dosya adından farklı olduğunu fark edebilirsiniz.

- Grubun tüm kurallarını özel bir kural kümesine eklemek için grubun onay kutusunu seçin. Grubun tüm kurallarını kaldırmak için onay kutusunu temizleyin.

- Özel kural kümesine belirli bir kural eklemek için, kuralın onay kutusunu seçin. Kuralı kural kümesinden kaldırmak için onay kutusunu temizleyin.

- Bir kod analizinde bir kural ihlal edildiğinde gerçekleştirilecek eylemi değiştirmek için, kural için **eylem** alanını seçin ve ardından aşağıdaki değerlerden birini seçin:

     **Uyarı** -bir uyarı oluşturur.

     **Hata** -bir hata oluşturur.

     **Bilgi** -bir ileti oluşturur.

     **Hiçbiri** -kuralı devre dışı bırakır. Bu eylem kural kümesinden kuralı kaldırma ile aynıdır.

## <a name="to-group-filter-or-change-the-fields-in-the-rule-set-editor-by-using-the-rule-set-editor-toolbar"></a>Kural kümesi Düzenleyicisi araç çubuğunu kullanarak kural kümesi düzenleyicisinde Alanları gruplandırmak, filtrelemek veya değiştirmek için

- Tüm gruplardaki kuralları genişletmek için **Tümünü Genişlet**' i seçin.

- Tüm gruplardaki kuralları daraltmak için **Tümünü Daralt**' ı seçin.

- Kuralların gruplandırıldığı alanı değiştirmek için **Gruplandırma ölçütü** listesinden alanı seçin. Gruplandırılmamış kuralları göstermek için **\<yok >** seçin.

- Kural sütunlarındaki alanları eklemek veya kaldırmak için **sütun seçenekleri**' yi seçin.

- Geçerli çözüm için geçerli olmayan kuralları gizlemek için **geçerli çözüm için geçerli olmayan kuralları gizle**' yi seçin.

- Hata eyleminin atandığı kuralları gösterme ve gizleme arasında geçiş yapmak için, **Kod Analizi hataları oluşturabilen kuralları göster**' i seçin.

- Uyarı eyleminin atandığı kuralları gösterme ve gizleme arasında geçiş yapmak için, **Kod Analizi uyarıları oluşturabilen kuralları göster**' i seçin.

- **Hiçbiri** eyleminin atandığı kuralları gösterme ve gizleme arasında geçiş yapmak için, **etkin olmayan kuralları göster**' i seçin.

- Geçerli kural kümesine Microsoft varsayılan kural kümelerini eklemek veya kaldırmak için **alt kural kümelerini Ekle veya Kaldır**' ı seçin.

## <a name="to-create-a-rule-set-in-a-text-editor"></a>Bir metin düzenleyicisinde bir kural kümesi oluşturmak için

Bir metin düzenleyicisinde özel bir kural kümesi oluşturabilir, `.ruleset` uzantısı olan herhangi bir konumda saklayabilir ve [/Analyze: RuleSet](/cpp/build/reference/analyze-code-analysis) derleyici seçeneğiyle ' de uygulayabilirsiniz.

Aşağıdaki örnek, başlangıç noktası olarak kullanabileceğiniz temel bir kural kümesi dosyasını gösterir:

::: moniker range="<=vs-2017"

```xml
<?xml version="1.0" encoding="utf-8"?>
<RuleSet Name="New Rule Set" Description=" " ToolsVersion="15.0">
  <Rules AnalyzerId="Microsoft.Analyzers.NativeCodeAnalysis" RuleNamespace="Microsoft.Rules.Native">
    <Rule Id="C6001" Action="Warning" />
    <Rule Id="C26494" Action="Warning" />
  </Rules>
</RuleSet>
```

::: moniker-end

::: moniker range=">=vs-2019"

```xml
<?xml version="1.0" encoding="utf-8"?>
<RuleSet Name="New Rule Set" Description=" " ToolsVersion="16.0">
  <Rules AnalyzerId="Microsoft.Analyzers.NativeCodeAnalysis" RuleNamespace="Microsoft.Rules.Native">
    <Rule Id="C6001" Action="Warning" />
    <Rule Id="C26494" Action="Warning" />
  </Rules>
</RuleSet>
```

::: moniker-end
