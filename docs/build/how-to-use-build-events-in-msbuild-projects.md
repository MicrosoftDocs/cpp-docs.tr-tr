---
title: 'Nasıl yapılır: MSBuild projelerinde derleme olaylarını kullanma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
f1_keywords:
- msbuild.cpp.howto.usebuildevents
dev_langs:
- C++
helpviewer_keywords:
- 'msbuild (c++), howto: use build events in projects'
ms.assetid: 2a58dc9d-3d50-4e49-97c1-86c5a05ce218
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 59863911072b491eb19a1296f3cb40d4f4ab4dce
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42613062"
---
# <a name="how-to-use-build-events-in-msbuild-projects"></a>Nasıl Yapılır: MSBuild Projelerinde Derleme Olaylarını Kullanma
Bir derleme olay MSBuild yapı işleminde belirli bir aşamada gerçekleştirir bir komuttur. *Derleme öncesi* olayı oluşturma başlamadan önce oluşur; *bağlama öncesi* olaylarının bağlantı adım başlatılmadan önce; ve *derleme sonrası* olay yapıdan sonra gerçekleşir başarılı bir şekilde sona erer. İlişkili derleme adımı oluşursa bir derleme olayı oluşur. Örneğin, bağlantı adım çalışmazsa bağlama öncesi olay gerçekleşmez.  
  
 Üç derleme olayların her biri bir öğe tanım grubu içinde bir command öğesi tarafından temsil edilen (`<Command>`), yürütülür ve bir ileti öğesi (`<Message>`) diğer bir deyişle olduğunda görüntülenen **MSBuild** derleme olayı gerçekleştirir. Her öğe isteğe bağlıdır ve birden çok kez aynı öğeye belirtirseniz, son oluşum önceliklidir.  
  
 İsteğe bağlı *yapı içinde kullanımı* öğesi (`<`* oluşturmak-olay ***UseInBuild**`>`) derleme olay yürütülüp yürütülmeyeceğini gösteren bir özellik grubu belirtilebilir. İçeriğinin değerini bir *yapı içinde kullanımı* öğedir ya da `true` veya `false`. Varsayılan olarak, bir derleme olay sürece yürütülür, karşılık gelen *yapı içinde kullanımı* ayarlanır `false`.  
  
 Aşağıdaki tabloda, her yapı olay XML öğesi listelenmektedir:  
  
|XML öğesi|Açıklama|  
|-----------------|-----------------|  
|`PreBuildEvent`|Oluşturma başlamadan önce bu olay yürütür.|  
|`PreLinkEvent`|Bağlantı adım başlamadan önce bu olay yürütür.|  
|`PostBuildEvent`|Derleme tamamlandıktan sonra bu olay yürütür.|  
  
 Aşağıdaki tabloda her listeler *yapı içinde kullanımı* öğesi:  
  
|XML öğesi|Açıklama|  
|-----------------|-----------------|  
|`PreBuildEventUseInBuild`|Yürütülecek belirtir *derleme öncesi* olay.|  
|`PreLinkEventUseInBuild`|Yürütülecek belirtir *bağlama öncesi* olay.|  
|`PostBuildEventUseInBuild`|Yürütülecek belirtir *derleme sonrası* olay.|  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, oluşturduğunuz myproject.vcxproj dosyanın proje öğesi içinde eklenebilir [izlenecek yol: Visual C++ projesi oluşturmak için MSBuild kullanma](../build/walkthrough-using-msbuild-to-create-a-visual-cpp-project.md). A *derleme öncesi* olay yaptığı bir kopyasını Main.cpp olarak; bir *bağlama öncesi* bir kopyasını main.obj; ve bir olay yapar *derleme sonrası* olay myproject.exe bir kopyasını getirir. Proje yayın yapılandırma kullanılarak oluşturulmuşsa, derleme olayları yürütülür. Proje hata ayıklama Yapılandırması kullanılarak oluşturulmuşsa, derleme olayları yürütülmedi.  
  
```  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MSBuild (Visual C++)](../build/msbuild-visual-cpp.md)   
 [İzlenecek yol: Visual C++ Projesi Oluşturmak için MSBuild Kullanma](../build/walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)