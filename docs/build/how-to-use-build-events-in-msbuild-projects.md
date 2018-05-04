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
ms.openlocfilehash: 2367c85dbd4a4ef7b10d927592c0fb10a417f0e6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="how-to-use-build-events-in-msbuild-projects"></a>Nasıl Yapılır: MSBuild Projelerinde Derleme Olaylarını Kullanma
Bir komut bir yapı olayıdır, [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] derleme sürecindeki belirli bir aşamada gerçekleştirir. *Oluşturma öncesi* olayı, yapı başlamadan önce oluşur; *bağlama öncesi* olayı bağlantı adım başlamadan önce; oluşur ve *oluşturma sonrası* olay oluştuktan sonra derleme başarılı bir şekilde sona erer. Yalnızca ilişkili derleme adımı oluşursa bir yapı olayı oluşur. Örneğin, bağlantı adım çalışmazsa bağlama öncesi olay gerçekleşmez.  
  
 Üç yapı olayların her biri bir öğesi tanım grubunda command öğesi tarafından temsil edilen (`<Command>`), yürütüldüğünde ve bir ileti öğesi (`<Message>`) diğer bir deyişle ne zaman görüntülenen **MSBuild** yapı olayı gerçekleştirir. Her öğe isteğe bağlıdır ve birden çok kez aynı öğeye belirtirseniz, son a geçişi önceliklidir.  
  
 İsteğe bağlı bir *kullanım yapısı* öğesi (`<`* oluşturmak-olay ***UseInBuild**`>`) derleme olayının yürütülüp yürütülmeyeceğini gösteren bir özellik grubu belirtilebilir. İçeriğinin değerini bir *kullanım yapısı* öğesidir ya da `true` veya `false`. Varsayılan olarak, bir derleme olayının sürece yürütülen ilgili *kullanım yapısı* ayarlanır `false`.  
  
 Aşağıdaki tabloda her bir yapı olay XML öğesi listelenmektedir:  
  
|XML öğesi|Açıklama|  
|-----------------|-----------------|  
|`PreBuildEvent`|Yapı başlamadan önce bu olay yürütür.|  
|`PreLinkEvent`|Bağlantı adım başlamadan önce bu olay yürütür.|  
|`PostBuildEvent`|Yapı tamamlandıktan sonra bu olay yürütür.|  
  
 Aşağıdaki tabloda her listeler *kullanım yapısı* öğe:  
  
|XML öğesi|Açıklama|  
|-----------------|-----------------|  
|`PreBuildEventUseInBuild`|Yürütülecek belirtir *oluşturma öncesi* olay.|  
|`PreLinkEventUseInBuild`|Yürütülecek belirtir *bağlama öncesi* olay.|  
|`PostBuildEventUseInBuild`|Yürütülecek belirtir *oluşturma sonrası* olay.|  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, Project öğesi içinde oluşturulan myproject.vcxproj dosyasının içinde eklenebilir [izlenecek yol: Visual C++ projesi oluşturmak için MSBuild kullanma](../build/walkthrough-using-msbuild-to-create-a-visual-cpp-project.md). A *oluşturma öncesi* bir main.cpp kopyasını; bir olay yapar *bağlama öncesi* main.obj; kopyasını bir ve bir olay yapar *oluşturma sonrası* olay myproject.exe bir kopyasını sağlar. Proje bir yayın yapılandırma kullanılarak oluşturulmuştur, derleme olaylarını yürütülür. Projeyi hata ayıklama Yapılandırması'nı kullanarak oluşturulursa, derleme olaylarını yürütülmedi.  
  
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