---
title: Vcxproj. Filters dosyaları
ms.date: 09/25/2019
description: Çözüm Gezgini içindeki dosyalar için özel mantıksal C++ klasörler tanımlamak üzere Visual Studio projelerindeki filtre dosyalarını kullanın
helpviewer_keywords:
- vcxproj.filters
- filters file [C++]
ms.openlocfilehash: ee44bf3d1cbe06d6c007ed8976ec384a456efca5
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2019
ms.locfileid: "71686861"
---
# <a name="vcxprojfilters-files"></a>vcxproj. Filters dosyaları

*Filtreler* dosyası (@no__t -1. vcxproj. Filters), MSBuild BIÇIMINDEKI bir XML dosyasıdır ve kök proje klasöründe bulunur. Hangi dosya türlerinin **Çözüm Gezgini**hangi mantıksal klasöre gidebileceği belirler. Aşağıdaki çizimde, *. cpp* dosyaları **kaynak dosyaları** düğümünün altındadır. *. h* dosyaları **üstbilgi dosyaları** düğümünün altında *. ICO* ve *. RC* dosyaları **kaynak dosyaları**altındadır. Bu yerleştirme, filtreler dosyası tarafından denetlenir.

![Çözüm Gezgini mantıksal klasörler](media/solution-explorer-filters.png)

## <a name="creating-a-custom-filters-file"></a>Özel filtre dosyası oluşturma

Visual Studio bu dosyayı otomatik olarak oluşturur. Masaüstü uygulamaları için, önceden tanımlanmış mantıksal klasörler (filtreler) şunlardır: **kaynak dosyalar**, **üst bilgi dosyaları** ve **kaynak dosyaları**. UWP gibi diğer proje türleri, farklı bir varsayılan klasör kümesine sahip olabilir. Visual Studio, bilinen dosya türlerini her klasöre otomatik olarak atar. Özel bir ad veya özel dosya türlerini tutan bir filtreye sahip bir filtre oluşturmak istiyorsanız, projenin kök klasöründe veya varolan bir filtrenin altında kendi filtreleri dosyanızı oluşturabilirsiniz. (**Başvurular** ve **dış bağımlılıklar** , filtrelemeye katılmayan özel klasörlerdir.)

## <a name="example"></a>Örnek

Aşağıdaki örnek, daha önce gösterilecek örnek için filtreler dosyasını gösterir. Düz bir hiyerarşiye sahiptir; diğer bir deyişle, iç içe geçmiş mantıksal klasör yoktur. @No__t-0 düğümü isteğe bağlıdır. Visual Studio Automation arabirimlerinin filtreyi bulmasını sağlar. `Extensions` de isteğe bağlıdır. Projeye yeni bir dosya eklendiğinde, bu, eşleşen bir dosya uzantısına sahip en üstteki filtreye eklenir. Belirli bir filtreye dosya eklemek için filtreye sağ tıklayıp **Yeni öğe Ekle**' yi seçin.

@No__t-1 düğümlerini içeren `ItemGroup`, proje ilk başlatıldığında oluşturulur. Kendi vcxproj dosyalarınızı oluşturuyorsanız, tüm proje öğelerinin filtreler dosyasında da bir girdiye sahip olduğundan emin olun. @No__t-0 düğümündeki değerler dosya uzantılarına göre varsayılan filtrelemeyi geçersiz kılar. Projeye yeni bir öğe eklemek için Visual Studio kullandığınızda, IDE filtreler dosyasına tek bir dosya girişi ekler. Dosyanın uzantısını değiştirirseniz filtre otomatik olarak yeniden atanmaz. 

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

İç içe mantıksal klasörler oluşturmak için, `ItemGroup` filtrelerdeki tüm düğümleri aşağıda gösterildiği gibi bildirin. Her alt düğüm, en üstteki üst öğenin tam mantıksal yolunu bildirmelidir. Aşağıdaki örnekte, sonraki düğümlerde başvurulduğundan boş bir `ParentFilter` bildirilmelidir.

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

