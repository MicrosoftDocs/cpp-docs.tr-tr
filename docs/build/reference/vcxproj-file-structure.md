---
title: .vcxproj ve .props dosya yapısı
ms.date: 09/18/2018
helpviewer_keywords:
- .vcxproj file structure
ms.assetid: 14d0c552-29db-480e-80c1-7ea89d6d8e9c
ms.openlocfilehash: 3b7c7bdad8848a3755db4ea565117459c72e939b
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57824130"
---
# <a name="vcxproj-and-props-file-structure"></a>.vcxproj ve .props dosya yapısı

[MSBuild](../msbuild-visual-cpp.md) seçtiğinizde, Visual Studio; varsayılan proje sistemi olan **dosya** > **yeni proje** Visual c++'ta ayarlarını depolanan bir MSBuild Projesi oluşturuyorsunuz. uzantıya sahip bir XML proje dosyasında `.vcxproj`. Proje dosyası ayrıca .props dosyaları ve .targets dosyaları ayarları depolandığı içe. Çoğu durumda, proje dosyasını elle düzenlemeniz gerekiyor ve MSBuild iyi anlamış olmanız sürece aslında onu el ile düzenlemeniz değil. Mümkün olduğunda proje ayarlarını değiştirmek için Visual Studio özellik sayfaları kullanmanız gerekir (bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md). Ancak, bazı durumlarda bir proje dosyası veya özellik sayfası el ile değiştirmeniz gerekebilir. Bu senaryolar için bu makalede dosya yapısı hakkında temel bilgileri içerir.

**Önemli:**

.Vcxproj dosyasını el ile düzenlemek isterseniz, bu bilgiler dikkat edin:

1. Bu makalede açıklanan önceden belirlenmiş bir form dosya yapısını izlemeniz gerekir.

1. Visual C++ proje sistemi şu anda proje öğelerinde joker karakterleri desteklemiyor. Örneğin, bu desteklenmez:

   ```xml
   <ClCompile Include="*.cpp"/>
   ```

1. Visual C++ proje sistemi proje öğesi yollarında makroları şu anda desteklemiyor. Örneğin, bu desteklenmez:

   ```xml
   <ClCompile Include="$(IntDir)\generated.cpp"/>
   ```

   "Desteklenmiyor" makroları IDE içindeki tüm işlemler için çalışmaya garanti edilmez anlamına gelir. Hangi değerlerine farklı yapılandırmaları değiştirme makroları çalışması gerekir, ancak farklı bir filtre ya da projeye bir öğe taşınırsa korunmayabilir. IDE farklı proje yapılandırmaları için farklı proje öğe yolları beklentisi çünkü hangi değerlerine farklı yapılandırmaları değiştirme makroları sorunlara neden olur.

1. Doğru bir şekilde eklendi, kaldırıldı veya düzenlendi, değiştirilen proje özellikleri için **proje özellikleri** iletişim kutusunda, dosyanın her proje yapılandırması için ayrı Grup içermelidir ve koşullar Bu biçimde olmalıdır:

   ```xml
   Condition="'$(Configuration)|$(Platform)'=='Debug|Win32'"
   ```

1. Özellik kuralı dosyasında belirtildiği gibi doğru etiketle grubundaki her bir özellik belirtilmelidir. Daha fazla bilgi için [özellik sayfası xml kural dosyaları](property-page-xml-files.md).

## <a name="vcxproj-file-elements"></a>.vcxproj dosyası öğeleri

Herhangi bir metin veya XML Düzenleyicisi'ni kullanarak bir .vcxproj dosyası içeriğini inceleyebilirsiniz. Visual Studio'daki Çözüm Gezgini'nde projeye sağ tıklayarak görüntüleyebilirsiniz seçme **projeyi** seçip **Düzenle Foo.vcxproj**.

Üst düzey öğeleri belirli bir sırada göründüğünü fark edilecek ilk şey var. Örneğin:

- Birçok özellik grupları ve öğe tanımı gruplarındaki Microsoft.Cpp.Default.props için içe sonra oluşur.

- Dosyanın sonunda tüm hedefleri içeri aktarılır.

- Her bir benzersiz etiket ile birden çok özellik grubu vardır ve belirli bir sırada ortaya.

MSBuild sıralı Değerlendirme modelini temel alan çünkü proje dosyasındaki öğelerin sırasını çok önemlidir.  Proje dosyanızı içeri aktarılan .props ve .targets dosyalarına dahil olmak üzere, bir özelliğin birden çok tanımları oluşuyorsa, son tanımı önceki olanları geçersiz kılar. MSBUild altyapısını olduğundan, değerlendirme sırasında son karşılaştığı aşağıdaki örnekte, derleme sırasında "xyz" değerine ayarlanır.

```xml
  <MyProperty>abc</MyProperty>
  <MyProperty>xyz</MyProperty>
```

Aşağıdaki kod parçacığı bir minimal .vcxproj dosyası gösterir. Visual Studio tarafından oluşturulan tüm .vcxproj dosyası bu üst düzey MSBuild öğeleri içerir ve (bunlar birden çok kopyasını böyle her bir üst düzey öğe içerebilir ancak) şu sırada görünür. Unutmayın `Label` öznitelikleri yalnızca Visual Studio tarafından işaret panolarını düzenlemek için kullanılan rastgele etiketler; diğer bir işlev sahiptirler.

```xml
<Project DefaultTargets="Build" ToolsVersion="4.0" xmlns='http://schemas.microsoft.com/developer/msbuild/2003'>
  <ItemGroup Label="ProjectConfigurations" />
  <PropertyGroup Label="Globals" />
  <Import Project="$(VCTargetsPath)\Microsoft.Cpp.default.props" />
  <PropertyGroup Label="Configuration" />
  <Import Project="$(VCTargetsPath)\Microsoft.Cpp.props" />
  <ImportGroup Label="ExtensionSettings" />
  <ImportGroup Label="PropertySheets" />
  <PropertyGroup Label="UserMacros" />
  <PropertyGroup />
  <ItemDefinitionGroup />
  <ItemGroup />
  <Import Project="$(VCTargetsPath)\Microsoft.Cpp.targets" />
  <ImportGroup Label="ExtensionTargets" />
</Project>
```

Aşağıdaki bölümlerde bu öğelerin her birinin amacı ve neden bu şekilde sıralanır açıklanmaktadır:

### <a name="project-element"></a>Proje öğesi

```xml
<Project DefaultTargets="Build" ToolsVersion="4.0" xmlns='http://schemas.microsoft.com/developer/msbuild/2003' >
```

`Project` kök düğümüdür. Bu, kullanılacak MSBuild sürümü ve aynı zamanda bu dosya için MSBuild.exe geçirildiğinde yürütülecek varsayılan hedef belirtir.

### <a name="projectconfigurations-itemgroup-element"></a>ProjectConfigurations ItemGroup öğesi

```xml
<ItemGroup Label="ProjectConfigurations" />
```

`ProjectConfigurations` Proje yapılandırması açıklamasını içerir. Örnekler, hata ayıklama | Win32, yayın | Win32, hata ayıklama | ARM ve benzeri. Birçok proje ayarları, belirli bir yapılandırmaya özgüdür. Örneğin, bir yayın yapısı ancak hata ayıklama derlemesi için en iyi duruma getirme özellikleri ayarlamak büyük olasılıkla isteyeceksiniz.

`ProjectConfigurations` Öğesi grubu oluşturma zamanında kullanılmaz. Visual Studio IDE, proje yüklemek için gerektirir. Şu öğe grubunu .props dosya taşındı ve .vcxproj dosyası içeri aktarıldı. Ekleme veya kaldırma yapılandırmaları gerekir, ancak bu durumda, elle .props dosyası düzenlemeniz gerekir; IDE kullanamazsınız.

### <a name="projectconfiguration-elements"></a>ProjectConfiguration öğeleri

Aşağıdaki kod parçacığında, bir proje yapılandırması gösterilmektedir. Bu örnekte ' Debug | x 64' olan yapılandırma adı. Proje yapılandırması adı biçimi $(Configuration)|$(Platform). içinde olmalıdır Bir proje yapılandırması düğüm iki özelliklere sahiptir: Yapılandırma ve Platform. Bu özellikler yapılandırma etkin olduğunda burada belirtilen değerlerle otomatik olarak ayarlanır.

```xml
<ProjectConfiguration Include="Debug|x64">
  <Configuration>Debug</Configuration>
  <Platform>x64</Platform>
</ProjectConfiguration>
```

Bir proje yapılandırması için herhangi bir birleşimini tüm ProjectConfiguration öğelerinde kullanılan yapılandırma ve Platform değerleri bulmak IDE bekliyor. Bu, genellikle anlamsız proje yapılandırmaları, bu gereksinimi karşılamak için bir proje gerekebileceği anlamına gelir. Örneğin, bir projenin bu yapılandırmaları varsa:

- Hata ayıklama | Win32

- Perakende | Win32

- Özel 32-bit iyileştirme | Win32

ardından "Özel 32-bit iyileştirme" için x64 anlamsız olmasına rağmen bu yapılandırmalar olmalıdır:

- Hata ayıklama | x64

- Perakende | x64

- Özel 32-bit iyileştirme | x64

Yapı devre dışı bırakabilir ve herhangi bir yapılandırma için komutları dağıtma **çözüm Yapılandırma Yöneticisi**.

### <a name="globals-propertygroup-element"></a>Globals PropertyGroup öğesi

```xml
<PropertyGroup Label="Globals" />
```

`Globals` Proje düzeyi ayarları ProjectGuid RootNamespace ve ApplicationType gibi içeren / ApplicationTypeRevision. Son iki genellikle hedef işletim sistemi tanımlar. Başvurular ve proje öğeleri koşullar şu anda sahip olamaz Bunun nedeni, bir proje yalnızca tek bir işletim sistemi hedefleyebilirsiniz. Bu özellikler genellikle başka bir proje dosyasında geçersiz kılınmaz. Bu grup yapılandırması bağımlı değildir ve bu nedenle genellikle yalnızca bir Globals grup proje dosyasında mevcut.

### <a name="microsoftcppdefaultprops-import-element"></a>Microsoft.Cpp.default.props içeri aktarma öğesi

```xml
<Import Project="$(VCTargetsPath)\Microsoft.Cpp.default.props" />
```

**Microsoft.Cpp.default.props** özellik sayfası Visual Studio ile birlikte gelir ve değiştirilemez. Bu proje için varsayılan ayarları içerir. Varsayılan değerleri ApplicationType bağlı olarak değişebilir.

### <a name="configuration-propertygroup-elements"></a>Yapılandırma PropertyGroup öğelerinin

```xml
<PropertyGroup Label="Configuration" />
```

A `Configuration` özellik grubuna sahip bir ekli yapılandırma durumu (gibi `Condition=”'$(Configuration)|$(Platform)'=='Debug|Win32'”`) ve yapılandırma başına birden çok kopya olarak gelir. Bu özellik grubu, belirli bir yapılandırma için ayarlanan özellikler barındırır. Yapılandırma özellikleri PlatformToolset içerir ve ayrıca sistem özellik sayfalarında dahilini denetimini **Microsoft.Cpp.props**. Örneğin, özellik tanımlarsanız `<CharacterSet>Unicode</CharacterSet>`, sonra sistem özellik sayfası **microsoft. Cpp.unicodesupport.props** dahil edilir. İnceleyin, **Microsoft.Cpp.props**, satır görürsünüz: `<Import Condition=”'$(CharacterSet)' == 'Unicode'”   Project=”$(VCTargetsPath)\microsoft.Cpp.unicodesupport.props”/>`.

### <a name="microsoftcppprops-import-element"></a>Microsoft.cpp.props öğesine içeri aktarma öğesi

```xml
<Import Project="$(VCTargetsPath)\Microsoft.Cpp.props" />
```

**Microsoft.Cpp.props** özellik sayfası (doğrudan veya içeri aktarmalar aracılığıyla) derleyicinin en iyi duruma getirme ve uyarı düzeyi özellikleri, MIDL Aracı'nın TypeLibraryName gibi birçok araca özgü özellikler için varsayılan değerleri tanımlar özellik ve benzeri. Yapılandırma özellikleri hemen yukarıdaki özelliği grupta tanımlanan göre çeşitli sistem özellik sayfalarını içeri aktarır.

### <a name="extensionsettings-importgroup-element"></a>ExtensionSettings Importgroup öğesi

```xml
<ImportGroup Label="ExtensionSettings" />
```

`ExtensionSettings` Yapı özelleştirmeleri parçası olan özellik sayfaları için içeri aktarmalar grubunu içerir. Bir yapı özelleştirmesi sağlayan üç adede kadar dosyalar tarafından tanımlanır: bir .targets dosyasında ve .props dosyası bir .xml dosyasıdır. Bu içeri aktarma Grup Imports .props dosyası içerir.

### <a name="propertysheets-importgroup-elements"></a>PropertySheets Importgroup öğeleri

```xml
<ImportGroup Label="PropertySheets" />
```

`PropertySheets` Kullanıcı özellik sayfaları için içeri aktarmalar grubunu içerir. Visual Studio özellik Yöneticisi görünüm aracılığıyla eklediğiniz özellik sayfalarını şunlardır. Bu içeri aktarmalar listelendiği sırası önemlidir ve özellik Yöneticisi'nde yansıtılır. Proje dosyası normal olarak, bu tür bir içe aktarma grubu, her bir proje yapılandırması için birden çok örneğini de içerir.

### <a name="usermacros-propertygroup-element"></a>UserMacros PropertyGroup öğesi

```xml
<PropertyGroup Label="UserMacros" />
```

`UserMacros` özellikleri içeren yapı işleminizi özelleştirmek için kullanılan değişkenleri olarak oluşturun. Örneğin, özel çıkış yolunuzu $(CustomOutputPath) tanımlayın ve diğer değişkenleri tanımlamak için kullanmak için bir kullanıcı makrosu tanımlayabilirsiniz. Bu özellik grubu gibi özellikleri barındırır. Visual C++ yapılandırmaları için kullanıcı makroları desteklemediğinden Visual Studio'da bu grup proje dosyasında doldurulmamış olduğunu unutmayın. Kullanıcı makroları, özellik sayfalarında desteklenir.

### <a name="per-configuration-propertygroup-elements"></a>Yapılandırma PropertyGroup öğelerinin

```xml
<PropertyGroup />
```

Bu grubun özelliği, tüm proje yapılandırmalarına ilişkin yapılandırma her birden çok örneği vardır. Her özellik grubu, bağlı bir yapılandırma koşul bulunmalıdır. Tüm yapılandırmaları eksikse **proje özellikleri** iletişim düzgün çalışmaz. Yukarıdaki özellik gruplarını, bu etiket yok. Bu grup, proje düzeyi yapılandırma ayarları içerir. Bu ayarlar, belirtilen öğe grubunun parçası olan tüm dosyalar için geçerlidir. Derleme özelleştirme öğesi tanımı meta verileri burada başlatılır.

Bu PropertyGroup sonra gelmelidir `<Import Project="$(VCTargetsPath)\Microsoft.Cpp.props" />` ve diğer hiçbir PropertyGroup önce bu etiket olmadan olması gerekir (Aksi takdirde proje özelliklerini düzenleme doğru şekilde çalışmaz).

### <a name="per-configuration-itemdefinitiongroup-elements"></a>Yapılandırma Itemdefinitiongroup öğeleri

```xml
<ItemDefinitionGroup />
```

Öğe tanımları içerir. Bu, her yapılandırma için etiket daha az PropertyGroup öğesi olarak aynı koşullar kurallara uymanız gerekir.

### <a name="itemgroup-elements"></a>ItemGroup öğelerini

```xml
<ItemGroup />
```

Proje öğeleri (kaynak dosyaları, vb.) içerir. Koşullar, proje öğeleri (proje öğeleri kuralları tanımlar tarafından kabul edilir diğer bir deyişle, öğe türleri) için desteklenmez.

Bunların tümü aynı olsa bile, her bir yapılandırma için koşulları yapılandırma meta verileri olmalıdır. Örneğin:

```xml
<ItemGroup>
  <ClCompile Include="stdafx.cpp">
    <TreatWarningAsError Condition="‘$(Configuration)|$(Platform)’==’Debug|Win32’">true</TreatWarningAsError>
    <TreatWarningAsError Condition="‘$(Configuration)|$(Platform)’==’Debug|x64’">true</TreatWarningAsError>
  </ClCompile>
</ItemGroup>
```

Visual C++ proje sistemi şu anda proje öğelerinde joker karakterleri desteklemiyor.

```xml
<ItemGroup>
  <ClCompile Include="*.cpp"> <!--Error-->
</ItemGroup>
```

Visual C++ proje sistemi proje öğeleri makroları şu anda desteklemiyor.

```xml
<ItemGroup>
  <ClCompile Include="$(IntDir)\generated.cpp"> <!--not guaranteed to work in all scenarios-->
</ItemGroup>
```

Başvuruları içinde bir ItemGroup belirtilir ve bu sınırlamalara sahiptirler:

- Başvuruları koşulları desteklemez.

- Meta verilere başvurur, koşulları desteklemez.

### <a name="microsoftcpptargets-import-element"></a>Microsoft.Cpp.targets içeri aktarma öğesi

```xml
<Import Project="$(VCTargetsPath)\Microsoft.Cpp.targets" />
```

(Doğrudan veya içeri aktarmalar aracılığıyla) gibi yapı, Visual C++ hedefleri temiz, vb. tanımlar.

### <a name="extensiontargets-importgroup-element"></a>ExtensionTargets Importgroup öğesi

```xml
<ImportGroup Label="ExtensionTargets" />
```

Bu grup, hedef yapı özelleştirmesi dosyaları için içeri aktarmalar içerir.

## <a name="impact-of-incorrect-ordering"></a>Hatalı sıralama etkisi

Visual Studio IDE proje dosyası sıralaması yukarıda açıklanan bağlıdır. Bir özellik değeri özellik sayfaları'nda tanımladığınızda, örneğin, IDE genel özellik tanımı boş bir etikete sahip özellik grubundaki yerleştirmeniz gerekir. Bu duruma sistem özellik sayfalarında varsayılan değerleri kullanıcı tanımlı değerler tarafından geçersiz kılınmasını sağlar. Benzer şekilde, hedef dosya sonunda yukarıda tanımlanan özellikler kullandıkları ve genellikle özelliklerinin kendileri tanımlamazsanız olduğundan içeri aktarılır. Sistem özellik sayfalarından sonra benzer şekilde, kullanıcı özellik sayfaları içeri aktarılan (aracılığıyla dahil **Microsoft.Cpp.props**). Bu kullanıcı tarafından sistem özellik sayfalarını getirildi tüm varsayılanları geçersiz kılabilirsiniz sağlar.

Bu düzen bir .vcxproj dosyası izlemiyorsa, yapı sonuçlarını beklediğiniz olmayabilir. Örneğin, kullanıcı tarafından tanımlanan özellik sayfalarından sonra yanlışlıkla bir sistem özellik sayfası içe aktarırsanız, kullanıcı ayarları tarafından sistem özellik sayfalarını kılınır.

Hatta IDE tasarım zamanı deneyimi öğeleri doğru sıralama belirli bir ölçüde bağlıdır. Örneğin, .vcxproj dosyası yoksa, `PropertySheets` grubunu İçeri Aktar, IDE içinde kullanıcı tarafından oluşturulan yeni bir özellik sayfası yerleştirileceği yeri belirlemek mümkün olmayabilir **özellik Yöneticisi**. Bu, bir sistem sayfası tarafından geçersiz kılınmış olan bir kullanıcı e-tablosunda sonuçlanabilir. IDE tarafından kullanılan buluşsal yöntem .vcxproj dosya düzeni küçük tutarsızlıklar tolere edebilen olsa da, bu makalenin önceki bölümlerinde gösterilen yapısından cluster_count_prıor değil önemle tavsiye edilir.

## <a name="how-the-ide-uses-element-labels"></a>IDE öğesi etiketleri kullanma

Ayarladığınızda IDE'de **UseOfAtl** özelliği genel özellik sayfası'nda yazılmış proje dosyasındaki yapılandırma özellik grubuna sırada **TargetName** aynı özellik sayfası özelliği Etiket daha az başına-yapılandırma özellik grubuna yazılır. Visual Studio her bir özellik yazılacağı hakkında bilgi için özellik sayfanın xml dosyasını inceler. İçin **genel** özellik sayfası (Visual Studio Enterprise Edition'ın İngilizce sürümünü sahip olduğunuz varsayılarak), bu dosya `%ProgramFiles(x86)%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\VC\VCTargets\1033\general.xml`. Özellik sayfası XML kural dosyası, bir kural ve tüm özelliklerini statik bilgilerini tanımlar. Böyle bir bilgi parçasıdır tercih edilen bir kural özelliğine (değerinin yazılacağı dosyası) hedef dosyadaki konumudur. Tercih edilen konum, proje dosyası öğelerini etiket özniteliği tarafından belirtilir.

## <a name="property-sheet-layout"></a>Özellik sayfa düzeni

Aşağıdaki XML kod parçacığı, bir özellik sayfası (.props) dosyasının en az bir düzendir. Bir .vcxproj dosyası benzer ve önceki tartışmadan .props öğeleri işlevlerini olayla.

```xml
<Project ToolsVersion="4.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <ImportGroup Label="PropertySheets" />
  <PropertyGroup Label="UserMacros" />
  <PropertyGroup />
  <ItemDefinitionGroup />
  <ItemGroup />
</Project>
```

Kendi özellik sayfası yapmak için .props dosyalardan biri VCTargets klasörüne kopyalayıp amaçlarınız için değiştirebilirsiniz. Visual Studio 2017 Enterprise edition için varsayılan VCTargets yoldur `%ProgramFiles%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\VC\VCTargets`.

## <a name="see-also"></a>Ayrıca bkz.

[C++ derleyicisi ayarlayın ve derleme Visual Studio özellikleri](../working-with-project-properties.md)<br/>
[Özellik Sayfası XML Dosyaları](property-page-xml-files.md)
