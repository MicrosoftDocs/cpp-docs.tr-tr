---
title: Özellik sayfası XML kuralı dosyaları
ms.date: 05/06/2019
helpviewer_keywords:
- property page XML files
ms.assetid: dd9d9734-4387-4098-8ba6-85b93507731d
ms.openlocfilehash: 76378dc5ef9d7443045c329579cfa3c410dc262f
ms.sourcegitcommit: 9d4ffb8e6e0d70520a1e1a77805785878d445b8a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/20/2019
ms.locfileid: "69630749"
---
# <a name="property-page-xml-rule-files"></a>Özellik sayfası XML kuralı dosyaları

IDE 'deki proje özelliği sayfaları, VCTargets klasöründeki XML dosyaları tarafından yapılandırılır. Tam yol, Visual Studio 'nun hangi sürümüne ve ürün diline bağlı olarak değişir. Visual Studio 2019 Enterprise Edition için, Ingilizce 'de yol olur `%ProgramFiles%\Microsoft Visual Studio\2019\Enterprise\Common7\IDE\VC\VCTargets\1033`. XML dosyaları kuralların adlarını, kategorileri ve bireysel özelliklerini, veri türlerini, varsayılan değerlerini ve bunların nasıl görüntüleneceğini açıklamaktadır. IDE 'de bir özelliği ayarladığınızda, yeni değer proje dosyasında depolanır.

Bu dosyaların iç işleyişini anlamanız gereken tek senaryolar ve Visual Studio IDE, (a) özel bir özellik sayfası oluşturmak istediğiniz veya (b), Visual Studio IDE 'den farklı bazı yollarla proje özelliklerinizi özelleştirmek istiyorsunuz.

İlk olarak, bir projenin özellik sayfalarını açalım ( **Çözüm Gezgini** ' de proje düğümüne sağ tıklayıp Özellikler ' i seçin):

![Visual Studio C++ proje özellikleri](../media/cpp-property-page-2017.png)

**Yapılandırma özellikleri** altındaki her düğüme bir kural denir. Bir kural bazen derleyici gibi tek bir aracı temsil eder, ancak genel olarak terim, çalıştırılan ve bazı çıktıları oluşturabilecek özellikleri olan bir şeye başvurur. Her kural VCTargets klasöründeki bir XML dosyasından doldurulur. Örneğin, yukarıda gösterilen C/C++ kuralı ' CL. xml ' tarafından doldurulur.

Yukarıda gösterildiği gibi, her kuralın kategoriler halinde düzenlenmiş bir özellikler kümesi vardır. Bir kural altındaki her alt düğüm bir kategoriyi temsil eder. Örneğin, C/C++ altındaki iyileştirme düğümü, derleyici aracının en iyi duruma getirme özelliklerini içerir. Özellikler ve değerleri, sağ bölmedeki kılavuz biçiminde işlenir.

CL. xml dosyasını Not defteri 'nde veya herhangi bir XML düzenleyicisinde açabilirsiniz (aşağıdaki anlık görüntüye bakın). Kullanıcı arabiriminde, ek meta verilerle birlikte, altında tanımlı özellikler listesi olan kural adlı bir kök düğüm görürsünüz.

```xml
<?xml version="1.0" encoding="utf-8"?>
<!--Copyright, Microsoft Corporation, All rights reserved.-->
<Rule Name="CL" PageTemplate="tool" DisplayName="C/C++" SwitchPrefix="/" Order="10" xmlns="http://schemas.microsoft.com/build/2009/properties" xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml" xmlns:sys="clr-namespace:System;assembly=mscorlib">
  <Rule.Categories>
    <Category Name="General" DisplayName="General" />
    <Category Name="Optimization" DisplayName="Optimization" />
    <Category Name="Preprocessor" DisplayName="Preprocessor" />
    <Category Name="Code Generation" DisplayName="Code Generation" />
    <Category Name="Language" DisplayName="Language" />
    <Category Name="Precompiled Headers" DisplayName="Precompiled Headers" />
    <Category Name="Output Files" DisplayName="Output Files" />
    <Category Name="Browse Information" DisplayName="Browse Information" />
    <Category Name="Advanced" DisplayName="Advanced" />
    <Category Name="All Options" DisplayName="All Options" Subtype="Search" />
    <Category Name="Command Line" DisplayName="Command Line" Subtype="CommandLine" />
  </Rule.Categories>
...
```

Özellik sayfaları kullanıcı arabirimindeki yapılandırma özellikleri altındaki her düğüme karşılık gelen bir XML dosyası vardır. Projedeki ilgili XML dosyalarına konum ekleyerek veya kaldırarak Kullanıcı arabirimindeki kuralları ekleyebilir veya kaldırabilirsiniz. Örneğin, Microsoft. CppBuild. targets (1033 klasöründen bir düzey) CL. xml ' yi içerir:

```xml
<PropertyPageSchema Condition="'$(ConfigurationType)' != 'Utility'" Include="$(VCTargetsPath)$(LangID)\cl.xml"/>
```

Tüm verilerin CL. xml ' yi Strip, aşağıdaki iskelet ile sona erdirmek için şunları yapmanız gerekir:

```xml
<?xml version="1.0" encoding="utf-8"?>
<Rule>
  <Rule.DataSource />
  <Rule.Categories>
    <Category />
        ...
  </Rule.Categories>
  <BoolProperty />
  <EnumProperty />
  <IntProperty />
  <StringProperty />
  <StringListProperty />
</Rule>
```

Aşağıdaki bölümde, her önemli öğe ve bunlara iliştirilebilecek bazı meta veriler açıklanmaktadır.

1. **Kurallar**  Kural genellikle XML dosyasındaki kök düğümdür; birçok özniteliğe sahip olabilir:

    ```xml
    <Rule Name="CL" PageTemplate="tool" SwitchPrefix="/" Order="10"
              xmlns="http://schemas.microsoft.com/build/2009/properties"
              xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
              xmlns:sys="clr-namespace:System;assembly=mscorlib">
      <Rule.DisplayName>
        <sys:String>C/C++</sys:String>
      </Rule.DisplayName>
    ```

   a. **Ada** Name özniteliği kural için bir kimliğidir. Projenin tüm özellik sayfası XML dosyaları arasında benzersiz olması gerekir.

   b. **PageTemplate:** Bu özniteliğin değeri kullanıcı ARABIRIMI tarafından Kullanıcı arabirimi şablonları koleksiyonundan seçim yapmak için kullanılır. "Araç" şablonu, özellikleri standart kılavuz biçiminde işler. Bu öznitelik için diğer yerleşik değerler "Debugger" ve "Generic" dir. Bu değerleri belirtmekten kaynaklanan Kullanıcı arabirimi biçimini görmek için sırasıyla hata ayıklama düğümüne ve genel düğümüne bakın. "Hata ayıklayıcı" sayfa şablonu için Kullanıcı arabirimi, farklı hata ayıklayıcıların özellikleri arasında geçiş yapmak için bir açılır kutu kullanır, ancak "genel" şablon farklı özellik kategorilerini bir sayfada birden çok kategori alt düğümüne sahip olmanın aksine tek bir sayfada görüntüler düğümüne. Bu öznitelik yalnızca Kullanıcı arabirimine yönelik bir öneridir; XML dosyası, Kullanıcı arabirimine bağımsız olacak şekilde tasarlanmıştır. Farklı bir kullanıcı arabirimi bu özniteliği farklı amaçlar için kullanabilir.

   c. **Anahtar öneki:** Bu, anahtarlar için komut satırında kullanılan önekidir. "/" Değeri/ZI,/nologo,/W3 vb. gibi görünen anahtarlara neden olur.

   d. **Siparişi** Bu, sistemdeki diğer kurallara kıyasla bu kuralın göreli konumundaki olası bir kullanıcı arabirimi istemcisine yönelik bir öneridir.

   e. **özniteliði** Bu, standart bir XAML öğesidir. Listelenen üç ad alanını görebilirsiniz. Bunlar, sırasıyla XAML seri kaldırma sınıfları, XAML şeması ve sistem ad alanları için ad alanlarına karşılık gelir.

   f. **DisplayName** Bu, kural düğümü için özellik sayfası kullanıcı arabiriminde gösterilen addır. Bu değer yerelleştirilmiştir. DisplayName, iç yerelleştirme aracı gereksinimleri nedeniyle bir öznitelik (ad veya SwitchPrefix gibi) yerine kuralın alt öğesi olarak oluşturulmuştur. XAML perspektifinden, her ikisi de eşdeğerdir. Bu nedenle, yalnızca dağınıklığı azaltmak veya olduğu gibi bırakmak için bir özniteliği yapabilirsiniz.

   g. **DataSource** Bu çok önemli bir özelliktir ve bu, proje sistemine özellik değerinin hangi konuma okunduğunu ve yazıldığını ve gruplandırılmasının (aşağıda açıklanmıştır) olduğunu söyler. CL. xml için bu değerler şunlardır:

      ```xml
      <DataSource Persistence="ProjectFile" ItemType="ClCompile" Label="" HasConfigurationCondition="true" />
      ```

   - `Persistence="ProjectFile`Proje sistemine kural için tüm özelliklerin proje dosyasına veya özellik sayfası dosyasına (özellik sayfalarını oluşturma için kullanılan düğüme bağlı olarak) yazılmasını söyler. Diğer olası değer,. User dosyasına değeri yazacak olan "UserFile" değeridir.

   - `ItemType="ClCompile"`özelliklerin, bu öğe türünün ItemDefinition meta verileri veya öğe meta verileri (yalnızca Çözüm Gezgini 'nde bir dosya düğümünden üretildiğinde) olarak depolandığını belirtir. Bu alan ayarlanmamışsa, özellik bir PropertyGroup içinde ortak bir özellik olarak yazılır.

   - `Label=""`Özellikler meta veri olarak `ItemDefinition` yazıldığında, ana ItemDefinitionGroup 'un etiketinin boş olacağını gösterir (her MSBuild öğesinin bir etiketi olabilir). Visual Studio 2017 ve üzeri,. vcxproj proje dosyasında gezinmek için etiketlenmiş grupları kullanır. Kural özelliklerinin çoğunu içeren grupların etiket olarak boş bir dize olduğunu unutmayın.

   - `HasConfigurationCondition="true"`proje sisteminin, yalnızca geçerli proje yapılandırması için etkili olması için bir yapılandırma koşulunu değere yapıştırmasını söyler (koşul, üst gruba veya değerin kendisine yapıştırılmış olabilir). Örneğin, proje düğümündeki özellik sayfalarını açın ve özellik değerini, **yapılandırma özellikleri > CC++ /genel** ' i "Evet" olarak ayarlayın. Aşağıdaki değer proje dosyasına yazılır. Yapılandırma koşulunun ana ItemDefinitionGroup grubuna iliştirildiğine dikkat edin.

      ```xml
      <ItemDefinitionGroup Condition="‘$(Configuration)|$(Platform)’==’Debug|Win32’">
        <ClCompile>
          <TreatWarningAsError>true</TreatWarningAsError>
        </ClCompile>
      </ItemDefinitionGroup>
      ```

      Bu değer, stbafx. cpp gibi belirli bir dosya için özellik sayfasında ayarlandıysa, özellik değeri aşağıda gösterildiği gibi proje dosyasındaki *stdadfx. cpp* öğesi altına yazılır. Yapılandırma koşulunun doğrudan meta verilere nasıl iliştirildiğine dikkat edin.

      ```xml
      <ItemGroup>
        <ClCompile Include="stdafx.cpp">
          <TreatWarningAsError Condition="‘$(Configuration)|$(Platform)’==’Debug|Win32’">true</TreatWarningAsError>
        </ClCompile>
      </ItemGroup>
      ```

   Yukarıda listelenmeyen bir **veri kaynağı** özniteliği **PersistedName**. Bu özniteliği, farklı bir ad kullanarak proje dosyasındaki bir özelliği göstermek için kullanabilirsiniz. Varsayılan olarak, bu öznitelik özelliğin **adına**ayarlanır.

   Tek bir özellik, üst kuralının veri kaynağını geçersiz kılabilir. Bu durumda, bu özelliğin değerinin konumu kuraldaki diğer özelliklerden farklı olacaktır.

   h. Burada görünmeyen Description ve Supportsfilebatch dahil olmak üzere bir kuralın diğer öznitelikleri vardır. Bir kurala veya diğer herhangi bir öğeye uygulanabilen özniteliklerin tam kümesi, bu türler için belgelere göz atarak elde edilebilir. Alternatif olarak, `Microsoft.Build.Framework.XamlTypes` `Microsoft.Build.Framework .dll` derlemede bulunan ad alanındaki türler üzerinde ortak özellikleri inceleyebilirsiniz.

   i. **DisplayName**, **PageTemplate**ve **Order** , bu durumda UI ile bağımsız veri modelinde bulunan UI ile ilgili özelliklerdir. Bu özellikler, özellik sayfalarını göstermek için kullanılan herhangi bir kullanıcı arabirimi tarafından kullanılmak üzere neredeyse belli olur. **DisplayName** ve **Description** , XML dosyasındaki neredeyse tüm öğelerde bulunan iki özelliklerdir. Bunlar, yerelleştirilmiş olan tek iki özelliklerdir (Bu dizelerin yerelleştirilmesi sonraki bir göndermede açıklanacaktır).

1. **Alan** Bir kuralda birden fazla kategori olabilir. Kategorilerin XML dosyasında listelenme sırası, kategorilerin aynı sırada görüntülenmesi için Kullanıcı arabirimine yönelik bir öneridir. Örneğin, UI – genel, Iyileştirme, Önişlemci,..C++ . içinde görüldüğü gibi, C/düğümü altındaki kategorilerin sırası.  –, CL. xml ' deki ile aynıdır. Örnek kategori şöyle görünür:

    ```xml
    <Category Name="Optimization">
      <Category.DisplayName>
        <sys:String>Optimization</sys:String>
      </Category.DisplayName>
    </Category>
    ```

   Yukarıdaki kod parçacığı, daha önce açıklanan **adı** ve **DisplayName** özniteliklerini gösterir. Bir kez daha, bir **kategorinin** yukarıda kullanılmamış olması için başka öznitelikler de vardır. Belgeleri okuyarak veya ıldadsm. exe ' yi kullanarak derlemeleri inceleyerek, bu bilgileri bilirsiniz.

1. **Özelliklerinin** Bu, XML dosyasının et ve bu kuraldaki tüm özelliklerin listesini içerir. Her özellik, Yukarıdaki XAML iskelet 'de gösterilen beş olası türden biri olabilir. Kuşkusuz, dosyanızda bu türlerden yalnızca birkaçı olabilir. Bir özellik, zengin olarak açıklanacak bir dizi özniteliğe sahiptir. Burada yalnızca **StringProperty** ' I açıklayacağım. Rest çok benzerdir.

    ```xml
    <StringProperty Subtype="file" Name="ObjectFileName" Category="Output Files" Switch="Fo">
      <StringProperty.DisplayName>
        <sys:String>Object File Name</sys:String>
      </StringProperty.DisplayName>
      <StringProperty.Description>
        <sys:String>Specifies a name to override the default object file name; can be file or directory name.(/Fo[name])</sys:String>
      </StringProperty.Description>
    </StringProperty>
    ```

   Kod parçacığındaki özniteliklerin çoğu daha önce açıklanmıştır. Yeni olanlar, alt tür, kategori ve anahtardır.

   a. **Subtype** yalnızca **StringProperty** ve **StringListProperty**için kullanılabilen bir özniteliktir; bağlamsal bilgiler verir. Örneğin, "File" değeri, özelliğin bir dosya yolunu temsil ettiğini belirtir. Bu tür bağlamsal bilgiler, kullanıcının dosyayı görsel olarak seçmesini sağlayan, özelliğin Düzenleyicisi olarak bir Windows Gezgini sağlayarak düzenleme deneyimini geliştirmek için kullanılır.

   b. **Alan** Bu, bu özelliğin hangi kategoriye düştüğünü bildirir. Bu özelliği kullanıcı arabirimindeki **çıkış dosyaları** kategorisi altında bulmayı deneyin.

   c. **Değiştirebilirsiniz** Bir kural, bu durumda derleyici aracı gibi bir aracı temsil ettiğinde, kuralın çoğu özelliği derleme sırasında araç yürütülebilirine anahtar olarak geçirilir. Bu özniteliğin değeri, kullanılacak anahtar değişmez değerini belirtir. Yukarıdaki özelliği, anahtarın **Info**olması gerektiğini belirtir. Üst kuraldaki **SwitchPrefix** özniteliğiyle birlikte, bu özellik yürütülebilir **\" "hata ayıklama** (özellik sayfası kullanıcı arabiriminde CC++ için komut satırında görünür) olarak çalıştırılabilir dosyaya geçirilir.

   Diğer özellik öznitelikleri şunlardır:

   d. **Görüne** Bir nedenden dolayı, özelliğin özellik sayfalarında görünmesini istemezsiniz (ancak büyük olasılıkla yapı süresi sırasında kullanılabilir), bu özniteliği false olarak ayarlayın.

   e. **Özelliğinin** Özellik sayfalarında bu özelliğin değerinin salt okunurdur görünümünü sağlamak istiyorsanız, bu özniteliği true olarak ayarlayın.

   f. **IncludeInCommandLine:** Bazı özelliklerin derleme zamanında bir araca geçirilmesi gerekmez. Bu özniteliğin false olarak ayarlanması, geçirilmesini engeller.
