---
title: dosya yapısı .vcxproj ve .props | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- .vcxproj file structure
ms.assetid: 14d0c552-29db-480e-80c1-7ea89d6d8e9c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fe466ff9250543a61fde8da41900b152a9874e09
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="vcxproj-and-props-file-structure"></a>.vcxproj ve .props dosya yapısı

MSBuild Visual Studio varsayılan proje sistemidir; seçtiğinizde **dosya | Yeni proje** Visual c++'ta ayarlarını uzantılı bir XML proje dosyasında depolanan MSBuild Projesi oluşturmakta olduğunuz `.vcxproj`. Proje dosyası da .props dosyaları ve ayarları depolandığı .targets dosyaları içeri. Çoğu durumda, hiçbir zaman proje dosyasını el ile düzenlemeniz gerekir ve MSBuild iyi anlamış yoksa aslında el ile düzenlemeden değil. Mümkün olduğunda proje ayarlarını değiştirmek için Visual Studio özellik sayfaları kullanmanız gerekir (bkz [proje özellikleriyle çalışma](working-with-project-properties.md). Ancak, bazı durumlarda bir proje dosyası veya özellik sayfasında el ile değiştirmeniz gerekebilir. Bu senaryolar için bu makalede dosya yapısı hakkında temel bilgileri içerir.

**Önemli:**

.Vcxproj dosyasını el ile düzenleme seçerseniz, bu bilgiler dikkat edin:

1. Dosyanın bu makalede açıklanan önceden belirlenmiş bir form yapıya sahip olmalıdır.

1. Visual C++ proje sistem şu anda proje öğelerinde joker karakterleri desteklemez. Örneğin, bu desteklenmez:

   ```xml
   <ClCompile Include="*.cpp"/>
   ```

1. Visual C++ proje sistemi proje öğesi yollarında makroları şu anda desteklemiyor. Örneğin, bu desteklenmez:

   ```xml
   <ClCompile Include="$(IntDir)\generated.cpp"/>
   ```

1. Doğru eklenmiş, kaldırılmış veya düzenlenebilir olduğunda değiştirilmesi proje özellikleri olması için **proje özelliklerini** iletişim kutusunda, dosyayı her proje yapılandırması için ayrı Grup içermelidir ve koşullar Bu biçimde olmalıdır:

   ```xml
   Condition="'$(Configuration)|$(Platform)'=='Debug|Win32'"
   ```

1. Özellik kural dosyasında belirtildiği doğru etiketle grubundaki her bir özellik belirtilmelidir. Daha fazla bilgi için bkz: [özellik sayfası xml kural dosyaları](property-page-xml-files.md).

## <a name="vcxproj-file-elements"></a>.vcxproj dosya öğeleri

Herhangi bir metin veya XML düzenleyicisi kullanarak .vcxproj dosyasının içeriğini inceleyebilirsiniz. Visual Studio'daki Çözüm Gezgini'nde projeye sağ tıklayarak görüntüleyebilirsiniz seçme **projeyi** ve ardından **Düzenle Foo.vcxproj**.

Fark edilecek ilk şey, üst düzey öğeleri belirli bir sırada görünür olur. Örneğin:

- Alma için Microsoft.Cpp.Default.props sonra birçok özellik grupları ve öğesi tanım gruplarını gerçekleşir.
- tüm hedefleri dosyanın sonunda içeri aktarılır.
- her benzersiz bir etiketi ile birden çok özellik grupları vardır ve belirli bir sırada gerçekleşir.

MSBuild sıralı Değerlendirme modelini temel alan olduğundan proje dosyasındaki öğelerin sırasını çok önemlidir.  Tüm içeri aktarılan .props ve .targets dosyaları dahil olmak üzere, proje dosyası birden çok özellik tanımını oluşuyorsa, son tanımı önceki olanları geçersiz kılar. MSBUild altyapısı olmadığından, değerlendirme sırasında en son karşılaştığı aşağıdaki örnekte, derleme sırasında "xyz" değerine ayarlanır.

```xml
  <MyProperty>abc</MyProperty>
  <MyProperty>xyz</MyProperty>
```

Aşağıdaki kod parçacığını bir minimal .vcxproj dosyasını gösterir. Visual Studio tarafından oluşturulan tüm .vcxproj dosyası bu üst düzey MSBuild öğeleri içerir ve (bunlar gibi her bir en üst düzey öğesi birden çok kopyasını bulunmasına karşın) bu sırada görüntülenir. Unutmayın `Label` öznitelikleri yalnızca Visual Studio tarafından işaret panolarını düzenlemek için kullanılan rastgele etiketleri; diğer bir işlev sahiptirler.

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

Aşağıdaki bölümlerde bu öğelerin her birini amacını ve bu şekilde neden sıralı açıklanmaktadır:

### <a name="project-element"></a>Proje öğesi

```xml
<Project DefaultTargets="Build" ToolsVersion="4.0" xmlns='http://schemas.microsoft.com/developer/msbuild/2003' >
```

`Project` kök düğümdür. MSBuild sürümü kullanmak için ve ayrıca bu dosya için MSBuild.exe geçirildiğinde yürütülecek varsayılan hedef belirtir.

### <a name="projectconfigurations-itemgroup-element"></a>ProjectConfigurations ItemGroup öğesi

```xml
<ItemGroup Label="ProjectConfigurations" />
```

`ProjectConfigurations` Proje yapılandırma açıklaması içerir. Örnekler hata ayıklama | Win32, sürüm | Win32, hata ayıklama | ARM ve benzeri. Çok sayıda proje ayarları belirli bir yapılandırmaya özeldir. Örneğin, bir yayın derlemesi ancak hata ayıklama derlemesi iyileştirme özelliklerini ayarlamak büyük olasılıkla isteyeceksiniz.

`ProjectConfigurations` Öğesi grubu derleme zamanında kullanılmaz. Visual Studio IDE proje yüklemek için gerektiriyor. Bu öğe grubu .props dosyasına taşınır ve .vcxproj dosyasına içeri. Yapılandırması ekleme ve kaldırma ihtiyacınız varsa, ancak bu durumda, el ile .props dosyayı düzenlemeniz gerekir; IDE kullanamazsınız.

### <a name="projectconfiguration-elements"></a>ProjectConfiguration öğeleri

Aşağıdaki kod parçacığını bir proje yapılandırması gösterilmektedir. Bu örnekte ' hata ayıklama | x 64' olan yapılandırma adı. Proje yapılandırma adı biçimi $(Configuration)|$(Platform). olmalıdır Bir proje yapılandırma düğümünü iki özelliklere sahip olabilir: yapılandırması ve platformu. Bu özellikler, yapılandırma etkin olduğunda burada belirtilen değerlerle otomatik olarak ayarlanır.

   ```xml
   <ProjectConfiguration Include="Debug|x64">
     <Configuration>Debug</Configuration>
     <Platform>x64</Platform>
   </ProjectConfiguration>
   ```

Herhangi bir bileşimini tüm ProjectConfiguration öğelerde kullanılan yapılandırması ve platformu değerler için bir proje yapılandırma bulmak IDE bekliyor. Bu, genellikle bir proje bu gereksinimi karşılamak için anlamsız proje yapılandırmaları gerekebileceği anlamına gelir. Örneğin, bir projenin Bu yapılandırmalar varsa:

- Hata ayıklama | Win32
- Perakende | Win32
- Özel 32-bit en iyi duruma getirme | Win32

ardından "Özel 32-bit iyileştirme" için x64 anlamsız olsa bile bu yapılandırmalar olmalıdır:

- Hata ayıklama | x64
- Perakende | x64
- Özel 32-bit en iyi duruma getirme | x64

Yapı devre dışı bırakmak ve herhangi bir yapılandırma için komutları dağıtma **çözüm Configuration Manager**.

### <a name="globals-propertygroup-element"></a>Globals PropertyGroup öğesi

```xml
 <PropertyGroup Label="Globals" />
```

`Globals` Proje düzeyi ayarları ProjectGuid, RootNamespace ve ApplicationType gibi içeren / ApplicationTypeRevision. Son iki genellikle işletim sistemi hedef tanımlayın. References ve proje öğeleri koşulları şu anda sahip olamaz due için nedeni, bir proje yalnızca tek bir işletim sistemi hedefleyebilirsiniz. Bu özellikleri genellikle başka bir yerde proje dosyasında geçersiz kılınmaz. Bu grubun yapılandırma bağımlı değildir ve bu nedenle yalnızca bir Globals grup proje dosyasında genellikle mevcut.

### <a name="microsoftcppdefaultprops-import-element"></a>Microsoft.Cpp.default.props içeri aktarma öğesi

```xml
<Import Project="$(VCTargetsPath)\Microsoft.Cpp.default.props" />
```

**Microsoft.Cpp.default.props** özellik sayfası Visual Studio ile gelir ve değiştirilemez. Proje için varsayılan ayarları içerir. Varsayılanları ApplicationType bağlı olarak değişebilir.

### <a name="configuration-propertygroup-elements"></a>Yapılandırma PropertyGroup öğeleri

```xml
<PropertyGroup Label="Configuration" />
```

A `Configuration` özellik grubu ekli yapılandırma koşula sahip (gibi `Condition=”'$(Configuration)|$(Platform)'=='Debug|Win32'”`) ve yapılandırma başına birden çok kopya sunar. Bu özellik grubu için belirli yapılandırma kümesi özellikleri barındırır. Yapılandırma özellikleri PlatformToolset içerir ve ayrıca sistem özellik sayfaları ekleme denetimini **Microsoft.Cpp.props**. Örneğin, özellik tanımlarsanız `<CharacterSet>Unicode</CharacterSet>`, ardından sistemi özellik sayfası **microsoft. Cpp.unicodesupport.props** dahil edilir. İnceleyin, **Microsoft.Cpp.props**, satır görürsünüz: `<Import Condition=”'$(CharacterSet)' == 'Unicode'”   Project=”$(VCTargetsPath)\microsoft.Cpp.unicodesupport.props”/>`.

### <a name="microsoftcppprops-import-element"></a>Microsoft.Cpp.props içeri aktarma öğesi

```xml
<Import Project="$(VCTargetsPath)\Microsoft.Cpp.props" />
```

**Microsoft.Cpp.props** özellik sayfası (doğrudan veya içeri aktarmalar aracılığıyla) derleyicinin en iyi duruma getirme ve uyarı düzeyi özellikleri MIDL aracın TypeLibraryName gibi birçok aracı özgü özelliklerinin varsayılan değerlerini tanımlar özellik ve benzeri. Ayrıca, hangi yapılandırma özellikleri hemen yukarıdaki özellik grubunda tanımlanan göre çeşitli sistem özellik sayfalarını alır.

### <a name="extensionsettings-importgroup-element"></a>ExtensionSettings Importgroup öğesi

```xml
<ImportGroup Label="ExtensionSettings" />
```

`ExtensionSettings` Grubu içeri aktarmalar için derleme özelleştirmeleri parçası olan özellik sayfalarını içerir. Yapı özelleştirme en çok üç dosyaları tarafından tanımlanır: bir .targets dosyasında, .props dosyası ve bir .xml dosyası. Bu içeri aktarma grup içeri aktarmalar için .props dosyası içerir.

### <a name="propertysheets-importgroup-elements"></a>PropertySheets Importgroup öğeleri

```xml
<ImportGroup Label="PropertySheets" />
```

`PropertySheets` Grubu içeri aktarmalar için kullanıcı özellik sayfalarını içerir. Visual Studio'da özellik Yöneticisi görünümü aracılığıyla eklediğiniz özellik sayfalarını bunlar. Bu içeri aktarmalar listelenmiş görevlerin sırası önemlidir ve özellik Yöneticisi'nde yansıtılır. Proje dosyası normal olarak bu tür bir içe aktarma grubu, her proje yapılandırması için bir tane birden çok örneğini içerir.

### <a name="usermacros-propertygroup-element"></a>UserMacros PropertyGroup öğesi

```xml
<PropertyGroup Label="UserMacros" />
```

`UserMacros` Özellikler içeren yapı işleminizin özelleştirmek için kullanılan değişkenleri olarak oluşturun. Örneğin, özel çıkış yolu $(CustomOutputPath) tanımlayın ve diğer değişkenleri tanımlamak için kullanmak üzere bir kullanıcı makrosu tanımlayabilirsiniz. Bu özellik grubu gibi özellikleri barındırır. Visual C++ yapılandırmaları için kullanıcı makroları desteklemediğinden Visual Studio'da bu grubun proje dosyasında doldurulmaz olduğunu unutmayın. Kullanıcı makroları özellik sayfalarında desteklenir.

### <a name="per-configuration-propertygroup-elements"></a>Yapılandırma başına PropertyGroup öğeleri

```xml
<PropertyGroup />
```

Bu özellik grubu, tüm proje yapılandırmaları için yapılandırma her birden çok örneği vardır. Her özellik grubu bağlı bir yapılandırma koşul olması gerekir. Tüm yapılandırmaları eksikse **proje özelliklerini** iletişim düzgün çalışmayacak. Yukarıdaki özellik grupları farklı olarak, bu bir etiket yok. Bu grup, proje düzeyi yapılandırma ayarları içerir. Bu ayarlar, belirtilen öğe grubunun parçası olan tüm dosyalar için geçerlidir. Özelleştirme öğesi tanımı oluşturma meta veri burada başlatılır.

Bu PropertyGroup sonra gelmelidir `<Import Project="$(VCTargetsPath)\Microsoft.Cpp.props" />` ve diğer hiçbir PropertyGroup kendisinden önce etiketsiz olmalıdır (Aksi halde proje özelliklerini düzenleme düzgün çalışmaz).

### <a name="per-configuration-itemdefinitiongroup-elements"></a>Yapılandırma başına Itemdefinitiongroup öğeleri

```xml
 <ItemDefinitionGroup />
```

Öğe tanımları içerir. Bu etiket daha az başına-yapılandırma PropertyGroup öğesi olarak aynı koşulları kurallara uymalıdır.

### <a name="itemgroup-elements"></a>ItemGroup öğeleri

```xml
<ItemGroup />
```

Proje öğelerinde (kaynak dosyaları, vs.) içerir. Koşullar proje öğeleri (proje öğeleri olarak kuralları tanımlar tarafından kullanılan başka bir deyişle, öğesi türleri) için desteklenmez.

Tümü aynı olsalar bile, meta veriler her yapılandırma için yapılandırma koşullar olması gerekir. Örneğin:

   ```xml
   <ItemGroup>
     <ClCompile Include="stdafx.cpp">
       <TreatWarningAsError Condition="‘$(Configuration)|$(Platform)’==’Debug|Win32’">true</TreatWarningAsError>
       <TreatWarningAsError Condition="‘$(Configuration)|$(Platform)’==’Debug|x64’">true</TreatWarningAsError>
     </ClCompile>
   </ItemGroup>
   ```

Visual C++ proje sistem şu anda proje öğelerinde joker karakterleri desteklemez.

   ```xml
   <ItemGroup>
     <ClCompile Include="*.cpp"> <!--Error-->
   </ItemGroup>
   ```

Visual C++ proje sistemi proje öğelerinde makroları şu anda desteklemiyor.

   ```xml
   <ItemGroup>
     <ClCompile Include="$(IntDir)\generated.cpp"> <!--not guaranteed to work in all scenarios-->
   </ItemGroup>
   ```

Başvurular bir ItemGroup belirtilir ve bu sınırlamalara sahiptir:

- Başvuruları koşulları desteklemez.
- Meta verilere başvurur koşulları desteklemez.

### <a name="microsoftcpptargets-import-element"></a>Microsoft.Cpp.targets içeri aktarma öğesi

```xml
<Import Project="$(VCTargetsPath)\Microsoft.Cpp.targets" />
```

(Doğrudan veya içeri aktarmalar aracılığıyla) gibi yapı, Visual C++ hedefleri temiz, vb. tanımlar.

### <a name="extensiontargets-importgroup-element"></a>ExtensionTargets Importgroup öğesi

```xml
<ImportGroup Label="ExtensionTargets" />
```

Bu grup, içeri aktarmalar için yapı özelleştirme hedef dosyaları içerir.

## <a name="impact-of-incorrect-ordering"></a>Yanlış sıralama etkisi

Visual Studio IDE proje dosyası sıralama yukarıda açıklanan sahip olunmasına bağlıdır. Bir özellik değeri özellik sayfalarında tanımladığınızda, örneğin, IDE genellikle özellik tanımı boş etiketle özellik grubundaki yerleştirir. Bu, varsayılan değerleri sistem özellik sayfalarında duruma tarafından kullanıcı tanımlı değerler kılınır sağlar. Benzer şekilde, hedef dosya sonunda yukarıda tanımlanan özellikler tüketen beri ve genellikle özelliklerinin kendileri tanımlamayın beri içeri aktarılır. Kullanıcı özellik sayfaları sonra sistem özellik sayfalarını benzer şekilde, içe aktarılan (aracılığıyla dahil **Microsoft.Cpp.props**). Bu, kullanıcı tarafından sistem özellik sayfalarını getirildi tüm varsayılanları geçersiz kılabilir sağlar.

.Vcxproj dosya bu düzeni izlemiyorsa yapı sonuçları beklediğiniz olmayabilir. Örneğin, yanlışlıkla bir sistem özellik sayfası kullanıcı tarafından tanımlanan özellik sayfalarını sonra içe aktarıyorsanız, kullanıcı ayarlarını tarafından sistem özellik sayfalarını kılınır.

Hatta IDE tasarım zamanı deneyimi öğelerin doğru sıralaması bazı aşamaya bağlıdır. Örneğin, .vcxproj dosyanızı yoksa `PropertySheets` içe aktarma grubu, IDE içinde kullanıcının oluşturduğu yeni bir özellik sayfası nereye yerleştireceğinizi belirlemek mümkün olmayabilir **özellik Yöneticisi**. Bu bir sistem sayfası tarafından kılınmadı olan bir kullanıcı sayfası neden olabilir. IDE tarafından kullanılan buluşsal yöntem .vcxproj dosya düzeninde küçük tutarsızlıklar dayanabileceği karşın, bu makalenin önceki bölümlerinde gösterilen yapısından cluster_count_prıor değil önemle tavsiye edilir.

## <a name="how-the-ide-uses-element-labels"></a>IDE öğesi etiketleri kullanma

Ayarladığınızda IDE içinde **UseOfAtl** genel özellik sayfası özelliğinde yazılmış proje dosyasında yapılandırma özelliği gruba sırada **TargetName** aynı özellik sayfasında özelliği Her yapılandırma için etiket daha az özellik grubuna yazılır. Özellik sayfasının xml dosyası her bir özellik yazılacağı hakkında bilgi için Visual Studio bakar. İçin **genel** özellik sayfası (Visual Studio Enterprise Edition İngilizce sürümünü sahip oldukları varsayılarak), bu dosya `%ProgramFiles(x86)%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\VC\VCTargets\1033\general.xml`. Özellik sayfası XML kural dosyasını bir kural ve tüm özelliklerini statik bilgilerini tanımlar. Böyle bir bilgi parçasını tercih edilen bir kural özelliğine hedef dosyasındaki (değerini yazılacağı dosya) konumudur. Tercih edilen konumu proje dosyası öğelerini etiket özniteliği tarafından belirtilen.

## <a name="property-sheet-layout"></a>Özellik sayfası düzeni

Aşağıdaki XML parçacığını bir özellik sayfası (.props) dosyasının en az bir düzen ' dir. .Vcxproj dosyasına benzer ve .props öğeleri işlevselliğini önceki tartışma çıkarsanabileceği.

```xml
<Project ToolsVersion="4.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <ImportGroup Label="PropertySheets" />
  <PropertyGroup Label="UserMacros" />
  <PropertyGroup />
  <ItemDefinitionGroup />
  <ItemGroup />
</Project>
```

Kendi özellik sayfası yapmak için .props dosyalardan birini VCTargets klasöründe kopyalayıp amaçlarınız için değiştirebilirsiniz. Visual Studio 2017 Enterprise edition için varsayılan VCTargets yoldur `%ProgramFiles%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\VC\VCTargets`.

## <a name="see-also"></a>Ayrıca bkz.

[Proje Özellikleriyle Çalışma](working-with-project-properties.md)  
[Özellik Sayfası XML Dosyaları](property-page-xml-files.md)  
