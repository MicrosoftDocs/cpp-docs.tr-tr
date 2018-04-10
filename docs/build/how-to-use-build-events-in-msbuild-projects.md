---
title: 'Nasıl yapılır: MSBuild projelerinde derleme olaylarını kullanma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- msbuild.cpp.howto.usebuildevents
dev_langs:
- C++
helpviewer_keywords:
- 'msbuild (c++), howto: use build events in projects'
ms.assetid: 2a58dc9d-3d50-4e49-97c1-86c5a05ce218
caps.latest.revision: 23
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cc8b3b21cdc9aad183f39bf709f93e022e790eef
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-use-build-events-in-msbuild-projects"></a>Nasıl Yapılır: MSBuild Projelerinde Derleme Olaylarını Kullanma
Bir komut bir yapı olayıdır, [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] derleme sürecindeki belirli bir aşamada gerçekleştirir. *Oluşturma öncesi* olayı, yapı başlamadan önce oluşur; *bağlama öncesi* olayı bağlantı adım başlamadan önce; oluşur ve *oluşturma sonrası* olay oluştuktan sonra derleme başarılı bir şekilde sona erer. Yalnızca ilişkili derleme adımı oluşursa bir yapı olayı oluşur. Örneğin, bağlantı adım çalışmazsa bağlama öncesi olay gerçekleşmez.  
  
 Üç yapı olayların her biri bir öğesi tanım grubunda command öğesi tarafından temsil edilen (`<Command>`), yürütüldüğünde ve bir ileti öğesi (`<Message>`) diğer bir deyişle ne zaman görüntülenen **MSBuild** yapı olayı gerçekleştirir. Her öğe isteğe bağlıdır ve birden çok kez aynı öğeye belirtirseniz, son a geçişi önceliklidir.  
  
 İsteğe bağlı bir *kullanım yapısı* öğesi (`<`*yapı olay***UseInBuild**`>`) belirtmek için bir özellik grubunda belirtilen olup olmadığını derleme olayının yürütülür. İçeriğinin değerini bir *kullanım yapısı* öğesidir ya da `true` veya `false`. Varsayılan olarak, bir derleme olayının sürece yürütülen ilgili *kullanım yapısı* ayarlanır `false`.  
  
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