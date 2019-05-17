---
title: Özellik sayfası XML kuralı dosyaları
ms.date: 05/06/2019
helpviewer_keywords:
- property page XML files
ms.assetid: dd9d9734-4387-4098-8ba6-85b93507731d
ms.openlocfilehash: f23c252604c5b69423b808b3b9f072889e38c816
ms.sourcegitcommit: a10c9390413978d36b8096b684d5ed4cf1553bc8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2019
ms.locfileid: "65837441"
---
# <a name="property-page-xml-rule-files"></a>Özellik sayfası XML kuralı dosyaları

IDE'de proje özelliği sayfalarından VCTargets klasöründe bulunan XML dosyaları tarafından yapılandırılır. Visual Studio'nun hangi sürümleri yüklenir ve ürün dili tam yolunu bağlıdır. Visual Studio 2019 Enterprise Edition için İngilizce, yoludur `%ProgramFiles%\Microsoft Visual Studio\2019\Enterprise\Common7\IDE\VC\VCTargets\1033`. XML dosyaları, kuralları, kategoriler ve özellikler, veri türü, varsayılan değerleri adları ve nasıl görüntülenecek oldukları açıklanmaktadır. IDE'de bir özelliği ayarlamak, yeni değer proje dosyasında depolanır.

(A) Bu dosyalar ve Visual Studio IDE iç işleyişini olduğunu anlamak gereksinim tek senaryoları bir özel özellik sayfası oluşturmak istiyorsunuz veya (b), proje özellikleri aracılığıyla Visual Studio IDE dışında bazı yollarla özelleştirmek istediğiniz.

İlk olarak, bir proje özellik sayfalarını açalım ('nde proje düğümüne sağ tıklayın **Çözüm Gezgini** ve Özellikler'i seçin):

![Visual Studio C++ proje özellikleri](../media/cpp-property-page-2017.png)

Her bir düğümünde **yapılandırma özellikleri** bir kuralı olarak adlandırılır. Bir kural, bazen derleyicinin gibi tek bir araçla temsil eder, ancak genel terimi, yürütür ve, bazı çıktı üretebilir özelliklere sahip bir ifade eder. Her kural VCTargets klasöründeki bir xml dosyasından doldurulur. Örneğin, yukarıda gösterilen C/C++ Kuralı 'cl.xml' tarafından doldurulur.

Yukarıda gösterildiği gibi her kural, kategoriler halinde düzenlenir özellikler kümesi vardır. Her alt düğümü altında bir kural kategorisini temsil eder. Örneğin, C/C++ iyileştirme düğümünde tüm iyileştirme ile ilgili özellikleri derleyici aracı içerir. Sağ bölmede bir kılavuz biçimde özelliklerini ve bunların değerlerini işlenir.

Not Defteri'nde veya herhangi bir XML Düzenleyicisi (aşağıda anlık görüntü bakın) cl.xml açabilirsiniz. Ek meta veri yanı sıra, kullanıcı arabiriminde görüntülenen altında tanımlanan özellikler listesiyle aynı olan kural olarak adlandırılan bir kök düğüm görürsünüz.

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

Özellik sayfaları UI Yapılandırma Özellikleri'nin altında her düğüm için karşılık gelen bir XML dosyası yok. Ekleyin ya da dahil olmak üzere veya projede konumlara karşılık gelen XML dosyaları kaldırarak kullanıcı Arabiriminde kuralları kaldırın. Örneğin, bu nasıl cl.xml Microsoft.CppBuild.targets (bir düzey yukarı 1033 klasöründen) içerir.

```xml
<PropertyPageSchema Condition="'$(ConfigurationType)' != 'Utility'" Include="$(VCTargetsPath)$(LangID)\cl.xml"/>
```

Tüm verilerin cl.xml Şerit, aşağıdaki çatı ile ulaşır:

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

Aşağıdaki bölümde, her temel öğeleri ve bazı kendisine bağlı meta veriler açıklanmaktadır.

1. **Kural:**  Genel xml dosyasının kök düğümünde kuralıdır; Bu, birçok özniteliklere sahip olabilir:

    ```xml
    <Rule Name="CL" PageTemplate="tool" SwitchPrefix="/" Order="10"
              xmlns="http://schemas.microsoft.com/build/2009/properties"
              xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
              xmlns:sys="clr-namespace:System;assembly=mscorlib">
      <Rule.DisplayName>
        <sys:String>C/C++</sys:String>
      </Rule.DisplayName>
    ```

   a. **Adı:** Ad özniteliği, kural için bir kimliğidir. Tüm özellik sayfası xml dosyaları için bir proje arasında benzersiz olması gerekir.

   b. **PageTemplate:** Bu özniteliğin değeri, kullanıcı Arabirimi şablonları koleksiyonundan seçmek için kullanıcı Arabirimi tarafından kullanılır. "Araç" şablonu özellikleri standart kılavuz biçiminde işler. Bu öznitelik için başka yerleşik değerler "hata ayıklayıcı" ve "Genel" dir. Hata ayıklama ve genel düğümlerini, bu değerleri belirleyerek kaynaklanan kullanıcı Arabirimi biçimini görmek için sırasıyla bakın. "Hata ayıklayıcı" sayfası şablonu için kullanıcı Arabirimi açılır liste kutusunda birden çok kategori alt düğümleri kuralın altında olması yerine tüm bir sayfa "Genel" şablonu farklı özellik kategorileri görüntüler ancak farklı hata ayıklayıcılar özellikleri arasında geçiş yapmak için kullanır. düğüm. Bu öznitelik yalnızca bir kullanıcı arabirimi öneridir; xml dosyası, bağımsız kullanıcı Arabirimi olacak şekilde tasarlanmıştır. Bu öznitelik, farklı bir kullanıcı Arabirimi farklı amaçlar için kullanabilirsiniz.

   c. **SwitchPrefix:** Komut satırında anahtarlar için kullanılan önek budur. Değerini "/", / zi, / nologo, / W3, vb. gibi görünen anahtarları neden olur.

   d. **Sırası:** Bu kural sistemdeki diğer tüm kurallar kıyasla göreli konumunu olası bir kullanıcı Arabirimi istemciye bir öneri budur.

   e. **xmlns:** Bu standart bir XAML öğedir. Listelenen üç ad alanlarını görebilirsiniz. Bu ad alanlarına XAML seri durumundan çıkarma için karşılık gelen sınıflar, XAML şema ve sistem ad alanı, sırasıyla.

   f. **DisplayName:** Bu kural düğümü için kullanıcı Arabirimi özellik sayfasında görüntülenen addır. Bu değer yerelleştirilir. DisplayName kural alt öğesi olarak yerine (örneğin, adı veya SwitchPrefix) özniteliği olarak nedeniyle iç yerelleştirme aracı gereksinimleri oluşturduk. XAML'ın açısından bakıldığında, her ikisi de eşdeğerdir. Bu nedenle, yalnızca bir öznitelik dağınıklığını azaltın veya olduğu gibi bırakın katılırsınız.

   g. **Veri kaynağı:** Bu proje sistemi okunan ve yazılan özellik değeri, gereken konum ve kendi gruplandırma (aşağıda açıklanmıştır) belirten bir çok önemli bir özelliktir. Cl.XML için bu değerler şunlardır:

      ```xml
      <DataSource Persistence="ProjectFile" ItemType="ClCompile" Label="" HasConfigurationCondition="true" />
      ```

   - `Persistence="ProjectFile` Tüm özellikleri kuralı için proje dosyasına yazılması proje sistemi veya özellik sayfası dosyasının (hangi düğümü özellik sayfaları üretme kullanıldı) bildirir. Başka bir olası değer "değeri için .user dosyasını yazacak olan UserFile" dir.

   - `ItemType="ClCompile"` belirten özellikleri ItemDefinition meta verileri veya (ikincisi yalnızca özellik sayfaları Çözüm Gezgini'ndeki bir dosya düğümünden kökenli,) öğesi meta veri olarak depolanır, bu öğe türü. Bu alan ayarlanmazsa, özellik, bir PropertyGroup ortak özelliği olarak yazılır.

   - `Label=""` özellikleri olarak yazıldığında belirten `ItemDefinition` meta verileri, üst Itemdefinitiongroup etiketi boş olacaktır (her MSBuild öğesi, bir etiket olabilir). Visual Studio 2017 ve daha sonra kullanmak, .vcxproj proje dosyasına gitmek için grupları etiketi. Çoğu kural özelliklerini içeren gruplar bir etiket olarak boş bir dize gerektiğini unutmayın.

   - `HasConfigurationCondition="true"` Proje sistemi bir yapılandırma koşulu değerle (koşulu üst gruba veya değer yapıştırılmış) yalnızca geçerli proje yapılandırması için geçerli olur böylece eklemesi söyler. Örneğin, özellik sayfalarını kapatmak proje düğümünü açın ve özellik değerini ayarlamak **uyarıları hata olarak değerlendir** altında **yapılandırma özellikleri > C/C++ genel** "Yes". Aşağıdaki değer proje dosyasına yazılır. Itemdefinitiongroup üst yapılandırma koşul bağlı dikkat edin.

      ```xml
      <ItemDefinitionGroup Condition="‘$(Configuration)|$(Platform)’==’Debug|Win32’">
        <ClCompile>
          <TreatWarningAsError>true</TreatWarningAsError>
        </ClCompile>
      </ItemDefinitionGroup>
      ```

      Bu değer, stdafx.cpp gibi belirli bir dosya için özellik sayfası'nda belirlenmişse özellik değerini aşağıda gösterildiği gibi proje dosyasında stdafx.cpp öğesinin altındaki yazılacaktır. Yapılandırma durumu veritabanına doğrudan nasıl bağlı dikkat edin.

      ```xml
      <ItemGroup>
        <ClCompile Include="stdafx.cpp">
          <TreatWarningAsError Condition="‘$(Configuration)|$(Platform)’==’Debug|Win32’">true</TreatWarningAsError>
        </ClCompile>
      </ItemGroup>
      ```

   Başka bir özniteliği **DataSource** Yukarıda listelenmeyen olan **PersistedName**. Proje dosyasında farklı bir ad kullanarak bir özelliği temsil etmek için bu özniteliği kullanabilirsiniz. Varsayılan olarak, bu öznitelik özelliğin ayarlanır **adı**.

   Tek bir özellik, üst kural veri kaynağı geçersiz kılabilirsiniz. Bu durumda, bu özelliğin değerini konumunu kuralında diğer özellikleri farklı olacaktır.

   h. Burada gösterilmiyor açıklaması ve SupportsFileBatching, dahil olmak üzere bir kural, diğer öznitelikleri vardır. Öznitelik geçerli bir kural veya başka bir öğenin tam kümesi, bu tür belgelerine göz atarak alınabilir. Alternatif olarak, türlerinde ortak özelliklerde inceleyebilirsiniz `Microsoft.Build.Framework.XamlTypes` ad alanında `Microsoft.Build.Framework .dll` derleme.

   i. **DisplayName**, **PageTemplate**, ve **sipariş** bu var olan kullanıcı Arabirimi ile ilgili özellikleri Aksi durumda olan kullanıcı Arabirimi bağımsız veri modeli. Bu özellik sayfaları görüntülemek için kullanılan herhangi bir kullanıcı Arabirimi tarafından kullanılacak belirli neredeyse özelliklerdir. **DisplayName** ve **açıklama** neredeyse tüm öğelerin xml dosyasında bulunan iki özellik. Ve yerelleştirilmiş yalnızca iki özellik şunlardır (Bu dizelerin yerelleştirilmesi daha yeni bir gönderiyi verilecektir).

1. **Kategori:** Birden çok kategori bir kuralınız olabilir. Kategoriler bir xml dosyasında listelenen sırayla kategorileri aynı sırada görüntülemek üzere bir kullanıcı arabirimi öneridir. Örneğin, kullanıcı Arabiriminde görüldüğü gibi C/C++ düğümünün altında kategorileri sırasını – genel en iyi duruma getirme, önişlemci,...  – söz konusu cl.xml ile aynıdır. Örnek kategori şöyle görünür:

    ```xml
    <Category Name="Optimization">
      <Category.DisplayName>
        <sys:String>Optimization</sys:String>
      </Category.DisplayName>
    </Category>
    ```

   Yukarıdaki kod parçacığında gösterildiği **adı** ve **DisplayName** önce açıklanan öznitelikleri. Bir kez daha, diğer öznitelikleri vardır bir **kategori** sahip olan yukarıda kullanılmaz. Bunlar hakkında belgeleri okuyarak ya da ildasm.exe kullanarak derlemeleri İnceleme bilebilirsiniz.

1. **Özellikler:** Bu xml dosyasının Et ve bu kural, tüm özellikler listesini içerir. Her bir özellik XAML skeleton yukarıda gösterilen beş olası türlerden biri olabilir. Elbette, yalnızca birkaç bu türlerin dosyanızda olabilir. Bir dizi zengin açıklanan izin öznitelikleri bir özelliğe sahiptir. Yalnızca anlatayım **StringProperty** burada. Rest da oldukça benzerdir.

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

   Kod parçacığı özniteliklerin çoğu önce açıklanan. Yeni alt, kategori ve anahtar olanlardır.

   a. **Alt tür** yalnızca bir öznitelik kullanılabilir **StringProperty** ve **StringListProperty**; bağlamsal bilgiler verir. Örneğin, "dosyasının" değerini özelliği bir dosya yolu temsil ettiğini gösterir. Bu tür bağlamsal bilgiler, görsel olarak dosya seçmesine izin veren özellik düzenleyici olarak bir Windows Explorer'ı sağlayarak düzenleme deneyimini geliştirmek için kullanılır.

   b. **Kategori:** Bu kategori altında bu özelliği denk bildirir. Bu özelliği altında bulmaya **Çıkış dosyalarını** kullanıcı arabiriminde kategorisi.

   c. **Anahtar:** Bir kural bir aracının – temsil ettiğinde gibi derleyici aracı bu durumda – özelliklerinin çoğu kuralın anahtarlar olarak araç derleme zamanında yürütülebilir geçirilir. Bu özniteliğin değeri, kullanılacak değişmez değer anahtar gösterir. Yukarıdaki özelliği, anahtar olması gerektiğini belirtir **Fo**. Birlikte **SwitchPrefix** kural, bu özellik üst öznitelikte yürütülebilir olarak geçirildiğinde **/Fo "hata ayıklama\"**  (komut satırında C/C++ için özellik sayfası kullanıcı Arabiriminde görünür).

   Diğer özellik öznitelikleri şunlardır:

   d. **Görünür:** Herhangi bir nedenle özellik sayfaları (ancak yine de büyük olasılıkla derleme zamanı sırasında kullanılabilir) gösterilmesi için bu öznitelik false olarak ayarlayın, özellik istemiyorsanız.

   e. **Salt okunur:** Bu özelliğin değerini özellik sayfalarındaki salt okunur bir görünümünü sağlamak istiyorsanız, bu öznitelik true olarak ayarlayın.

   f. **IncludeInCommandLine:** Bazı özellikler, derleme zamanında bir aracına geçirilecek gerekmeyebilir. Bu öznitelik false olarak ayarlamayı geçirilen öğesinden engeller.
