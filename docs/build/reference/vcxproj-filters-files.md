---
title: Vcxproj.filters dosyaları
ms.date: 09/25/2019
description: Solution Explorer'daki dosyalar için özel mantıksal klasörler tanımlamak için Visual Studio C++ projelerindeki filtreleri kullanma
helpviewer_keywords:
- vcxproj.filters
- filters file [C++]
ms.openlocfilehash: 57735246b543680243994b99b8c05c9ad1211f38
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81335941"
---
# <a name="vcxprojfilters-files"></a>vcxproj.filters dosyaları

*Filtreler* dosyası (\*.vcxproj.filters) kök proje klasöründe bulunan MSBuild biçiminde bir XML dosyasıdır. **Çözüm Gezgini'nde**hangi dosya türlerinin hangi mantıksal klasöre girdiğini belirtir. Aşağıdaki resimde, *.cpp* dosyaları Kaynak **Dosyalar** düğümü altındadır. *.h* dosyaları **Üstbilgi Dosyaları** düğümü altında ve *.ico* ve *.rc* dosyaları **Kaynak Dosyaları**altında. Bu yerleşim filtreler dosyası tarafından denetlenir.

![Çözüm Gezgini'ndeki mantıksal klasörler](media/solution-explorer-filters.png)

## <a name="creating-a-custom-filters-file"></a>Özel filtreler dosyası oluşturma

Visual Studio bu dosyayı otomatik olarak oluşturur. Masaüstü uygulamaları için, önceden tanımlanmış mantıksal klasörler (filtreler) şunlardır: **Kaynak Dosyalar,** **Üstbilgi Dosyaları** ve **Kaynak Dosyaları.** UWP gibi diğer proje türleri farklı bir varsayılan klasör kümesine sahip olabilir. Visual Studio her klasöre bilinen dosya türlerini otomatik olarak atar. Özel bir ada veya özel dosya türleri barındıran bir filtre oluşturmak istiyorsanız, projenin kök klasöründe veya varolan bir filtrenin altında kendi filtre dosyanızı oluşturabilirsiniz. (**Başvurular** ve **Dış Bağımlılıklar,** filtreleme ile katılmayan özel klasörlerdir.)

## <a name="example"></a>Örnek

Aşağıdaki örnek, örnek için filtre ler dosyasını daha önce gösterir. Düz bir hiyerarşiye sahiptir; başka bir deyişle, iç içe geçen mantıksal klasörler yoktur. Düğüm `UniqueIdentifier` isteğe bağlıdır. Visual Studio otomasyon arayüzlerinin filtreyi bulmasını sağlar. `Extensions`isteğe bağlıdır. Projeye yeni bir dosya eklendiğinde, eşleşen bir dosya uzantısı ile en üstteki filtreye eklenir. Belirli bir filtreye dosya eklemek için filtreye sağ tıklayın ve **Yeni Öğe Ekle'yi**seçin.

`ClInclude` Düğümleri `ItemGroup` içeren proje ilk başlatıldığında oluşturulur. Kendi vcxproj dosyalarınızı oluşturuyorsanız, tüm proje öğelerinin de filtre dosyasında bir girişi olduğundan emin olun. Düğümdeki `ClInclude` değerler, dosya uzantılarını temel alan varsayılan filtrelemeyi geçersiz kılar. Projeye yeni bir öğe eklemek için Visual Studio'yu kullandığınızda, IDE filtreler dosyasına ayrı bir dosya girişi ekler. Dosyanın uzantısını değiştirirseniz filtre otomatik olarak yeniden atanmamış olur.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Project ToolsVersion="4.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <ItemGroup>
    <Filter Include="Source Files">
      <UniqueIdentifier>{4FC737F1-C7A5-4376-A066-2A32D752A2FF}</UniqueIdentifier>
      <Extensions>cpp;c;cc;cxx;def;odl;idl;hpj;bat;asm;asmx</Extensions>
    </Filter>
    <Filter Include="Header Files">
      <UniqueIdentifier>{93995380-89BD-4b04-88EB-625FBE52EBFB}</UniqueIdentifier>
      <Extensions>h;hh;hpp;hxx;hm;inl;inc;ipp;xsd</Extensions>
    </Filter>
    <Filter Include="Resource Files">
      <UniqueIdentifier>{67DA6AB6-F800-4c08-8B7A-83BB121AAD01}</UniqueIdentifier>
      <Extensions>rc;ico;cur;bmp;dlg;rc2;rct;bin;rgs;gif;jpg;jpeg;jpe;resx;tiff;tif;png;wav;mfcribbon-ms</Extensions>
    </Filter>
  </ItemGroup>
  <ItemGroup>
    <ClInclude Include="MFCApplication1.h">
      <Filter>Header Files</Filter>
    </ClInclude>
    <ClInclude Include="MFCApplication1Dlg.h">
      <Filter>Header Files</Filter>
    </ClInclude>
    <ClInclude Include="stdafx.h">
      <Filter>Header Files</Filter>
    </ClInclude>
    <ClInclude Include="targetver.h">
      <Filter>Header Files</Filter>
    </ClInclude>
    <ClInclude Include="Resource.h">
      <Filter>Header Files</Filter>
    </ClInclude>
  </ItemGroup>
  <ItemGroup>
    <ClCompile Include="MFCApplication1.cpp">
      <Filter>Source Files</Filter>
    </ClCompile>
    <ClCompile Include="MFCApplication1Dlg.cpp">
      <Filter>Source Files</Filter>
    </ClCompile>
    <ClCompile Include="stdafx.cpp">
      <Filter>Source Files</Filter>
    </ClCompile>
  </ItemGroup>
  <ItemGroup>
    <ResourceCompile Include="MFCApplication1.rc">
      <Filter>Resource Files</Filter>
    </ResourceCompile>
  </ItemGroup>
  <ItemGroup>
    <None Include="res\MFCApplication1.rc2">
      <Filter>Resource Files</Filter>
    </None>
  </ItemGroup>
  <ItemGroup>
    <Image Include="res\MFCApplication1.ico">
      <Filter>Resource Files</Filter>
    </Image>
  </ItemGroup>
</Project>
```

İç içe geçmiş mantıksal klasörler oluşturmak için, `ItemGroup` filtrelerdeki tüm düğümleri aşağıda gösterildiği gibi bildirin. Her alt düğüm en üstteki üst öğeye tam mantıksal yolu bildirmelidir. Aşağıdaki örnekte, daha `ParentFilter` sonraki düğümlerde başvurulduğuiçin boş bir beyan edilmelidir.

```xml
  <ItemGroup>
    <Filter Include="ParentFilter">
    </Filter>
    <Filter Include="ParentFilter\Source Files"> <!-- Full path to topmost parent.-->  
      <UniqueIdentifier>{4FC737F1-C7A5-4376-A066-2A32D752A2FF}</UniqueIdentifier> <!--  Optional-->
      <Extensions>cpp;c;cc;cxx;def;odl;idl;hpj;bat;asm;asmx</Extensions> <!-- Optional -->
    </Filter>
    <Filter Include="Header Files">
      <UniqueIdentifier>{93995380-89BD-4b04-88EB-625FBE52EBFB}</UniqueIdentifier>
      <Extensions>h;hh;hpp;hxx;hm;inl;inc;ipp;xsd</Extensions>
    </Filter>
  </ItemGroup>
```
