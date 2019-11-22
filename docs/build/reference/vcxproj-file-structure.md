---
title: .vcxproj ve .props dosya yapısı
ms.date: 05/16/2019
helpviewer_keywords:
- .vcxproj file structure
ms.assetid: 14d0c552-29db-480e-80c1-7ea89d6d8e9c
ms.openlocfilehash: a24349980e9395257f20fcfcc0987883060a7c1d
ms.sourcegitcommit: 069e3833bd821e7d64f5c98d0ea41fc0c5d22e53
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74303130"
---
# <a name="vcxproj-and-props-file-structure"></a>.vcxproj ve .props dosya yapısı

[MSBuild](../msbuild-visual-cpp.md) , Visual Studio 'daki varsayılan proje sistemidir; Visual C++ 'te **Dosya** > **Yeni proje** ' yi seçtiğinizde, ayarları, uzantısı `.vcxproj`olan bir XML proje dosyasında depolanan bir MSBuild projesi oluşturuyorsunuz. Proje dosyası, ayarların saklanabileceği. props dosyalarını ve. targets dosyalarını da içeri aktarabilir. Çoğu durumda, proje dosyasını el ile düzenlemeniz gerekmez ve aslında MSBuild 'in iyi bir şekilde anlaşılmadığı müddetçe el ile düzenlememelisiniz. Her mümkün olduğunda proje ayarlarını değiştirmek için Visual Studio özellik sayfalarını kullanmanız gerekir (bkz. [Visual C++ Studio 'da derleyici ve derleme özelliklerini ayarlama](../working-with-project-properties.md). Ancak, bazı durumlarda bir proje dosyasını veya özellik sayfasını el ile değiştirmeniz gerekebilir. Bu senaryolar için, bu makale dosyanın yapısıyla ilgili temel bilgileri içerir.

**Önemli:**

Bir. vcxproj dosyasını el ile düzenlemeyi seçerseniz, bu olgulara dikkat edin:

1. Dosyanın yapısı, bu makalede açıklanan, önceden tanımlanmış bir biçimde gelmelidir.

1. Visual Studio C++ proje sistemi şu anda proje öğelerinde joker karakterleri desteklemiyor. Örneğin, bu desteklenmez:

   ```xml
   <ClCompile Include="*.cpp"/>
   ```

1. Visual Studio C++ proje sistemi şu anda proje öğesi yollarında makroları desteklemez. Örneğin, bu desteklenmez:

   ```xml
   <ClCompile Include="$(IntDir)\generated.cpp"/>
   ```

   "Desteklenmiyor", makroların IDE 'deki tüm işlemler için çalışma garantisi olmadığı anlamına gelir. Farklı yapılandırmalarda değerlerini değiştirolmayan makrolar çalışmalıdır, ancak bir öğe farklı bir filtreye veya projeye taşınırsa korunmayabilir. Farklı yapılandırmalara ilişkin değerlerini değiştiren makrolar, IDE proje öğesi yollarının farklı proje yapılandırmalarında farklı olmasına neden olmadığı için sorunlara neden olur.

1. **Proje Özellikleri iletişim kutusunda** düzenlendiğinde proje özelliklerinin doğru şekilde eklenmesini, kaldırılmasını veya değiştirilmesini sağlamak için, her proje yapılandırması için dosyanın ayrı gruplar içermesi ve koşulların bu biçimde olması gerekir:

   ```xml
   Condition="'$(Configuration)|$(Platform)'=='Debug|Win32'"
   ```

1. Özellik kuralı dosyasında belirtildiği gibi, her bir özellik, doğru etikete sahip olan grupta belirtilmelidir. Daha fazla bilgi için bkz. [özellik sayfası XML kural dosyaları](property-page-xml-files.md).

## <a name="vcxproj-file-elements"></a>. vcxproj dosya öğeleri

Herhangi bir metin veya XML Düzenleyicisi kullanarak bir. vcxproj dosyasının içeriğini inceleyebilirsiniz. Projeyi Çözüm Gezgini ' de projeye sağ tıklayıp, **Projeyi Kaldır** ' ı seçip **foo. vcxproj Düzenle**' yi seçerek Visual Studio 'da görüntüleyebilirsiniz.

Dikkat edilmesi gereken ilk şey, en üst düzey öğelerin belirli bir sırada görünmeişindedir. Örneğin:

- Özellik gruplarının ve öğe tanımı gruplarının çoğu, Microsoft. cpp. default. props için içeri aktarma işleminden sonra oluşur.

- Tüm hedefler dosyanın sonuna aktarılır.

- Her biri benzersiz bir etikete sahip birden çok özellik grubu vardır ve bunlar belirli bir sırada oluşur.

MSBuild sıralı bir değerlendirme modelini temel aldığı için proje dosyasındaki öğelerin sırası çok önemlidir.  Tüm içeri aktarılan. props ve. targets dosyaları dahil olmak üzere proje dosyanız bir özelliğin birden çok tanımından oluşuyorsa, son tanım önceki değerleri geçersiz kılar. Aşağıdaki örnekte, "XYZ" değeri derleme sırasında ayarlanacak, çünkü MSBUild altyapısı değerlendirme sırasında en son ile karşılaştığında.

```xml
  <MyProperty>abc</MyProperty>
  <MyProperty>xyz</MyProperty>
```

Aşağıdaki kod parçacığında en az bir. vcxproj dosyası gösterilmektedir. Visual Studio tarafından oluşturulan herhangi bir. vcxproj dosyası, bu üst düzey MSBuild öğelerini içerir ve bu sırada görünür (ancak, her bir en üst düzey öğenin birden çok kopyasını içerse de). `Label` özniteliklerin yalnızca Visual Studio tarafından yalnızca düzenlenmek üzere signas iletileri olarak kullanılan rastgele Etiketler olduğunu unutmayın; başka bir işlevi yoktur.

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

### <a name="project-element"></a>Proje öğesi

```xml
<Project DefaultTargets="Build" ToolsVersion="4.0" xmlns='http://schemas.microsoft.com/developer/msbuild/2003' >
```

kök düğüm `Project`. Bu, kullanılacak MSBuild sürümünü ve ayrıca bu dosya MSBuild. exe ' ye geçirildiğinde yürütülecek varsayılan hedefi belirler.

### <a name="projectconfigurations-itemgroup-element"></a>ProjectConfigurations ItemGroup öğesi

```xml
<ItemGroup Label="ProjectConfigurations" />
```

`ProjectConfigurations` proje yapılandırma açıklamasını içerir. Örnekler hata ayıklaması | Win32, yayın | Win32, hata ayıkla | ARM ve benzeri. Birçok proje ayarı belirli bir yapılandırmaya özgüdür. Örneğin, büyük olasılıkla bir yayın derlemesi için en iyi duruma getirme özelliklerini ayarlamak isteyeceksiniz, ancak bir hata ayıklama derlemesi.

`ProjectConfigurations` öğesi grubu derleme zamanında kullanılmaz. Visual Studio IDE, projeyi yüklemek için bunu gerektirir. Bu öğe grubu bir. props dosyasına taşınabilir ve. vcxproj dosyasına aktarılabilir. Ancak, bu durumda, yapılandırma eklemeniz veya kaldırmanız gerekirse,. props dosyasını el ile düzenlemeniz gerekir. IDE 'yi kullanamazsınız.

### <a name="projectconfiguration-elements"></a>ProjectConfiguration öğeleri

Aşağıdaki kod parçacığında bir proje yapılandırması gösterilmektedir. Bu örnekte, ' Debug | x64 ' yapılandırma adıdır. Proje yapılandırma adı $ (yapılandırma) | $ (Platform) biçiminde olmalıdır. Proje yapılandırma düğümü iki özelliğe sahip olabilir: yapılandırma ve platform. Yapılandırma etkin olduğunda, bu özellikler burada belirtilen değerlerle otomatik olarak ayarlanır.

```xml
<ProjectConfiguration Include="Debug|x64">
  <Configuration>Debug</Configuration>
  <Platform>x64</Platform>
</ProjectConfiguration>
```

IDE, tüm ProjectConfiguration öğelerinde kullanılan yapılandırma ve platform değerlerinin herhangi bir birleşimi için bir proje yapılandırması bulmayı bekler. Bu, genellikle bir projenin bu gereksinimi karşılamak için anlamlı proje yapılandırmalarına sahip olabileceği anlamına gelir. Örneğin, bir proje şu yapılandırmalara sahipse:

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

`Globals` ProjectGuid, RootNamespace ve ApplicationType/ApplicationTypeRevision gibi proje düzeyi ayarları içerir. Son iki genellikle hedef işletim sistemini tanımlar. Bir proje yalnızca bir işletim sistemini hedefleyebilir çünkü başvuruları ve proje öğeleri şu anda koşullara sahip olamaz. Bu özellikler genellikle proje dosyasının başka bir yerinde geçersiz kılınmaz. Bu grup, yapılandırmaya bağımlı değildir ve bu nedenle genellikle proje dosyasında yalnızca bir genel grup bulunur.

### <a name="microsoftcppdefaultprops-import-element"></a>Microsoft. cpp. default. props Içeri aktarma öğesi

```xml
<Import Project="$(VCTargetsPath)\Microsoft.Cpp.default.props" />
```

**Microsoft. cpp. default. props** Özellik sayfası Visual Studio ile birlikte gelir ve değiştirilemez. Proje için varsayılan ayarları içerir. Varsayılanlar, ApplicationType öğesine göre farklılık gösterebilir.

### <a name="configuration-propertygroup-elements"></a>Yapılandırma PropertyGroup öğeleri

```xml
<PropertyGroup Label="Configuration" />
```

Bir `Configuration` özellik grubu, bağlı bir yapılandırma koşuluna sahiptir (örneğin, `Condition="'$(Configuration)|$(Platform)'=='Debug|Win32'"`) ve her yapılandırma için birden fazla kopyaya gelir. Bu özellik grubu, belirli bir yapılandırma için ayarlanan özellikleri barındırır. Yapılandırma özellikleri Platformaraç takımını içerir ve ayrıca **Microsoft. cpp. props**içindeki Sistem özellik sayfalarının eklenmesini denetler. Örneğin, `<CharacterSet>Unicode</CharacterSet>`özelliğini tanımlarsanız, ardından sistem özellik sayfası **Microsoft. Cpp. unicodesupport. props** dahil edilecek. **Microsoft. cpp. props**' u incelemenizi istiyorsanız şu satırı görürsünüz: `<Import Condition="'$(CharacterSet)' == 'Unicode'" Project="$(VCTargetsPath)\microsoft.Cpp.unicodesupport.props" />`.

### <a name="microsoftcppprops-import-element"></a>Microsoft. cpp. props Içeri aktarma öğesi

```xml
<Import Project="$(VCTargetsPath)\Microsoft.Cpp.props" />
```

**Microsoft. cpp. props** Özellik sayfası (doğrudan veya içeri aktarmalar aracılığıyla), derleyicinin En Iyi duruma getirme ve uyarı düzeyi özellikleri, MIDL aracının TypeLibraryName özelliği vb. gibi birçok araca özgü özellik için varsayılan değerleri tanımlar. Ayrıca, yukarıdaki özellik grubunda tanımlanan yapılandırma özelliklerine göre çeşitli sistem özellik sayfalarını içeri aktarır.

### <a name="extensionsettings-importgroup-element"></a>ExtensionSettings ImportGroup öğesi

```xml
<ImportGroup Label="ExtensionSettings" />
```

`ExtensionSettings` grubu, yapı özelleştirmelerinin parçası olan özellik sayfaları için içeri aktarmaları içerir. Yapı özelleştirmesi en fazla üç dosya tarafından tanımlanır:. targets dosyası, bir. props dosyası ve bir. xml dosyası. Bu içeri aktarma grubu. props dosyası için içeri aktarmaları içerir.

### <a name="propertysheets-importgroup-elements"></a>Propertysayfalarý ImportGroup öğeleri

```xml
<ImportGroup Label="PropertySheets" />
```

`PropertySheets` grubu, Kullanıcı Özellik sayfaları için içeri aktarmaları içerir. Bunlar, Visual Studio 'daki Özellik Yöneticisi görünümü aracılığıyla eklediğiniz Özellik sayfalarıdır. Bu içeri aktarmaların listelendiği sıra önemlidir ve Özellik Yöneticisi yansıtılır. Proje dosyası normalde her proje yapılandırması için bir tane olan bu türdeki içeri aktarma grubunun birden fazla örneğini içerir.

### <a name="usermacros-propertygroup-element"></a>UserMacros PropertyGroup öğesi

```xml
<PropertyGroup Label="UserMacros" />
```

`UserMacros` yapı işleminizi özelleştirmek için kullanılan değişkenler olarak oluşturduğunuz özellikleri içerir. Örneğin, özel çıkış yolunuzu $ (CustomOutputPath) olarak tanımlamak için bir Kullanıcı makrosu tanımlayabilir ve bunu diğer değişkenleri tanımlamak için kullanabilirsiniz. Bu özellik grubu, bu tür özellikleri barındırır. Visual Studio 'da bu grubun proje dosyasında doldurulmadığını unutmayın çünkü görsel C++ , yapılandırma için Kullanıcı makrolarını desteklemez. Kullanıcı makroları özellik sayfalarında desteklenir.

### <a name="per-configuration-propertygroup-elements"></a>Yapılandırma başına PropertyGroup öğeleri

```xml
<PropertyGroup />
```

Her proje yapılandırması için bir yapılandırma başına, bu özellik grubunun birden çok örneği vardır. Her özellik grubuna bir yapılandırma koşulu eklenmiş olmalıdır. Herhangi bir yapılandırma eksikse, **Proje özellikleri** iletişim kutusu doğru çalışmaz. Yukarıdaki Özellik gruplarının aksine, bu bir etiketi yoktur. Bu grup proje yapılandırma düzeyi ayarlarını içerir. Bu ayarlar, belirtilen öğe grubunun parçası olan tüm dosyalar için geçerlidir. Derleme özelleştirme öğesi tanımı meta verileri buradan başlatılır.

Bu PropertyGroup `<Import Project="$(VCTargetsPath)\Microsoft.Cpp.props" />` sonrasında gelmelidir ve önce etiketi olmayan başka bir PropertyGroup olmamalıdır (Aksi halde proje özellikleri düzenlemesi doğru çalışmaz).

### <a name="per-configuration-itemdefinitiongroup-elements"></a>Yapılandırma başına ItemDefinitionGroup öğeleri

```xml
<ItemDefinitionGroup />
```

Öğe tanımlarını içerir. Bunlar, tek tek yapılandırma PropertyGroup öğeleriyle aynı koşul kurallarını izlemelidir.

### <a name="itemgroup-elements"></a>ItemGroup öğeleri

```xml
<ItemGroup />
```

Projedeki öğeleri (kaynak dosyaları, vb.) içerir. Koşullar proje öğeleri (yani, kural tanımlarına göre proje öğeleri olarak kabul edilen öğe türleri) için desteklenmez.

Verilerin tümünün aynı olsa bile her yapılandırma için yapılandırma koşulları olmalıdır. Örneğin:

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

Derleme, temizleme vb. gibi görsel C++ hedefleri tanımlar (doğrudan veya aracılığıyla içeri aktarmaları).

### <a name="extensiontargets-importgroup-element"></a>ExtensionTargets ImportGroup öğesi

```xml
<ImportGroup Label="ExtensionTargets" />
```

Bu grup, derleme özelleştirmesi hedef dosyaları için içeri aktarmaları içerir.

## <a name="impact-of-incorrect-ordering"></a>Yanlış sıralamanın etkisi

Visual Studio IDE, yukarıda açıklanan sıralamaya sahip proje dosyasına bağlıdır. Örneğin, özellik sayfalarında bir özellik değeri tanımladığınızda, IDE, özellik tanımını genellikle boş etikete sahip özellik grubuna yerleştirir. Bu, sistem özellik sayfalarında getirilen varsayılan değerlerin Kullanıcı tanımlı değerler tarafından geçersiz kılınmasını sağlar. Benzer şekilde, hedef dosyalar, yukarıda tanımlanan özellikleri tükettiği ve genellikle özellikleri tanımlamadığı için son olarak içeri aktarılır. Benzer şekilde, Kullanıcı Özellik sayfaları, sistem Özellik sayfaları ( **Microsoft. cpp. props**aracılığıyla bulunur) sonrasında içeri aktarılır. Bu, kullanıcının sistem Özellik sayfaları tarafından getirilen tüm Varsayılanları geçersiz kılabilmesini sağlar.

Bir. vcxproj dosyası bu düzeni izlemmezse, yapı sonuçları beklediğiniz gibi olmayabilir. Örneğin, Kullanıcı tarafından tanımlanan özellik sayfalarından sonra bir sistem özellik sayfasını yanlışlıkla içeri aktarırsanız, Kullanıcı ayarları sistem Özellik sayfaları tarafından geçersiz kılınır.

IDE tasarım zamanı deneyimi bile, öğelerin doğru sıralamasına göre bir ölçüde farklılık gösterir. Örneğin,. vcxproj dosyanızda `PropertySheets` içeri aktarma grubu yoksa, IDE, kullanıcının **Özellik Yöneticisi**oluşturduğu yeni bir özellik sayfasının nereye yerleştirileceğini belirleyemeyebilir. Bu, bir Kullanıcı sayfasının bir sistem sayfası tarafından geçersiz kılınmasına neden olabilir. IDE tarafından kullanılan buluşsal yöntem. vcxproj dosya düzeninde küçük tutarsızlıklara izin verse de, bu makalede daha önce gösterilen yapıdan sapmamak kesinlikle önerilir.

## <a name="how-the-ide-uses-element-labels"></a>IDE 'nin öğe etiketleri nasıl kullanır

IDE 'de, genel özellik sayfasında **useOfATL** özelliğini ayarladığınızda, bu, proje dosyasındaki yapılandırma özellik grubuna yazılır, ancak aynı özellik sayfasındaki **TargetName** özelliği, etiket-daha az yapılandırma özellik grubuna yazılır. Visual Studio her bir özelliğin nereye yazılacağı hakkında bilgi için özellik sayfasının XML dosyasına bakar. **Genel** Özellik sayfası Için (Visual Studio 2019 Enterprise Edition 'ın İngilizce sürümüne sahip olduğunuz varsayılarak), bu dosya `%ProgramFiles(x86)%\Microsoft Visual Studio\2019\Enterprise\Common7\IDE\VC\VCTargets\1033\general.xml`. Özellik sayfası XML kural dosyası, bir kuralla ilgili statik bilgileri ve tüm özelliklerini tanımlar. Bu tür bir bilgi, hedef dosyadaki bir kural özelliğinin tercih edilen konumudur (değerinin yazılacağı dosya). Tercih edilen konum, proje dosyası öğelerinde Label özniteliğiyle belirtilir.

## <a name="property-sheet-layout"></a>Özellik sayfası düzeni

Aşağıdaki XML kod parçacığı, bir özellik sayfası (. props) dosyasının en az düzenidir. . Vcxproj dosyasına benzer ve. props öğelerinin işlevselliği önceki tartışmadan çıkarsanamıyor.

```xml
<Project ToolsVersion="4.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <ImportGroup Label="PropertySheets" />
  <PropertyGroup Label="UserMacros" />
  <PropertyGroup />
  <ItemDefinitionGroup />
  <ItemGroup />
</Project>
```

Kendi özellik sayfanızı oluşturmak için, VCTargets klasöründeki. props dosyalarından birini kopyalayın ve sizin amacınıza göre değiştirin. Visual Studio 2019 Enterprise Edition için varsayılan VCTargets yolu `%ProgramFiles%\Microsoft Visual Studio\2019\Enterprise\Common7\IDE\VC\VCTargets`.

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio’da C++ derleyicisi ve derleme özelliklerini ayarlama](../working-with-project-properties.md)<br/>
[Özellik Sayfası XML Dosyaları](property-page-xml-files.md)
