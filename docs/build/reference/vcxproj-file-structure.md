---
title: .vcxproj ve .props dosya yapısı
description: C++ yerel MSBuild proje System. vcxproj ve. props dosyaları proje bilgilerini depolar.
ms.date: 09/30/2020
helpviewer_keywords:
- .vcxproj file structure
ms.assetid: 14d0c552-29db-480e-80c1-7ea89d6d8e9c
ms.openlocfilehash: 562ef0c1b371d7212f31da1917d19c012e4cbb24
ms.sourcegitcommit: f7fbdc39d73e1fb3793c396fccf7a1602af7248b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/02/2020
ms.locfileid: "91662288"
---
# <a name="vcxproj-and-props-file-structure"></a>`.vcxproj` ve `.props` dosya yapısı

[MSBuild](../msbuild-visual-cpp.md) , Visual Studio 'daki varsayılan proje sistemidir; Visual C++ **Dosya**  >  **Yeni proje** ' yi seçtiğinizde, ayarları uzantısına sahip bir XML proje dosyasında depolanan bir MSBuild projesi oluşturuyorsunuz *`.vcxproj`* . Proje dosyası, *`.props`* ayarların saklanabileceği dosya ve dosyaları da içeri aktarabilir *`.targets`* .

Yalnızca *`.vcxproj`* IDE 'de projeleri oluşturup değiştirmenizi ve mümkün olduğunca el ile düzenlemeden kaçınmanızı öneririz. Çoğu durumda, hiçbir zaman proje dosyasını el ile düzenlemeniz gerekmez. Mümkün olduğunda, proje ayarlarını değiştirmek için Visual Studio özellik sayfalarını kullanmanız gerekir. Daha fazla bilgi için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

IDE 'de mümkün olmayan özelleştirmeler gerekiyorsa, özel props veya hedefler eklemenizi öneririz. Özelleştirmeleri eklemek için kullanışlı olan konumlar, *`Directory.Build.props`* *`Directory.Build.targets`* Tüm MSBuild tabanlı projelerde otomatik olarak içeri aktarılan ve dosyalarıdır.

Bazı durumlarda, hala bir *`.vcxproj`* Proje dosyası veya özellik sayfasını el ile değiştirmeniz gerekebilir. MSBuild 'i iyi anlayabilmeniz ve bu makaledeki yönergeleri izlemeniz gerekmedikçe el ile düzenlemeniz önerilmez. IDE 'nin dosyaları otomatik olarak yüklemesi ve güncelleştirmesi için *`.vcxproj`* , bu dosyaların diğer MSBuild proje dosyalarına uygulanmamaları için bazı kısıtlamalar vardır. Bunlar el ile düzenlenmek üzere tasarlanmadı. Hatalar IDE 'nin çökmesine veya beklenmedik yollarla davranmasına neden olabilir.

El ile düzenlenen senaryolar için, bu makale ve ilgili dosyaların yapısıyla ilgili temel bilgileri içerir *`.vcxproj`* .

**Önemli:**

Bir dosyayı el ile düzenlemeyi seçerseniz *`.vcxproj`* , bu olgulara dikkat edin:

- Dosyanın yapısı, bu makalede açıklanan, önceden tanımlanmış bir biçimde gelmelidir.

- Visual Studio C++ proje sistemi şu anda doğrudan proje öğelerinde joker karakterler veya listeler desteklemez. Örneğin, bu formlar desteklenmez:

   ```xml
   <ItemGroup>
     <None Include="*.txt"/>
     <ClCompile Include="a.cpp;b.cpp"/>
   </ItemGroup>
   ```

   Projelerde joker karakter desteği ve olası geçici çözümler hakkında daha fazla bilgi için bkz. [ `.vcxproj` Dosyalar ve joker karakterler](vcxproj-files-and-wildcards.md).

- Visual Studio C++ proje sistemi şu anda proje öğesi yollarında makroları desteklemez. Örneğin, bu form desteklenmez:

   ```xml
   <ItemGroup>
     <ClCompile Include="$(IntDir)\generated.cpp"/>
   </ItemGroup>
   ```

   "Desteklenmiyor", makroların IDE 'deki tüm işlemler için çalışma garantisi olmadığı anlamına gelir. Farklı yapılandırmalarda değerlerini değiştirolmayan makrolar çalışmalıdır, ancak bir öğe farklı bir filtreye veya projeye taşınırsa korunmayabilir. Farklı yapılandırmaların değerlerini değiştiren makrolar sorunlara neden olur. Bunun nedeni, IDE 'nin proje öğesi yollarının farklı proje yapılandırmalarında farklı olmasını beklemez.

- Proje **özellikleri** iletişim kutusunda düzenlerken proje özelliklerini doğru bir şekilde eklemek, kaldırmak veya değiştirmek için, her proje yapılandırması için dosyanın ayrı gruplar içermesi gerekir. Koşulların bu biçimde olması gerekir:

   ```xml
   Condition="'$(Configuration)|$(Platform)'=='Debug|Win32'"
   ```

- Özellik kuralı dosyasında belirtildiği gibi, her bir özellik, grupta doğru etiketi ile belirtilmelidir. Daha fazla bilgi için bkz. [özellik sayfası XML kural dosyaları](property-page-xml-files.md).

## <a name="vcxproj-file-elements"></a>`.vcxproj` dosya öğeleri

*`.vcxproj`* Herhangi bir metin veya XML Düzenleyicisi kullanarak bir dosyanın içeriğini inceleyebilirsiniz. Projeyi Çözüm Gezgini ' de projeye sağ tıklayıp, **Projeyi Kaldır** ' ı seçip **foo. vcxproj Düzenle**' yi seçerek Visual Studio 'da görüntüleyebilirsiniz.

Dikkat edilmesi gereken ilk şey, en üst düzey öğelerin belirli bir sırada görünmeişindedir. Örnek:

- Özellik gruplarının ve öğe tanımı gruplarının çoğu, Microsoft. cpp. default. props için içeri aktarma işleminden sonra oluşur.

- Tüm hedefler dosyanın sonuna aktarılır.

- Her biri benzersiz bir etikete sahip birden çok özellik grubu vardır ve bunlar belirli bir sırada oluşur.

MSBuild sıralı bir değerlendirme modelini temel aldığı için proje dosyasındaki öğelerin sırası önemli değildir.  Tüm içeri aktarılan ve dosyalar dahil olmak üzere proje *`.props`* dosyanız *`.targets`* bir özelliğin birden çok tanımından oluşuyorsa, son tanım önceki değerleri geçersiz kılar. Aşağıdaki örnekte, "XYZ" değeri derleme sırasında ayarlanacak, çünkü MSBUild altyapısı değerlendirme sırasında en son ile karşılaştığında.

```xml
  <MyProperty>abc</MyProperty>
  <MyProperty>xyz</MyProperty>
```

Aşağıdaki kod parçacığında en az bir *`.vcxproj`* Dosya gösterilmektedir. *`.vcxproj`* Visual Studio tarafından oluşturulan herhangi bir dosya, bu üst düzey MSBuild öğelerini içerir. Ayrıca, bu sırayla görünürler, ancak bu tür bir en üst düzey öğenin birden çok kopyasını içerebilirler. Herhangi bir `Label` öznitelik, yalnızca Visual Studio tarafından düzenlenmek üzere signas iletileri olarak kullanılan rastgele etiketlerdir; başka bir işlevi yoktur.

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

Aşağıdaki bölümler, bu öğelerin her birinin amacını ve neden bu şekilde sıralı olduğunu anlatmaktadır:

### <a name="project-element"></a>Project öğesi

```xml
<Project DefaultTargets="Build" ToolsVersion="4.0" xmlns='http://schemas.microsoft.com/developer/msbuild/2003' >
```

`Project` kök düğümdür. Bu, kullanılacak MSBuild sürümünü ve ayrıca bu dosya MSBuild.exe geçirildiğinde yürütülecek varsayılan hedefi belirtir.

### <a name="projectconfigurations-itemgroup-element"></a>ProjectConfigurations ItemGroup öğesi

```xml
<ItemGroup Label="ProjectConfigurations" />
```

`ProjectConfigurations` Proje yapılandırma açıklamasını içerir. Örnekler hata ayıklaması | Win32, yayın | Win32, hata ayıkla | ARM ve benzeri. Birçok proje ayarı belirli bir yapılandırmaya özgüdür. Örneğin, büyük olasılıkla bir yayın derlemesi için en iyi duruma getirme özelliklerini ayarlamak isteyeceksiniz, ancak bir hata ayıklama derlemesi.

`ProjectConfigurations`Öğe grubu derleme zamanında kullanılmıyor. Visual Studio IDE, projenin yüklenmesini gerektirir. Bu öğe grubu bir *`.props`* dosyaya taşınabilir ve *`.vcxproj`* dosyaya aktarılabilir. Ancak, bu durumda, yapılandırma eklemeniz veya kaldırmanız gerekirse, dosyayı el ile düzenlemeniz gerekir *`.props`* ; IDE 'yi kullanamazsınız.

### <a name="projectconfiguration-elements"></a>ProjectConfiguration öğeleri

Aşağıdaki kod parçacığında bir proje yapılandırması gösterilmektedir. Bu örnekte, ' Debug | x64 ' yapılandırma adıdır. Proje yapılandırma adı biçiminde olmalıdır `$(Configuration)|$(Platform)` . `ProjectConfiguration`Düğüm iki özelliğe sahip olabilir: `Configuration` ve `Platform` . Bu özellikler, yapılandırma etkin olduğunda burada belirtilen değerlerle otomatik olarak ayarlanır.

```xml
<ProjectConfiguration Include="Debug|x64">
  <Configuration>Debug</Configuration>
  <Platform>x64</Platform>
</ProjectConfiguration>
```

IDE, `Configuration` `Platform` Tüm öğelerinde kullanılan ve değerlerinin birleşimi için bir proje yapılandırması bulmayı bekler `ProjectConfiguration` . Genellikle, bir projenin bu gereksinimi karşılamak için anlamlı proje yapılandırmalarına sahip olabileceği anlamına gelir. Örneğin, bir proje şu yapılandırmalara sahipse:

- Hata Ayıkla | Win

- Perakende | Win

- Özel 32 bit Iyileştirmesi | Win

Ayrıca, "özel 32 bit Iyileştirmesi" x64 için anlamlı olsa da, bu yapılandırmalara de sahip olmalıdır:

- Hata Ayıkla | x64

- Perakende | x64

- Özel 32 bit Iyileştirmesi | x64

**Çözüm Configuration Manager**herhangi bir yapılandırma için derleme ve dağıtma komutlarını devre dışı bırakabilirsiniz.

### <a name="globals-propertygroup-element"></a>Globals PropertyGroup öğesi

```xml
<PropertyGroup Label="Globals" />
```

`Globals``ProjectGuid`, ve veya gibi proje düzeyi ayarlarını içerir `RootNamespace` `ApplicationType` `ApplicationTypeRevision` . Son iki genellikle hedef işletim sistemini tanımlar. Bir proje yalnızca tek bir işletim sistemini hedefleyebilir çünkü şu anda, başvurular ve proje öğeleri koşullara sahip olamaz. Bu özellikler genellikle proje dosyasının başka bir yerinde geçersiz kılınmaz. Bu grup, yapılandırmaya bağımlı değildir ve genellikle `Globals` Proje dosyasında yalnızca bir grup bulunur.

### <a name="microsoftcppdefaultprops-import-element"></a>Microsoft. cpp. default. props Içeri aktarma öğesi

```xml
<Import Project="$(VCTargetsPath)\Microsoft.Cpp.default.props" />
```

**Microsoft. cpp. default. props** Özellik sayfası Visual Studio ile birlikte gelir ve değiştirilemez. Proje için varsayılan ayarları içerir. Varsayılanlar, ApplicationType öğesine göre farklılık gösterebilir.

### <a name="configuration-propertygroup-elements"></a>Yapılandırma PropertyGroup öğeleri

```xml
<PropertyGroup Label="Configuration" />
```

Bir `Configuration` özellik grubu, bağlı bir yapılandırma koşuluna sahiptir (gibi `Condition="'$(Configuration)|$(Platform)'=='Debug|Win32'"` ) ve her yapılandırma için birden fazla kopyaya gelir. Bu özellik grubu, belirli bir yapılandırma için ayarlanan özellikleri barındırır. Yapılandırma özellikleri Platformaraç takımını içerir ve ayrıca **Microsoft. cpp. props**içindeki Sistem özellik sayfalarının eklenmesini denetler. Örneğin, özelliğini tanımlarsanız, `<CharacterSet>Unicode</CharacterSet>` daha sonra sistem özellik sayfası **Microsoft. Cpp. unicodesupport. props** dahil edilecek. **Microsoft. cpp. props**' u incelemenizi istiyorsanız şu satırı görürsünüz: `<Import Condition="'$(CharacterSet)' == 'Unicode'" Project="$(VCTargetsPath)\microsoft.Cpp.unicodesupport.props" />` .

### <a name="microsoftcppprops-import-element"></a>Microsoft. cpp. props Içeri aktarma öğesi

```xml
<Import Project="$(VCTargetsPath)\Microsoft.Cpp.props" />
```

**Microsoft. cpp. props** Özellik sayfası (doğrudan veya içeri aktarmalar aracılığıyla), araca özgü birçok özellik için varsayılan değerleri tanımlar. Örnek olarak derleyicinin En Iyi duruma getirme ve uyarı düzeyi özellikleri, MıDL aracının TypeLibraryName özelliği vb. verilebilir. Ayrıca, özellik grubunda hangi yapılandırma özelliklerinin tanımlandığını temel alan çeşitli sistem özellik sayfalarını içeri aktarır.

### <a name="extensionsettings-importgroup-element"></a>ExtensionSettings ImportGroup öğesi

```xml
<ImportGroup Label="ExtensionSettings" />
```

`ExtensionSettings`Grup, yapı özelleştirmelerinin parçası olan özellik sayfaları için içeri aktarmalar içerir. Yapı özelleştirmesi en fazla üç dosya tarafından tanımlanır: bir *`.targets`* Dosya, *`.props`* dosya ve *`.xml`* dosya. Bu içeri aktarma grubu, dosya için içeri aktarmaları içerir *`.props`* .

### <a name="propertysheets-importgroup-elements"></a>Propertysayfalarý ImportGroup öğeleri

```xml
<ImportGroup Label="PropertySheets" />
```

`PropertySheets`Grup, Kullanıcı Özellik sayfaları için içeri aktarmaları içerir. Bu içeri aktarmalar, Visual Studio 'daki Özellik Yöneticisi görünümü aracılığıyla eklediğiniz Özellik sayfalarıdır. Bu içeri aktarmaların listelendiği sıra önemlidir ve Özellik Yöneticisi yansıtılır. Proje dosyası normalde her proje yapılandırması için bir tane olan bu türdeki içeri aktarma grubunun birden fazla örneğini içerir.

### <a name="usermacros-propertygroup-element"></a>UserMacros PropertyGroup öğesi

```xml
<PropertyGroup Label="UserMacros" />
```

`UserMacros` Yapı işleminizi özelleştirmek için kullanılan değişkenler olarak oluşturduğunuz özellikleri içerir. Örneğin, özel çıkış yolunuzu $ (CustomOutputPath) olarak tanımlamak için bir Kullanıcı makrosu tanımlayabilir ve bunu diğer değişkenleri tanımlamak için kullanabilirsiniz. Bu özellik grubu, bu tür özellikleri barındırır. Visual Studio 'da, Visual C++ yapılandırma için Kullanıcı makrolarını desteklemediğinden, bu grup proje dosyasında doldurulmaz. Kullanıcı makroları özellik sayfalarında desteklenir.

### <a name="per-configuration-propertygroup-elements"></a>Yapılandırma başına PropertyGroup öğeleri

```xml
<PropertyGroup />
```

Her proje yapılandırması için bir yapılandırma başına, bu özellik grubunun birden çok örneği vardır. Her özellik grubuna bir yapılandırma koşulu eklenmiş olmalıdır. Herhangi bir yapılandırma eksikse, **Proje özellikleri** iletişim kutusu doğru çalışmaz. Daha önce listelenen özellik gruplarının aksine, bu bir etiketi yoktur. Bu grup proje yapılandırma düzeyi ayarlarını içerir. Bu ayarlar, belirtilen öğe grubunun parçası olan tüm dosyalar için geçerlidir. Derleme özelleştirme öğesi tanımı meta verileri buradan başlatılır.

Bu PropertyGroup öğesinden sonra gelmelidir `<Import Project="$(VCTargetsPath)\Microsoft.Cpp.props" />` ve önce etiketi olmayan başka bir PropertyGroup olmamalıdır (Aksi halde proje özellikleri düzenlemesi doğru çalışmaz).

### <a name="per-configuration-itemdefinitiongroup-elements"></a>Yapılandırma başına ItemDefinitionGroup öğeleri

```xml
<ItemDefinitionGroup />
```

Öğe tanımlarını içerir. Bu tanımlar, etiket-daha az yapılandırma öğeleriyle aynı koşullar kurallarına uymalıdır `PropertyGroup` .

### <a name="itemgroup-elements"></a>ItemGroup öğeleri

```xml
<ItemGroup />
```

`ItemGroup` öğeler, projedeki öğeleri (kaynak dosyalar vb.) içerir. Koşullar proje öğeleri (yani, kural tanımlarına göre proje öğeleri olarak kabul edilen öğe türleri) için desteklenmez.

Her biri aynı olsa bile meta veriler her yapılandırma için yapılandırma koşullarına sahip olmalıdır. Örnek:

```xml
<ItemGroup>
  <ClCompile Include="stdafx.cpp">
    <TreatWarningAsError Condition="'$(Configuration)|$(Platform)'=='Debug|Win32'">true</TreatWarningAsError>
    <TreatWarningAsError Condition="'$(Configuration)|$(Platform)'=='Debug|x64'">true</TreatWarningAsError>
  </ClCompile>
</ItemGroup>
```

Visual Studio C++ proje sistemi şu anda proje öğelerinde joker karakterleri desteklemiyor.

```xml
<ItemGroup>
  <ClCompile Include="*.cpp"> <!--Error-->
</ItemGroup>
```

Visual Studio C++ proje sistemi şu anda proje öğelerindeki makroları desteklemez.

```xml
<ItemGroup>
  <ClCompile Include="$(IntDir)\generated.cpp"> <!--not guaranteed to work in all scenarios-->
</ItemGroup>
```

Başvurular bir ItemGroup içinde belirtilmiştir ve şu sınırlamalara sahiptir:

- Başvurular koşulları desteklemez.

- Başvuru meta verileri, koşulları desteklemez.

### <a name="microsoftcpptargets-import-element"></a>Microsoft. cpp. targets Içeri aktarma öğesi

```xml
<Import Project="$(VCTargetsPath)\Microsoft.Cpp.targets" />
```

Derleme, temizleme vb. gibi C++ hedeflerini tanımlar (doğrudan veya üzerinden içeri aktarmalar).

### <a name="extensiontargets-importgroup-element"></a>ExtensionTargets ImportGroup öğesi

```xml
<ImportGroup Label="ExtensionTargets" />
```

Bu grup, derleme özelleştirmesi hedef dosyaları için içeri aktarmaları içerir.

## <a name="impact-of-incorrect-ordering"></a>Yanlış sıralamanın etkisi

Visual Studio IDE, daha önce açıklanan sıralamaya sahip proje dosyasına bağlıdır. Örneğin, özellik sayfalarında bir özellik değeri tanımladığınızda, IDE, özellik tanımını genellikle boş etikete sahip özellik grubuna yerleştirir. Bu sıralama, sistem özellik sayfalarında getirilen varsayılan değerlerin Kullanıcı tanımlı değerler tarafından geçersiz kılınmasını sağlar. Benzer şekilde, hedef dosyalar, daha önce tanımlanan özellikleri tükettiği ve genellikle özellikleri tanımlamadığı için son olarak içeri aktarılır. Benzer şekilde, Kullanıcı Özellik sayfaları, sistem özellik sayfalarından sonra içeri aktarılır (tarafından dahildir *`Microsoft.Cpp.props`* ). Bu sipariş, kullanıcının sistem Özellik sayfaları tarafından getirilen tüm Varsayılanları geçersiz kılabilmesini sağlar.

Bir *`.vcxproj`* dosya bu düzeni izlemmezse, yapı sonuçları beklediğiniz gibi olmayabilir. Örneğin, Kullanıcı tarafından tanımlanan özellik sayfalarından sonra yanlışlıkla bir sistem özellik sayfası aktarırsanız, Kullanıcı ayarları sistem Özellik sayfaları tarafından geçersiz kılınır.

IDE tasarım zamanı deneyimi, öğelerin doğru sıralamasına göre bir ölçüde farklılık gösterir. Örneğin, *`.vcxproj`* dosyanızda `PropertySheets` içeri aktarma grubu yoksa, IDE, kullanıcının **Özellik Yöneticisi**içinde oluşturduğu yeni bir özellik sayfasının nereye yerleştirileceğini tespit edemeyebilir. Bir sistem sayfası tarafından geçersiz kılınmakta olan bir Kullanıcı sayfasının oluşmasına neden olabilir. IDE tarafından kullanılan buluşsal yöntem dosya düzeninde küçük tutarsızlıklara izin verse de *`.vcxproj`* , bu makalede daha önce gösterilen yapıdan sapmamanızı öneririz.

## <a name="how-the-ide-uses-element-labels"></a>IDE 'nin öğe etiketleri nasıl kullanır

IDE 'de, genel özellik sayfasında **useOfATL** özelliğini ayarladıktan sonra proje dosyasındaki yapılandırma özelliği grubuna yazılır. Aynı özellik sayfasındaki **TargetName** özelliği, etiket-daha az yapılandırma özelliği grubuna yazılır. Visual Studio her bir özelliğin nereye yazılacağı hakkında bilgi için özellik sayfasının XML dosyasına bakar. **Genel** Özellik sayfası Için, Visual Studio 2019 Enterprise Edition 'ın İngilizce sürümüne sahip olduğunuz varsayılarak, bu dosya olur `%ProgramFiles(x86)%\Microsoft Visual Studio\2019\Enterprise\Common7\IDE\VC\VCTargets\1033\general.xml` . Özellik sayfası XML kural dosyası, bir kuralla ilgili statik bilgileri ve tüm özelliklerini tanımlar. Bu tür bir bilgi, hedef dosyadaki bir kural özelliğinin tercih edilen konumudur (değerinin yazılacağı dosya). Tercih edilen konum, proje dosyası öğelerinde Label özniteliğiyle belirtilir.

## <a name="property-sheet-layout"></a>Özellik sayfası düzeni

Aşağıdaki XML kod parçacığı, bir özellik sayfası (. props) dosyasının en az düzenidir. Bir *`.vcxproj`* dosyaya benzer ve *`.props`* öğelerin işlevselliği önceki tartışmadan çıkarsanamıyor.

```xml
<Project ToolsVersion="4.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <ImportGroup Label="PropertySheets" />
  <PropertyGroup Label="UserMacros" />
  <PropertyGroup />
  <ItemDefinitionGroup />
  <ItemGroup />
</Project>
```

Kendi özellik sayfanızı oluşturmak için, *`.props`* klasördeki dosyalardan birini kopyalayın ve sizin amacınıza göre *`VCTargets`* değiştirin. Visual Studio 2019 Enterprise Edition için varsayılan *`VCTargets`* yol olur `%ProgramFiles%\Microsoft Visual Studio\2019\Enterprise\Common7\IDE\VC\VCTargets` .

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio 'da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md)\
[Özellik sayfası XML dosyaları](property-page-xml-files.md)\
[`.vcxproj` dosyalar ve joker karakterler](vcxproj-files-and-wildcards.md)
