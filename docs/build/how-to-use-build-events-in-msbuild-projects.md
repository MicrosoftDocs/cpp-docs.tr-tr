---
title: 'Nasıl Yapılır: MSBuild Projelerinde Derleme Olaylarını Kullanma'
ms.date: 11/04/2016
helpviewer_keywords:
- 'msbuild (c++), howto: use build events in projects'
ms.assetid: 2a58dc9d-3d50-4e49-97c1-86c5a05ce218
ms.openlocfilehash: 7c35abbcabe62da2e60fbc2393c575e7c3872cf3
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87224012"
---
# <a name="how-to-use-build-events-in-msbuild-projects"></a>Nasıl Yapılır: MSBuild Projelerinde Derleme Olaylarını Kullanma

Yapı olayı, MSBuild 'in derleme işlemindeki belirli bir aşamada gerçekleştirdiği bir komuttur. Oluşturma *öncesi* olay, derleme başlamadan önce oluşur; bağlama *öncesi* olay, bağlantı adımı başlamadan önce oluşur; ve derleme *sonrası* olay, derleme başarıyla bittikten sonra oluşur. Derleme olayı yalnızca ilişkili derleme adımı gerçekleşirse oluşur. Örneğin, bağlantı adımı çalıştırılmayan bağlantı öncesi olay oluşmaz.

Üç derleme olayının her biri, bir öğe tanımı grubunda yürütülen bir komut öğesi ( `<Command>` ) ve `<Message>` **MSBuild** derleme olayını gerçekleştirdiğinde görüntülenen bir ileti öğesi () tarafından temsil edilir. Her öğe isteğe bağlıdır ve aynı öğeyi birden çok kez belirtirseniz, son oluşum öncelik kazanır.

*use-in-build* `<` Derleme olayının yürütülüp yürütülmediğini göstermek için bir özellik grubunda isteğe bağlı bir Use-Build öğesi (*derleme-olay* `UseInBuild>` ) belirtilebilir. Bir *Use derlemesi* öğesinin içerik değeri ya da ' dir **`true`** **`false`** . Varsayılan olarak, karşılık gelen *derleme kullanımı* öğesi olarak ayarlanmadığı takdirde bir yapı olayı yürütülür **`false`** .

Aşağıdaki tabloda her derleme olay XML öğesi listelenmektedir:

|XML öğesi|Açıklama|
|-----------------|-----------------|
|`PreBuildEvent`|Bu olay, oluşturma başlamadan önce yürütülür.|
|`PreLinkEvent`|Bu olay bağlantı adımı başlamadan önce yürütülür.|
|`PostBuildEvent`|Bu olay, derleme tamamlandıktan sonra yürütülür.|

Aşağıdaki tabloda her *derleme kullanımı* öğesi listelenmektedir:

|XML öğesi|Açıklama|
|-----------------|-----------------|
|`PreBuildEventUseInBuild`|*Oluşturma öncesi* olayının yürütülüp yürütülmeyeceğini belirtir.|
|`PreLinkEventUseInBuild`|*Bağlama öncesi* etkinliğin yürütülüp yürütülmeyeceğini belirtir.|
|`PostBuildEventUseInBuild`|*Oluşturma sonrası* olayının yürütülüp yürütülmeyeceğini belirtir.|

## <a name="example"></a>Örnek

Aşağıdaki örnek, [Izlenecek yol: C++ projesi oluşturmak Için MSBuild kullanılarak](walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)oluşturulan MyProject. vcxproj dosyasının proje öğesinin içine eklenebilir. *Oluşturma öncesi* bir olay Main. cpp kopyasını oluşturur; *bağlama öncesi* bir olay Main. obj; kopyasını oluşturur. *oluşturma sonrası* bir olay myproject.exe bir kopyasını oluşturur. Proje sürüm yapılandırması kullanılarak derlenip, derleme olayları yürütülür. Proje bir hata ayıklama yapılandırması kullanılarak derlenise, derleme olayları yürütülmez.

``` xml
<ItemDefinitionGroup>
  <PreBuildEvent>
    <Command>copy $(ProjectDir)main.cpp $(ProjectDir)copyOfMain.cpp</Command>
    <Message>Making a copy of main.cpp </Message>
  </PreBuildEvent>
  <PreLinkEvent>
    <Command>copy $(ProjectDir)$(Configuration)\main.obj $(ProjectDir)$(Configuration)\copyOfMain.obj</Command>
    <Message>Making a copy of main.obj</Message>
  </PreLinkEvent>
  <PostBuildEvent>
    <Command>copy $(ProjectDir)$(Configuration)\$(TargetFileName) $(ProjectDir)$(Configuration)\copyOfMyproject.exe</Command>
    <Message>Making a copy of myproject.exe</Message>
  </PostBuildEvent>
</ItemDefinitionGroup>

<PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Release|Win32'">
  <PreBuildEventUseInBuild>true</PreBuildEventUseInBuild>
  <PreLinkEventUseInBuild>true</PreLinkEventUseInBuild>
  <PostBuildEventUseInBuild>true</PostBuildEventUseInBuild>
</PropertyGroup>

<PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Debug|Win32'">
  <PreBuildEventUseInBuild>false</PreBuildEventUseInBuild>
  <PreLinkEventUseInBuild>false</PreLinkEventUseInBuild>
  <PostBuildEventUseInBuild>false</PostBuildEventUseInBuild>
</PropertyGroup>
```

## <a name="see-also"></a>Ayrıca bkz.

[Komut satırında MSBuild-C++](msbuild-visual-cpp.md)<br/>
[İzlenecek yol: C++ projesi oluşturmak için MSBuild kullanma](walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)
