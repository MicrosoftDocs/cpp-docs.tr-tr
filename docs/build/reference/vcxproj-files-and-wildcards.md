---
title: . vcxproj dosyaları ve joker karakterler
description: C++ yerel MSBuild proje System. vcxproj dosyaları, joker karakterleri işler.
ms.date: 09/30/2020
helpviewer_keywords:
- .vcxproj file structure
ms.assetid: 14d0c552-29db-480e-80c1-7ea89d6d8e9c
ms.openlocfilehash: 23d36a63f328e14cca59d1d57838173b4dcb0954
ms.sourcegitcommit: f7fbdc39d73e1fb3793c396fccf7a1602af7248b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/02/2020
ms.locfileid: "91662884"
---
# <a name="vcxproj-files-and-wildcards"></a>`.vcxproj` dosyalar ve joker karakterler

Visual Studio IDE, dosyalardaki proje öğelerinde belirli yapıları desteklemez *`.vcxproj`* . Bu desteklenmeyen yapılar joker karakter, noktalı virgülle ayrılmış listeler veya birden çok dosyaya genişlemekte olan MSBuild makrolarını içerir. `.vcxproj`C++ Derlemeleriyle ilgili proje sistemi MSBuild 'ten daha kısıtlayıcıdır. Her proje öğesinin kendi MSBuild öğesine sahip olması gerekir. Dosya biçimi hakkında daha fazla bilgi için `.vcxproj` bkz. [ `.vcxproj` ve `.props` dosya yapısı](vcxproj-file-structure.md).

Bu yapı örnekleri IDE tarafından desteklenmez:

```xml
<ItemGroup>
  <None Include="*.txt">
  <ClCompile Include="a.cpp;b.cpp"/>
  <ClCompile Include="@(SomeItems)" />
</ItemGroup>
```

`.vcxproj`Bu yapıları içeren bir proje dosyası IDE 'de yüklenirse, proje ilk başta çalışıyor görünebilir. Ancak, sorunlar büyük olasılıkla proje Visual Studio tarafından değiştirildiğidir ve daha sonra diskte kaydedilir. Rastgele Kilitlenmeler ve tanımsız davranışlarla karşılaşabilirsiniz.

Visual Studio 2019 sürüm 16,7 ' de, Visual Studio bir `.vcxproj` Proje dosyası yüklediğinde, proje öğelerinde desteklenmeyen girdileri otomatik olarak algılar. Çözüm yükleme sırasında çıkış penceresinde uyarıları görürsünüz.

Visual Studio 2019 sürüm 16,7, salt okunurdur proje desteği de ekler. Salt okuma desteği, IDE 'nin IDE ile düzenlenebilir projeler için ek sınırlamalara sahip olmayan el ile yazılmış projeler kullanmasına izin verir.

`.vcxproj`Desteklenmeyen bir veya daha fazla yapı kullanan bir dosyanız varsa, aşağıdaki seçeneklerden birini kullanarak IDE 'de uyarılar olmadan yük sağlayabilirsiniz:

- Tüm öğeleri açık olarak Listele
- Projenizi salt okunurdur olarak işaretleme
- Joker karakter öğelerini bir hedef gövdeye taşıma

## <a name="list-all-items-explicitly"></a>Tüm öğeleri açık olarak Listele

Şu anda, salt olmayan bir projedeki Çözüm Gezgini penceresinde joker karakter genişletme öğelerini görünür hale getirmenin bir yolu yoktur. Çözüm Gezgini projelerin tüm öğeleri açıkça listeliyorsa.

`.vcxproj`Projeleri otomatik olarak Visual Studio 2019 sürüm 16,7 veya sonraki bir sürümde genişletmek için `ReplaceWildcardsInProjectItems` özelliğini olarak ayarlayın `true` . *`Directory.Build.props`* Kök dizinde bir dosya oluşturmanızı ve bu içeriği kullanmanızı öneririz:

```xml
<Project>
  <PropertyGroup>
    <ReplaceWildcardsInProjectItems>true</ReplaceWildcardsInProjectItems>
  </PropertyGroup>
</Project>
```

## <a name="mark-your-project-as-read-only"></a>Projenizi salt okunurdur olarak işaretleme

Visual Studio 2019 sürüm 16,7 ve sonraki sürümlerde, projeleri *salt okuma*olarak işaretleyebilirsiniz. Projenizi salt okunurdur olarak işaretlemek için, dosyanıza aşağıdaki özelliği *`.vcxproj`* veya içe aktardığı dosyaları ekleyin:

```xml
<PropertyGroup>
    <ReadOnlyProject>true</ReadOnlyProject>
</PropertyGroup>
```

`<ReadOnlyProject>`Bu ayar, Visual Studio 'nun projeyi düzenlemesini ve kaydetmesini önler, böylece joker karakterler de dahil olmak üzere herhangi bir MSBuild yapısını kullanabilirsiniz.

Visual Studio, dosyadaki proje öğelerinde *`.vcxproj`* veya içeri aktarmalarının herhangi birinde joker karakter algıladığında proje önbelleğinin kullanılabilir olmadığını bilmelidir. Joker karakter kullanan çok sayıda projeniz varsa, IDE 'deki çözüm yükleme süreleri çok daha uzundur.

## <a name="move-wildcard-items-to-a-target-body"></a>Joker karakter öğelerini bir hedef gövdeye taşıma

Kaynakları toplamak, oluşturulan kaynakları eklemek vb. için joker karakterler kullanmak isteyebilirsiniz. Çözüm Gezgini penceresinde listelenen bunlara ihtiyacınız yoksa, bunun yerine bu yordamı kullanabilirsiniz:

1. Joker karakterler eklemek için öğe grubunun adını değiştirin. Örneğin, yerine:

   ```xml
   <Image Include="*.bmp" />
   <ClCompile Include="*.cpp" />
   ```

   Şunu değiştirin:

   ```xml
   <_WildCardImage Include="*.bmp" />
   <_WildCardClCompile Include="*.cpp" />
   ```

1. Bu içeriği  *`.vcxproj`* dosyanıza ekleyin.Ya da bu *`Directory.Build.targets`* köke ait tüm projeleri etkilemek için kök dizindeki bir dosyaya ekleyin:

   ```xml
   <Target Name="AddWildCardItems"
       AfterTargets="BuildGenerateSources">
     <ItemGroup>
       <Image Include="@(_WildCardImage)" />
       <ClCompile Include="@(_WildCardClCompile)" />
     </ItemGroup>
   </Target>
   ```

   Bu değişiklik, derlemeyi dosyada tanımlandığı gibi görün  *`.vcxproj`* . Ancak, artık Çözüm Gezgini penceresinde görünmezler ve IDE 'de sorunlara neden olmaz.

1.  `_WildCardClCompile`   Düzenleyicide bu dosyaları açtığınızda öğeler Için doğru IntelliSense 'i göstermek için aşağıdaki içeriği ekleyin:

   ```xml
   <PropertyGroup>
     <ComputeCompileInputsTargets>
       AddWildCardItems
       $(ComputeCompileInputsTargets)
     </ComputeCompileInputsTargets>
   </PropertyGroup>
   ```

Etkin olarak, bir hedef gövde içindeki herhangi bir öğe için joker karakterler kullanabilirsiniz. Ayrıca,  `ItemGroup`   bir tarafından proje öğesi olarak tanımlanmayan bir içinde joker karakterler kullanabilirsiniz [`ProjectSchemaDefinition`](https://devblogs.microsoft.com/cppblog/vc-MSBuild-extensibility-example/) .

> [!NOTE]
> Joker karakter içeren bir *`.vcxproj`* dosyayı dosyadan içeri aktarılan bir dosyaya taşırsanız, Çözüm Gezgini pencerede görünmez. Bu değişiklik Ayrıca projenizin değişiklik yapılmadan IDE 'ye yüklenmesine de olanak tanır. Ancak, bu yaklaşımı önermeyiz çünkü proje önbelleğini devre dışı bırakır.

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio’da C++ derleyicisi ve derleme özelliklerini ayarlama](../working-with-project-properties.md)<br/>
[Özellik sayfası XML dosyaları](property-page-xml-files.md)
