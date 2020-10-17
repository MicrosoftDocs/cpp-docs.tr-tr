---
title: Özellik sayfası XML kuralı dosyaları
description: Visual Studio IDE C++ Özellik sayfası XML kural dosyaları ve içeriği açıklaması.
ms.date: 10/14/2020
helpviewer_keywords:
- property page XML files
ms.openlocfilehash: 96cbf6a32cada2b594874493868ec884823016cb
ms.sourcegitcommit: 6e5429e076e552b32e8bdc49480c51498d7924c1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/15/2020
ms.locfileid: "92099725"
---
# <a name="property-page-xml-rule-files"></a>Özellik sayfası XML kuralı dosyaları

IDE 'deki proje özelliği sayfaları varsayılan kurallar klasöründe XML dosyaları tarafından yapılandırılır. XML dosyaları kuralların adlarını, kategorileri ve bireysel özelliklerini, veri türlerini, varsayılan değerlerini ve bunların nasıl görüntüleneceğini açıklamaktadır. IDE 'de bir özelliği ayarladığınızda, yeni değer proje dosyasında depolanır.

::: moniker range="vs-2015"

Varsayılan kurallar klasörünün yolu, kullanımdaki Visual Studio 'nun yerel ayarına ve sürümüne bağlıdır. Visual Studio 2015 veya önceki bir geliştirici komut isteminde Rules klasörü *`%ProgramFiles(x86)%\MSBuild\Microsoft.Cpp\v4.0\<version>\<locale>`* . `<version>`Değer *`v140`* Visual Studio 2015 ' dir. , `<locale>` Örneğin, İngilizce için BIR LCID 'dir `1033` . Visual Studio 'nun yüklü her sürümü için ve her dil için farklı bir yol kullanacaksınız. Örneğin, Ingilizce 'de Visual Studio 2015 Community Edition için varsayılan kurallar klasör yolu olabilir *`C:\Program Files (x86)\MSBuild\Microsoft.Cpp\v4.0\v140\1033\`* .

::: moniker-end

::: moniker range="vs-2017"

Varsayılan kurallar klasörünün yolu, kullanımdaki Visual Studio 'nun yerel ayarına ve sürümüne bağlıdır. Visual Studio 2017 Geliştirici komut isteminde Rules klasörü *`%VSINSTALLDIR%Common7\IDE\VC\VCTargets\<locale>\`* . , `<locale>` Örneğin, İngilizce için BIR LCID 'dir `1033` . Visual Studio 2015 veya önceki bir geliştirici komut isteminde, Rules klasörü, *`%ProgramFiles(x86)%\MSBuild\Microsoft.Cpp\v4.0\<version>\<locale>\`* burada `<version>` değer *`v140`* Visual Studio 2015 ' dir. Visual Studio 'nun yüklü her sürümü için ve her dil için farklı bir yol kullanacaksınız. Örneğin, Ingilizce 'de Visual Studio 2017 Community Edition için varsayılan kurallar klasör yolu olabilir *`C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\VC\VCTargets\1033\`* .

::: moniker-end

::: moniker range=">=vs-2019"

Varsayılan kurallar klasörünün yolu, kullanımdaki Visual Studio 'nun yerel ayarına ve sürümüne bağlıdır. Visual Studio 2019 veya sonraki bir geliştirici komut isteminde, Rules klasörü, *`%VSINSTALLDIR%MSBuild\Microsoft\VC\<version>\<locale>\`* burada `<version>` değer *`v160`* Visual Studio 2019 ' dir. , `<locale>` Örneğin, İngilizce için BIR LCID 'dir `1033` . Visual Studio 2017 ' de, Rules klasörü *`%VSINSTALLDIR%Common7\IDE\VC\VCTargets\<locale>\`* . Visual Studio 2015 veya önceki bir geliştirici komut isteminde Rules klasörü *`%ProgramFiles(x86)%\MSBuild\Microsoft.Cpp\v4.0\<version>\<locale>\`* . Visual Studio 'nun yüklü her sürümü için ve her dil için farklı bir yol kullanacaksınız. Örneğin, Ingilizce 'de Visual Studio 2019 Community Edition için varsayılan kurallar klasör yolu olabilir *`C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\MSBuild\Microsoft\VC\v160\1033\`* .

::: moniker-end

Yalnızca birkaç senaryoda bu dosyaların ve Visual Studio IDE 'nin iç işleyişini anlamanız gerekir:

- Özel bir özellik sayfası oluşturmak istiyorsanız veya
- Visual Studio IDE 'yi kullanmadan proje özelliklerinizi özelleştirmek istiyorsunuz.

## <a name="contents-of-rule-files"></a>Kural dosyalarının içeriği

İlk olarak, bir projenin özellik sayfalarını açalım. **Çözüm Gezgini** ' de proje düğümüne sağ tıklayın ve **Özellikler**' i seçin:

![Visual Studio C++ proje özellikleri iletişim kutusunu gösterir](../media/cpp-property-page-2017.png)

**Yapılandırma özellikleri** altındaki her düğüme bir *kural*denir. Bir kural bazen derleyici gibi tek bir aracı temsil eder. Genel olarak, terim, çalıştıran ve bazı çıktıları oluşturabilecek özellikleri olan bir şeyi ifade eder. Her kural varsayılan kurallar klasöründeki bir XML dosyasından doldurulur. Örneğin, burada gösterilen C/C++ kuralı *'cl.xml '* tarafından doldurulur.

Her kural, *Kategoriler*halinde düzenlenmiş bir dizi özellik içerir. Bir kural altındaki her alt düğüm bir kategoriyi temsil eder. Örneğin, **C/C++** altındaki **iyileştirme** düğümü, derleyici aracının en iyi duruma getirme özelliğini içerir. Özellikler ve değerleri sağ bölmedeki kılavuz biçiminde işlenir.

*`cl.xml`* Not defteri veya herhangi BIR XML düzenleyicisinde açabilirsiniz. Adlı bir kök düğüm görürsünüz `Rule` . Kullanıcı arabiriminde görüntülenen özelliklerin aynı listesini, ek meta verilerle birlikte tanımlar.

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
  <!-- . . . -->
</Rule>
```

Özellik sayfaları kullanıcı arabirimindeki **yapılandırma özellikleri** altındaki her düğüm IÇIN bir XML dosyası vardır. Kullanıcı arabirimindeki kuralları ekleyebilir veya kaldırabilirsiniz: Projedeki karşılık gelen XML dosyalarına konum ekleme veya kaldırma işlemi yapılır. Örneğin, *`Microsoft.CppBuild.targets`* (1033 klasöründen daha yüksek bir düzey bulunur) şunları içerir *`cl.xml`* :

```xml
<PropertyPageSchema Condition="'$(ConfigurationType)' != 'Utility'" Include="$(VCTargetsPath)$(LangID)\cl.xml"/>
```

*`cl.xml`* Tüm verilerin şeridine sahipseniz, bu temel çatıya sahipsiniz:

```xml
<?xml version="1.0" encoding="utf-8"?>
<Rule>
  <Rule.DataSource />
  <Rule.Categories>
    <Category />
    <!-- . . . -->
  </Rule.Categories>
  <BoolProperty />
  <EnumProperty />
  <IntProperty />
  <StringProperty />
  <StringListProperty />
</Rule>
```

Sonraki bölümde, iliştirebilmeniz için her bir ana öğe ve bazı meta veriler açıklanmaktadır.

### <a name="rule-attributes"></a>Kural öznitelikleri

**`<Rule>`** Öğesi, XML dosyasındaki kök düğümdür. Birçok özniteliğe sahip olabilir:

```xml
<Rule Name="CL" PageTemplate="tool" SwitchPrefix="/" Order="10"
          xmlns="http://schemas.microsoft.com/build/2009/properties"
          xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
          xmlns:sys="clr-namespace:System;assembly=mscorlib">
  <Rule.DisplayName>
    <sys:String>C/C++</sys:String>
  </Rule.DisplayName>
```

- **`Name`**: Ad özniteliği, için bir KIMLIĞIDIR `Rule` . Projenin tüm özellik sayfası XML dosyaları arasında benzersiz olması gerekir.

- **`PageTemplate`**: Bu özniteliğin değeri kullanıcı arabirimi tarafından Kullanıcı arabirimi şablonları koleksiyonundan seçim yapmak için kullanılır. "Araç" şablonu, özellikleri standart kılavuz biçiminde işler. Bu öznitelik için diğer yerleşik değerler "Debugger" ve "Generic" dir. Bu değerleri belirtmekten kaynaklanan Kullanıcı arabirimi biçimini görmek için sırasıyla hata ayıklama düğümüne ve genel düğümüne bakın. "Hata ayıklayıcı" sayfa şablonu için Kullanıcı arabirimi, farklı hata ayıklayıcıların özellikleri arasında geçiş yapmak için bir açılan kutu kullanır. "Genel" şablon, düğüm altında birden çok kategori alt düğümüne sahip olmanın aksine, farklı özellik kategorilerini tek bir sayfada görüntüler `Rule` . Bu öznitelik yalnızca Kullanıcı arabirimine yönelik bir öneridir. XML dosyası, Kullanıcı arabirimine bağımsız olacak şekilde tasarlanmıştır. Farklı bir kullanıcı arabirimi bu özniteliği farklı amaçlar için kullanabilir.

- **`SwitchPrefix`**: Anahtarlar için komut satırında kullanılan önek. Bir değeri,,, vb `"/"` . gibi görünen anahtarlara neden olur **`/ZI`** **`/nologo`** **`/W3`** .

- **`Order`**: Bu, `Rule` sistemdeki diğer tüm kurallara kıyasla bunun göreli konumundaki olası bir kullanıcı arabirimi istemcisine yönelik bir öneridir.

- **`xmlns`**: Standart bir XML öğesi. Listelenen üç ad alanını görebilirsiniz. Bu öznitelikler, sırasıyla XML seri kaldırma sınıfları, XML şeması ve sistem ad alanları için ad alanlarına karşılık gelir.

- **`DisplayName`**: Düğüm için özellik sayfası kullanıcı arabiriminde gösterilen ad `Rule` . Bu değer yerelleştirilmiştir. `DisplayName` `Rule` `Name` `SwitchPrefix` İç yerelleştirme aracı gereksinimleri nedeniyle bir öznitelik (veya gibi) yerine bir alt öğesi olarak oluşturuluyoruz. XML perspektifinden her ikisi de eşdeğerdir. Bu nedenle, yalnızca dağınıklığı azaltmak veya olduğu gibi bırakmak için bir özniteliği yapabilirsiniz.

- **`DataSource`**: Bu önemli özellik proje sistemine, özellik değerini ve gruplandırmasını (daha sonra açıklanacak) okuyup yazmayacağını söyler. İçin *`cl.xml`* , bu değerler şunlardır:

    ```xml
    <DataSource Persistence="ProjectFile" ItemType="ClCompile" Label="" HasConfigurationCondition="true" />
    ```

  - `Persistence="ProjectFile"` Proje sistemine, için tüm özelliklerin `Rule` proje dosyasına veya özellik sayfası dosyasına (özellik sayfalarını oluşturma için kullanılan düğüme bağlı olarak) yazılmasını söyler. Diğer olası değer, `"UserFile"` Bu değeri *`.user`* dosyasına yazacak.

  - `ItemType="ClCompile"` özelliklerin, bu öğe türünün ItemDefinition meta verileri veya öğe meta verileri (yalnızca Çözüm Gezgini 'nde bir dosya düğümünden üretildiğinde) olarak depolandığını belirtir. Bu alan ayarlanmamışsa, özellik bir PropertyGroup içinde ortak bir özellik olarak yazılır.

  - `Label=""` Özellikler `ItemDefinition` meta veri olarak yazıldığında, ana ItemDefinitionGroup 'un etiketinin boş olacağını gösterir (her MSBuild öğesinin bir etiketi olabilir). Visual Studio 2017 ve üzeri,. vcxproj proje dosyasında gezinmek için etiketlenmiş grupları kullanır. Çoğu özelliği içeren grupların `Rule` etiket olarak boş bir dizesi vardır.

  - `HasConfigurationCondition="true"` proje sisteminin, yalnızca geçerli proje yapılandırması için etkili olması için bir yapılandırma koşulunu değere yapıştırmasını söyler (koşul, üst gruba veya değerin kendisine yapıştırılmış olabilir). Örneğin, proje düğümündeki özellik sayfalarını açın ve özellik değerini, **yapılandırma özellikleri > C/C++ genel** ' i "Evet **" olarak ayarlayın** . Aşağıdaki değer proje dosyasına yazılır. Yapılandırma koşulunun ana ItemDefinitionGroup grubuna iliştirildiğine dikkat edin.

    ```xml
    <ItemDefinitionGroup Condition="'$(Configuration)|$(Platform)'=='Debug|Win32'">
      <ClCompile>
        <TreatWarningAsError>true</TreatWarningAsError>
      </ClCompile>
    </ItemDefinitionGroup>
    ```

     Bu değer, gibi belirli bir dosya için özellik sayfasında ayarlandıysa *`stdafx.cpp`* , özellik değeri `stdafx.cpp` burada gösterildiği gibi proje dosyasındaki öğenin altına yazılmalıdır. Yapılandırma koşulunun meta verilere doğrudan nasıl iliştirildiğine dikkat edin:

    ```xml
    <ItemGroup>
      <ClCompile Include="stdafx.cpp">
        <TreatWarningAsError Condition="'$(Configuration)|$(Platform)'=='Debug|Win32'">true</TreatWarningAsError>
      </ClCompile>
    </ItemGroup>
    ```

  Burada listelenmeyen başka bir özniteliği `DataSource` aşağıda verilmiştir `PersistedName` . Bu özniteliği, farklı bir ad kullanarak proje dosyasındaki bir özelliği göstermek için kullanabilirsiniz. Varsayılan olarak, bu öznitelik özelliği olarak ayarlanır `Name` .

  Bireysel bir özellik, `DataSource` üst öğesinin öğesini geçersiz kılabilir `Rule` . Bu durumda, bu özelliğin değerinin konumu içindeki diğer özelliklerden farklı olacaktır `Rule` .

- `Rule`Burada görüntülenmeyen ve dahil olmak üzere başka bir öznitelikleri vardır `Description` `SupportsFileBatching` . Herhangi bir veya başka bir öğe üzerinde geçerli olan özniteliklerin tam kümesi, `Rule` Bu türler için belgelere göz atarak elde edilebilir. Alternatif olarak, derlemede bulunan ad alanındaki türler üzerinde ortak özellikleri inceleyebilirsiniz `Microsoft.Build.Framework.XamlTypes` `Microsoft.Build.Framework.dll` .

- **`DisplayName`**, **`PageTemplate`** ve, **`Order`** Bu durumda UI ile bağımsız veri MODELINDE bulunan UI ile ilgili özelliklerdir. Bu özellikler, özellik sayfalarını göstermek için kullanılan herhangi bir kullanıcı arabirimi tarafından kullanılmak üzere neredeyse belli olur. `DisplayName` ve `Description` , XML dosyasındaki neredeyse tüm öğelerde bulunan iki özelliklerdir. Bu iki özellik de yerelleştirilmiş tek alanlardır.

### <a name="category-elements"></a>Kategori öğeleri

`Rule`Öğesinin birden çok `Category` öğesi olabilir. Kategorilerin XML dosyasında listelenme sırası, kategorilerin aynı sırada görüntülenmesi için Kullanıcı arabirimine yönelik bir öneridir. Örneğin, Kullanıcı arabiriminde gördüğünüz **C/C++** düğümünün altındaki kategorilerin sırası, içindeki sırasıyla aynı olur *`cl.xml`* . Örnek kategori şöyle görünür:

```xml
<Category Name="Optimization">
  <Category.DisplayName>
    <sys:String>Optimization</sys:String>
  </Category.DisplayName>
</Category>
```

Bu kod parçacığı, `Name` daha `DisplayName` önce açıklanan ve özniteliklerini gösterir. Bir kez daha, örnekte gösterilmeyen başka öznitelikler de vardır `Category` . Belgeleri okuyarak veya kullanarak derlemeleri inceleyerek hakkında bilgi edinebilirsiniz *`ildasm.exe`* .

### <a name="property-elements"></a>Özellik öğeleri

Kural dosyasının çoğu `Property` öğelerinden oluşur. İçindeki tüm özelliklerin listesini içerirler `Rule` . Her özellik temel çerçevede gösterilen beş olası türden biri olabilir: `BoolProperty` , `EnumProperty` ,, `IntProperty` `StringProperty` ve `StringListProperty` . Dosyanızda bu türlerden yalnızca birkaçı olabilir. Bir özellik, ayrıntılı olarak açıklanacak bir dizi özniteliğe sahiptir. `StringProperty`Burada açıklanmıştır. Rest benzerdir.

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

Kod parçacığındaki özniteliklerin çoğu daha önce açıklanmıştır. Yeni olanlar `Subtype` , ve ' dir `Category` `Switch` .

- **`Subtype`** yalnızca ve öğeleri için kullanılabilen bir `StringProperty` özniteliktir `StringListProperty` . Bağlamsal bilgiler verir. Örneğin, değer, `file` özelliğin bir dosya yolunu temsil ettiğini gösterir. Visual Studio, bu tür bağlamsal bilgileri, düzen deneyimini geliştirmek için kullanır. Örneğin, kullanıcının özelliğin Düzenleyicisi olarak dosyayı görsel olarak seçmesini sağlayan bir Windows Explorer penceresi sağlayabilir.

- **`Category`**: Bu özelliğin bulunduğu kategori. Bu özelliği kullanıcı arabirimindeki **çıkış dosyaları** kategorisi altında bulmayı deneyin.

- **`Switch`**: Bir kural derleyici aracı gibi bir aracı temsil ettiğinde, çoğu `Rule` özellik yapı zamanında araç yürütülebilir dosyasına anahtar olarak geçirilir. Bu özniteliğin değeri, hangi anahtar değişmez değerini kullanacağını gösterir. `<StringProperty>`Örnek, anahtarın olması gerektiğini belirtir **`Fo`** . `SwitchPrefix`Üst öğe üzerinde özniteliğiyle birlikte `Rule` Bu özellik yürütülebilir dosyaya geçirilir **`/Fo"Debug\"`** . Özellik sayfası kullanıcı arabiriminde C/C++ için komut satırında görünür.

   Diğer özellik öznitelikleri şunlardır:

- **`Visible`**: Özelliğin özellik sayfalarında görünmesini istemiyorsanız, ancak derleme zamanında kullanılabilir olmasını istemiyorsanız, bu özniteliği olarak ayarlayın `false` .

- **`ReadOnly`**: Özellik sayfalarında bu özelliğin değerinin salt okunurdur görünümünü sağlamak istiyorsanız, bu özniteliği olarak ayarlayın `true` .

- **`IncludeInCommandLine`**: Derleme zamanında bir araç, bazı özelliklerine ihtiyaç duymayabilir. `false`Belirli bir özelliğin geçirilmesini engellemek için bu özniteliği olarak ayarlayın.
