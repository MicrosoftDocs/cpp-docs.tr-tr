---
title: "Özellik sayfası XML kural dosyaları | Microsoft Docs"
ms.custom: 
ms.date: 04/27/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: property page XML files
ms.assetid: dd9d9734-4387-4098-8ba6-85b93507731d
caps.latest.revision: "1"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9af178e96b3da8ea839633812128f64190f47d6a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="property-page-xml-rule-files"></a>Özellik sayfası XML kural dosyaları
IDE içinde proje özellik sayfalarını VCTargets klasördeki XML dosyalarını tarafından yapılandırılır. Visual Studio'nun hangi edition(s) yüklenir ve ürün dili tam yolunu bağlıdır. Visual Studio 2017 Enterprise Edition için İngilizce, yolun olduğundan `%ProgramFiles%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\VC\VCTargets\1033`. XML dosyaları, kurallar, kategoriler ve özellikler, kendi veri türü, varsayılan değerleri adlarını ve nasıl görüntülenecek oldukları açıklanmaktadır. IDE içinde bir özellik ayarladığınızda, yeni değer proje dosyasında depolanır.

Bu dosyalar ve Visual Studio IDE iç işleyişini (a) olduğunu anlamak gereken tek senaryoları bir özel özellik sayfası oluşturmak istediğiniz veya (b), Visual Studio IDE aracılığıyla dışındaki bazı yöntem, proje özellikleri özelleştirmek istediğiniz. 

İlk olarak, bir proje özellik sayfalarını açalım (proje düğümüne sağ tıklayın **Çözüm Gezgini** ve Özellikler'i seçin):
   
![Visual C++ proje özellikleri](media/cpp-property-page-2017.png)

Her düğümü altında **yapılandırma özellikleri** bir kural olarak adlandırılır. Bir kural bazen derleyici gibi tek bir araç temsil eder, ancak terimi, yürütür ve bazı çıktıları üretebilir özelliklere sahip bir şey için genel anlamına gelir. Her kural VCTargets klasöründeki bir xml dosyasından doldurulur. Örneğin, yukarıda gösterilen C/C++ kural 'cl.xml' tarafından doldurulur.

Yukarıda gösterildiği gibi her kural kategoriler halinde düzenlenir özellikleri kümesi vardır. Her bir kural alt düğümünde kategorisini temsil eder. Örneğin, C/C++ iyileştirme düğümünde tüm en iyi duruma getirme ile ilgili özelliklerini derleyici aracı içerir. Sağ bölmede bir kılavuz biçiminde özellikler ve değerlerinin kendilerini çizilir.

Not Defteri'nde veya herhangi bir XML Düzenleyicisi (aşağıda anlık görüntü bakın) cl.xml açabilirsiniz. Ek meta veri yanı sıra, kullanıcı arabiriminde görüntülendiği gibi altında tanımlanan özellikler aynı listesine sahip kural olarak adlandırılan bir kök düğüm görürsünüz.

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

Özellik sayfaları UI Yapılandırma Özellikleri'nin altında her düğüm için karşılık gelen bir XML dosyası yok. Ekleyebilir veya kuralları da dahil olmak üzere veya karşılık gelen XML dosyaları konumlara projede kaldırarak kullanıcı Arabiriminde kaldırın. Örneğin, bunu nasıl Microsoft.CppBuild.targets (bir düzey yukarı 1033 klasöründen) cl.xml dahildir:

```xml  
<PropertyPageSchema Condition="'$(ConfigurationType)' != 'Utility'" Include="$(VCTargetsPath)$(LangID)\cl.xml"/>

``` 
Tüm verilerin cl.xml Şerit, aşağıdaki çatıyı ile ulaşır:
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

Aşağıdaki bölümde temel her öğe ve bunlara bağlı meta veri bazıları açıklanmaktadır.

1. **Kural:** kural genellikle xml dosyasında kök düğümü; birçok özniteliklere sahip olabilir:

```xml    
<Rule Name="CL" PageTemplate="tool" SwitchPrefix="/" Order="10"
          xmlns="http://schemas.microsoft.com/build/2009/properties"
          xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
          xmlns:sys="clr-namespace:System;assembly=mscorlib">
  <Rule.DisplayName>
    <sys:String>C/C++</sys:String>
  </Rule.DisplayName>
```  

   a. **Ad:** Name özniteliği bir kural kimliğidir. Tüm özellik sayfası xml dosyaları bir proje için arasında benzersiz olması gerekir.

   b. **PageTemplate:** bu özniteliğin değeri UI şablonları koleksiyonundan seçmek için kullanıcı Arabirimi tarafından kullanılır. "Aracı" şablonu özellikleri standart kılavuz biçiminde işler. Diğer-yerleşik bu öznitelik için "hata ayıklayıcı" ve "Genel" değerlerdir. Hata ayıklama ve genel düğümlerini, bu değerleri belirtme kaynaklanan UI biçimi görmek için sırasıyla bakın. UI "hata ayıklayıcı" sayfası şablonu için bir açılan kutusu "Genel" Şablon kural altında birden çok kategori alt düğümleri sahip aksine tümü tek bir sayfada farklı özellik kategorileri görüntüler ancak farklı hata ayıklayıcıları özellikleri arasında geçiş yapmak için kullanır. düğüm. Bu öznitelik yalnızca bir kullanıcı arabirimine öneridir; xml dosyasını UI bağımsız olacak şekilde tasarlanmıştır. Farklı bir kullanıcı Arabirimi, farklı amaçlar için bu öznitelik kullanabilir.

  c. **SwitchPrefix:** komut satırında için anahtar kullanılan öneki budur. Değerini "/" Konum/zi, / nologo, /W3, vb. gibi anahtarları ile sonuçlandı.

  d. **Sırası:** bu sistemdeki diğer tüm kurallar karşılaştırıldığında bu kural göreli konumunu olası UI istemciye öneridir.

  e. **xmlns:** bu standart bir XAML öğedir. Listelenen üç ad alanlarını görebilirsiniz. Bu ad alanları için XAML seri durumdan çıkarma karşılık XAML şema ve sistem ad alanı, sırasıyla sınıfları.

  F **DisplayName:** bu kuralı düğümü için kullanıcı Arabirimi özellik sayfasında görüntülenen addır. Bu değer yerelleştirilmiştir. DisplayName kuralı bir alt öğesi olarak yerine (örneğin, adı veya SwitchPrefix) özniteliği olarak iç yerelleştirme nedeniyle aracı gereksinimleri oluşturduk. XAML'ın açısından bakıldığında, her ikisi de eşdeğerdir. Bu nedenle, yalnızca bunu görünmesine veya olduğu gibi bırakın öznitelik duruma getirebilirsiniz.

  G. **Veri kaynağı:** bu proje sistemi okunur ve yazılır, özellik değeri gereken konumu hem de (aşağıda açıklanmıştır), gruplandırma belirten, çok önemli bir özelliktir. Cl.XML için bu değerler şunlardır:

```xml  
       <DataSource Persistence="ProjectFile" ItemType="ClCompile" Label="" HasConfigurationCondition="true" />
```  
   - `Persistence="ProjectFile`Kural için tüm özellikleri proje dosyasına yazılması gereken proje sistemi veya (hangi düğümün özellik sayfaları oluşturma için kullanılan) özellik sayfası dosyası olduğunu bildirir. Başka bir olası değer ", değer .kullanıcı dosyasına yazılacak UserFile" dir.

   - `ItemType="ClCompile"`Özellikler ItemDefinition meta verileri veya öğe meta verisi (ikinci bir dosya düğümünden Çözüm Gezgini'nde özellik sayfaları yalnızca kökenli varsa) olarak depolanacağı diyor bu öğe türü. Bu alan ayarlanmazsa, özellik bir PropertyGroup ortak özelliği olarak yazılır.

   - `Label=""`özellikleri olarak yazıldığında belirten `ItemDefinition` meta verileri, üst Itemdefinitiongroup etiketi boş olacaktır (her MSBuild öğesi bir etiket olabilir). Visual Studio 2017 etiketli gruplarını .vcxproj proje dosyası gitmek için kullanır. Çoğu kural özelliklerini içeren gruplarının bir etiket olarak boş bir dize gerektiğini unutmayın.

   - `HasConfigurationCondition="true"`Böylece etkinleşir (koşul üst grubu veya bir değere yapıştırılmış) yalnızca geçerli proje yapılandırması için bir yapılandırma koşulu değerle eklemesi proje sistemi söyler. Örneğin, proje düğümüne kapalı özellik sayfaları açın ve özellik değerini ayarlayın **uyarıları hata olarak kabul** altında **yapılandırma özellikleri > C/C++ genel** "Yes". Aşağıdaki değeri proje dosyasına yazılır. Yapılandırma koşulu Itemdefinitiongroup üst öğeye bağlı dikkat edin.

```xml  
     <ItemDefinitionGroup Condition="‘$(Configuration)|$(Platform)’==’Debug|Win32’">
        <ClCompile>
           <TreatWarningAsError>true</TreatWarningAsError>
        </ClCompile>
     </ItemDefinitionGroup>
 ```
   Bu değer stdafx.cpp gibi belirli bir dosya için özellik sayfasından ayarlandıysa özellik değeri aşağıda gösterildiği gibi proje dosyasında stdafx.cpp öğesi altında yazılacaktır. Yapılandırma koşul meta için doğrudan nasıl bağlı dikkat edin.

 ```xml  
<ItemGroup>
   <ClCompile Include="stdafx.cpp">
      <TreatWarningAsError Condition="‘$(Configuration)|$(Platform)’==’Debug|Win32’">true</TreatWarningAsError>
   </ClCompile>
</ItemGroup>
 ```
   Başka bir özniteliği **DataSource** Yukarıda listelenmeyen olan **PersistedName**. Bu öznitelik, farklı bir ad kullanarak proje dosyasında bir özelliği temsil etmek için kullanabilirsiniz. Varsayılan olarak bu öznitelik özelliğin ayarlanır **adı**. 

   Tek bir özellik grubun üst kuralı veri kaynağı geçersiz kılabilirsiniz. Bu durumda, bu özelliğin değeri konumunu kuralında diğer özellikleri farklı olacaktır.

   h. Burada gösterilmiyor başka bir kural açıklaması, vb. SupportsFileBatching özniteliklerini vardır. Bu tür belgelerine göz atarak öznitelikler geçerli bir kural veya başka bir öğenin tam kümesi alınamıyor. Alternatif olarak, türlerinde ortak özellikler inceleyebilirsiniz `Microsoft.Build.Framework.XamlTypes` ad alanında `Microsoft.Build.Framework .dll` derleme.

   ı. **DisplayName**, **PageTemplate**, ve **sipariş** bu var olan kullanıcı Arabirimi ile ilgili değilse özelliklerdir UI bağımsız veri modeli. Bu özellik sayfalarını görüntülemek için kullanılan herhangi bir kullanıcı Arabirimi tarafından kullanılacak belirli neredeyse özelliklerdir. **DisplayName** ve **açıklama** xml dosyasındaki neredeyse tüm öğelerde var olan iki özelliklerdir. Ve yerelleştirilmiş yalnızca iki özellik bunlar (yerelleştirme bu dizeler, bir sonraki postasına de verilecektir).

2.  **Kategori:** birden çok kategori bir kuralınız olabilir. Kategoriler xml dosyasında listelenen sırayla kategorilerini görüntülemek için bir öneri kullanıcı arabirimine sırasıdır. Örneğin, kullanıcı Arabiriminde görüldüğü gibi C/C++ düğümü altında kategorilerin sırasını – genel, en iyi duruma getirme, önişlemci,...  – söz konusu cl.xml ile aynıdır. Bir örnek kategori şöyle görünür:

```xml  
 <Category Name="Optimization">
    <Category.DisplayName>
        <sys:String>Optimization</sys:String>
    </Category.DisplayName>
 </Category>
```
Yukarıdaki kod parçacığında gösterildiği **adı** ve **DisplayName** önce açıklanan öznitelikleri. Bir kez daha, diğer öznitelikleri vardır bir **kategori** , olabilir yukarıda kullanılmaz. Belge okuma veya ildasm.exe kullanarak derlemeler inceleniyor bildiğiniz bunları hakkında.

3. **Özellikler:** bu xml dosyasının Et ve bu kural tüm özellikleri listesini içerir. Her bir özellik Yukarıdaki XAML çatıyı gösterilen beş olası türlerinden biri olabilir. Elbette, yalnızca birkaç bu türlerin dosyanızda sahip olabilir. Zengin açıklanan izin öznitelik sayısı bir özelliğe sahiptir. Yalnızca açıklamada bulunacağız **StringProperty** burada. Rest çok benzer.

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
Kod parçacığını özniteliklerin çoğunu önce anlatılan. Yeni alt türü, kategori ve anahtar olanlardır.

   a. **Alt** bir öznitelik yalnızca kullanılabilir **StringProperty** ve **StringListProperty**; bağlamsal bilgi verir. Örneğin, "dosyası" değeri özelliği bir dosya yolu temsil ettiğini gösterir. Bağlamsal gibi bilgileri, kullanıcının dosyayı görsel olarak seçmesine izin verir özelliğin düzenleyicisi olarak bir Windows Gezgini sağlayarak düzenleme deneyimini geliştirmek için kullanılır.

   b. **Kategori:** bu altında bu özellik döner kategori bildirir. Bu özellik altında bulmaya **çıktı dosyaları** kullanıcı arabiriminde kategorisi.

   c. **Anahtar:** ne zaman bir kuralı, bir aracı temsil – derleyici araç gibi böyle bir durumda – kuralının özelliklerinin çoğu anahtarlar olarak araç yapı süre boyunca yürütülebilir geçirilir. Bu özniteliğin değeri kullanılacak literal anahtar belirtir. Yukarıdaki özelliği, kendi anahtarını olması gerektiğini belirtir **Fo**. Birlikte **SwitchPrefix** kural, bu özellik üst öznitelikte yürütülebilir geçirilir **/Fo "hata ayıklama\"**  (C/C++ için komut satırı özelliği sayfasında kullanıcı Arabirimi görünür).

   Diğer özellik öznitelikleri şunlardır:

   d. **Görünür:** herhangi bir nedenle özellik sayfaları (ancak hala büyük olasılıkla, derleme zamanı sırasında de kullanılabilir) görünmesini, bu özniteliği false olarak ayarlayın, özellik istiyorsanız yok.

   e. **Salt okunur:** bu özelliğin değeri özellik sayfalarındaki salt okunur bir görünümünü sağlamak istiyorsanız, bu özniteliği true olarak ayarlayın.

   F **IncludeInCommandLine:** bazı özellikler için bir aracı yapı süre boyunca geçirilmesi gerek kalmaz. Bu öznitelik ayarını false olarak geçirilen gelen engeller.


