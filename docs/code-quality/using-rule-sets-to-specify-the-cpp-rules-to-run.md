---
description: 'Daha fazla bilgi edinin: çalıştırılacak C++ kurallarını belirtmek için kural kümeleri kullanma'
title: Çalıştırılacak C++ Kurallarını Belirtmek için Kural Kümeleri Kullanma
ms.date: 07/27/2020
ms.topic: conceptual
f1_keywords:
- vs.codeanalysis.rulesets.native
ms.openlocfilehash: fc1423e92b9dde26b7f6123cae23f1ea4f671fbd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97288483"
---
# <a name="use-rule-sets-to-specify-the-c-rules-to-run"></a>Çalıştırılacak C++ Kurallarını Belirtmek için Kural Kümeleri Kullanma

Visual Studio 'da, kod analizi ile ilişkili belirli proje ihtiyaçlarını karşılamak için özel bir *kural kümesi* oluşturabilir ve değiştirebilirsiniz. Varsayılan kural kümeleri içinde depolanır *`%VSINSTALLDIR%\Team Tools\Static Analysis Tools\Rule Sets`* .

**Visual Studio 2017 sürüm 15,7 ve üzeri:** Herhangi bir metin düzenleyicisini kullanarak özel kural kümeleri oluşturabilir ve bunu, hangi yapı sistemini kullandığınıza bağımsız olarak komut satırı yapılarına uygulayabilirsiniz. Daha fazla bilgi için bkz. [`/analyze:ruleset`](../build/reference/analyze-code-analysis.md).

Visual Studio 'da özel bir C++ kural kümesi oluşturmak için Visual Studio IDE 'de bir C/C++ projesi açık olmalıdır. Daha sonra kural kümesi düzenleyicisinde bir standart kural kümesi açıp, belirli kuralları ekleyip kaldırarak ve isteğe bağlı olarak, kod analizi bir kuralın ihlal edildiğini belirlediğinde oluşan eylemi değiştirirsiniz.

Yeni bir özel kural kümesi oluşturmak için yeni bir dosya adı kullanarak bu dosyayı kaydedersiniz. Özel kural kümesi projeye otomatik olarak atanır.

## <a name="to-create-a-custom-rule-from-a-single-existing-rule-set"></a>Tek bir var olan kural kümesinden özel bir kural oluşturmak için

::: moniker range="<=msvc-150"

1. Çözüm Gezgini ' de, proje için kısayol menüsünü açın ve ardından **Özellikler**' i seçin.

1. **Özellik sayfaları** iletişim kutusunda **yapılandırma özellikleri** > **Kod Analizi** > **genel** özellik sayfasını seçin.

1. **Kural kümesi** açılan listesinde aşağıdakilerden birini yapın:

   - Özelleştirmek istediğiniz kural kümesini seçin.

     \- veya

   - **\<Browse...>** Listede olmayan var olan bir kural kümesini belirtmeyi seçin.

1. Kural kümesi düzenleyicisinde kuralları göstermek için **Aç** ' ı seçin.

::: moniker-end
::: moniker range=">=msvc-160"

1. Çözüm Gezgini ' de, proje için kısayol menüsünü açın ve ardından **Özellikler**' i seçin.

1. **Özellik sayfaları** iletişim kutusunda **yapılandırma özellikleri** > **Kod Analizi** > **Microsoft** özellik sayfasını seçin.

1. **Etkin kurallar** açılan listesinde aşağıdakilerden birini yapın:

   - Özelleştirmek istediğiniz kural kümesini seçin.

     \- veya

   - **\<Browse...>** Listede olmayan var olan bir kural kümesini belirtmeyi seçin.

1. Kural kümesi düzenleyicisinde kuralları göstermek için **Aç** ' ı seçin.

::: moniker-end

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

- Kuralların gruplandırıldığı alanı değiştirmek için **Gruplandırma ölçütü** listesinden alanı seçin. Gruplandırılmamış kuralları göstermek için öğesini seçin **\<None>** .

- Kural sütunlarındaki alanları eklemek veya kaldırmak için **sütun seçenekleri**' yi seçin.

- Geçerli çözüm için geçerli olmayan kuralları gizlemek için **geçerli çözüm için geçerli olmayan kuralları gizle**' yi seçin.

- Hata eyleminin atandığı kuralları gösterme ve gizleme arasında geçiş yapmak için, **Kod Analizi hataları oluşturabilen kuralları göster**' i seçin.

- Uyarı eyleminin atandığı kuralları gösterme ve gizleme arasında geçiş yapmak için, **Kod Analizi uyarıları oluşturabilen kuralları göster**' i seçin.

- **Hiçbiri** eyleminin atandığı kuralları gösterme ve gizleme arasında geçiş yapmak için, **etkin olmayan kuralları göster**' i seçin.

- Geçerli kural kümesine Microsoft varsayılan kural kümelerini eklemek veya kaldırmak için **alt kural kümelerini Ekle veya Kaldır**' ı seçin.

## <a name="to-create-a-rule-set-in-a-text-editor"></a>Bir metin düzenleyicisinde bir kural kümesi oluşturmak için

Bir metin düzenleyicisinde özel bir kural kümesi oluşturabilir, bunu bir uzantıya sahip herhangi bir yerde saklayabilir *`.ruleset`* ve [`/analyze:ruleset`](../build/reference/analyze-code-analysis.md) derleyici seçeneğiyle uygulayabilirsiniz.

Aşağıdaki örnek, başlangıç noktası olarak kullanabileceğiniz temel bir kural kümesi dosyasını gösterir:

```xml
<?xml version="1.0" encoding="utf-8"?>
<RuleSet Name="New Rule Set" Description="New rules to apply." ToolsVersion="10.0">
  <Rules AnalyzerId="Microsoft.Analyzers.NativeCodeAnalysis" RuleNamespace="Microsoft.Rules.Native">
    <Rule Id="C6001" Action="Warning" />
    <Rule Id="C26494" Action="Warning" />
  </Rules>
</RuleSet>
```

## <a name="ruleset-schema"></a>RuleSet şeması

Aşağıdaki RuleSet şeması bir RuleSet dosyasının XML şemasını açıklar. RuleSet şeması içinde depolanır *`%VSINSTALLDIR%\Team Tools\Static Analysis Tools\Schemas\RuleSet.xsd`* . Kendi kural kümelerinizi programlama yoluyla yazmak veya özel RuleSets 'in doğru biçime bağlı olup olmadığını doğrulamak için bunu kullanabilirsiniz. Daha fazla bilgi için bkz. [nasıl yapılır: xsd şemasını temel alan XML belgesi oluşturma](/visualstudio/xml-tools/how-to-create-an-xml-document-based-on-an-xsd-schema).

```xml
<?xml version="1.0" encoding="utf-8"?>
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema">

  <xs:annotation>
    <xs:documentation xml:lang="en">
            Visual Studio Code Analysis Rule Set Schema Definition Language.
            Copyright (c) Microsoft Corporation. All rights reserved.
        </xs:documentation>
  </xs:annotation>

  <!-- Every time this file changes, be sure to change the Validate method for the corresponding object in the code -->

  <xs:element name="RuleSet" type="TRuleSet">
  </xs:element>

  <xs:complexType name="TLocalization">
    <xs:all>
      <xs:element name="Name" type="TName" minOccurs="0" maxOccurs="1" />
      <xs:element name="Description" type="TDescription" minOccurs="0" maxOccurs="1" />
    </xs:all>
    <xs:attribute name="ResourceAssembly" type="TNonEmptyString" use="required" />
    <xs:attribute name="ResourceBaseName" type="TNonEmptyString" use="required" />
  </xs:complexType>

  <xs:complexType name="TRuleHintPaths">
    <xs:sequence>
      <xs:element name="Path" type="TNonEmptyString" minOccurs="0" maxOccurs="unbounded" />
    </xs:sequence>
  </xs:complexType>
  
  <xs:complexType name="TName">
    <xs:attribute name="Resource" type="TNonEmptyString" use="required" />
  </xs:complexType>

  <xs:complexType name="TDescription">
    <xs:attribute name="Resource" type="TNonEmptyString" use="required" />
  </xs:complexType>

  <xs:complexType name="TInclude">
    <xs:attribute name="Path" type="TNonEmptyString" use="required" />
    <xs:attribute name="Action" type="TIncludeAction" use="required" />
  </xs:complexType>

  <xs:complexType name="TIncludeAll">
    <xs:attribute name="Action" type="TIncludeAllAction" use="required" />
  </xs:complexType>

  <xs:complexType name="TRule">
    <xs:attribute name="Id" type="TNonEmptyString" use="required" />
    <xs:attribute name="Action" type="TRuleAction" use="required" />
  </xs:complexType>

  <xs:complexType name="TRules">
    <xs:sequence>
      <xs:element name="Rule" type="TRule" minOccurs="0" maxOccurs="unbounded" />
    </xs:sequence>
    <xs:attribute name="AnalyzerId" type="TNonEmptyString" use="required" />
    <xs:attribute name="RuleNamespace" type="TNonEmptyString" use="required" />
  </xs:complexType>

  <xs:complexType name="TRuleSet">
    <xs:sequence minOccurs="0" maxOccurs="1">
      <xs:element name="Localization" type="TLocalization" minOccurs="0" maxOccurs="1" />
      <xs:element name="RuleHintPaths" type="TRuleHintPaths" minOccurs="0" maxOccurs="1" />
      <xs:element name="IncludeAll" type="TIncludeAll" minOccurs="0" maxOccurs="1" />
      <xs:choice minOccurs="0" maxOccurs="unbounded">
        <xs:element name="Include" type="TInclude" minOccurs="0" maxOccurs="unbounded" />
        <xs:element name="Rules" type="TRules" minOccurs="0" maxOccurs="unbounded">
          <xs:unique name="UniqueRuleName">
            <xs:selector xpath="Rule" />
            <xs:field xpath="@Id" />
          </xs:unique>
        </xs:element>
      </xs:choice>
    </xs:sequence>
    <xs:attribute name="Name" type="TNonEmptyString" use="required" />
    <xs:attribute name="Description" type="xs:string" use="optional" />
    <xs:attribute name="ToolsVersion" type="TNonEmptyString" use="required" />
  </xs:complexType>

  <xs:simpleType name="TRuleAction">
    <xs:restriction base="xs:string">
      <xs:enumeration value="Error"/>
      <xs:enumeration value="Warning"/>
      <xs:enumeration value="Info"/>
      <xs:enumeration value="Hidden"/>
      <xs:enumeration value="None"/>
    </xs:restriction>
  </xs:simpleType>

  <xs:simpleType name="TIncludeAction">
    <xs:restriction base="xs:string">
      <xs:enumeration value="Error"/>
      <xs:enumeration value="Warning"/>
      <xs:enumeration value="Info"/>
      <xs:enumeration value="Hidden"/>
      <xs:enumeration value="None"/>
      <xs:enumeration value="Default"/>
    </xs:restriction>
  </xs:simpleType>

  <xs:simpleType name="TIncludeAllAction">
    <xs:restriction base="xs:string">
      <xs:enumeration value="Error"/>
      <xs:enumeration value="Warning"/>
      <xs:enumeration value="Info"/>
      <xs:enumeration value="Hidden"/>
    </xs:restriction>
  </xs:simpleType>

  <xs:simpleType name="TNonEmptyString">
    <xs:restriction base="xs:string">
      <xs:minLength value="1" />
    </xs:restriction>
  </xs:simpleType>
  
</xs:schema>

```

Şema öğesi ayrıntıları:

| Şema öğesi | Açıklama |
|--------------------|--------------|
| `TLocalization` | RuleSet dosyasının adı, RuleSet dosyasının açıklaması, yerelleştirilmiş kaynağı içeren kaynak derlemesinin adı ve yerelleştirilmiş kaynağın temel adı dahil olmak üzere yerelleştirme bilgileri |
| `TRuleHintPaths` | Kural kümesi dosyalarını aramak için ipuçları olarak kullanılan dosya yolları |
| `TName` | Geçerli RuleSet dosyasının adı |
| `TDescription` | Geçerli RuleSet dosyasının açıklaması |
| `TInclude` | Kural eylemiyle dahil edilen bir RuleSet 'in yolu |
| `TIncludeAll` | Tüm kurallar için kural eylemi |
| `TRule` | Kural KIMLIĞI, kural eylemi |
| `TRules` | Bir veya daha fazla kural koleksiyonu |
| `TRuleSet` | Kural ipucu yollarından oluşan ruleset dosya biçimi, tüm bilgileri, içerme bilgilerini, kural bilgilerini, ad, açıklama ve Araçlar sürüm bilgilerini içerir |
| `TRuleAction` | Hata, uyarı, bilgi, gizli veya hiçbiri gibi bir kural eylemini açıklayan sabit listesi |
| `TIncludeAction` | Hata, uyarı, bilgi, gizli, yok veya varsayılan gibi bir kural eylemini açıklayan sabit listesi |
| `TIncludeAllAction` | Hata, uyarı, bilgi veya gizli gibi bir kural eylemini açıklayan sabit listesi |

Bir RuleSet örneğine bir örnek görmek için bkz. [bir metin düzenleyicisinde bir kural kümesi oluşturmak için](#to-create-a-rule-set-in-a-text-editor)veya içinde depolanan varsayılan RuleSets 'ler `%VSINSTALLDIR%\Team Tools\Static Analysis Tools\Rule Sets` .
