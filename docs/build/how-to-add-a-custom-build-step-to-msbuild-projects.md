---
title: "Nasıl yapılır: MSBuild projelerine özel derleme adımı ekleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- msbuild.cpp.howto.addcustombuildstep
dev_langs:
- C++
helpviewer_keywords:
- 'msbuild (c++), howto: add a custom build step'
ms.assetid: a20a0c47-4df4-4754-a1f0-a94a99958916
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d664b9fad6a9ec67dc009a90171119036dc13cde
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-add-a-custom-build-step-to-msbuild-projects"></a>Nasıl Yapılır: MSBuild Projelerine Özel Derleme Adımı Ekleme
Özel derleme adımı bir yapı içinde kullanıcı tanımlı bir adımdır. Özel derleme adımı diğer gibi davranır *komut aracını* gibi standart derleme veya bağlantı aracı adım adım.  
  
 Özel derleme adımı proje dosyası (.vcxproj) belirtin. Adım yürütmek için herhangi bir ek giriş veya çıkış dosyaları ve görüntülenecek bir ileti bir komut satırını belirtebilirsiniz. Varsa **MSBuild** belirler, çıktı dosyaları göre giriş dosyalarınızın güncel olup, komutu yürütür ve ileti görüntüler.  
  
 Özel derleme konumunu adım yapı hedefleri sırayla belirtmek için birini veya her ikisini kullanın `CustomBuildAfterTargets` ve `CustomBuildBeforeTargets` proje dosyasındaki XML öğeleri. Örneğin, özel derleme adımı bağlantı aracı hedefi sonra ve bildirim aracı hedef önce çalışır belirtebilirsiniz. Kullanılabilir hedefler gerçek kümesi belirli yapınızın bağlıdır.  
  
 Belirtin `CustomBuildBeforeTargets` öğesinin belirli bir hedefe çalıştırmadan önce özel derleme adımı yürütme için `CustomBuildAfterTargets` belirli bir hedefe çalıştıktan sonra adım yürütmek için veya birden çok adım iki bitişik hedefler arasında yürütmek için her iki öğe. Hiçbiri öğesi belirtilmişse, sonra kendi varsayılan konumda özel derleme aracınızı yürütür **bağlantı** hedef.  
  
 Özel derleme adımlarını ve özel derleme araçları belirtilen bilgileri paylaşabilir `CustomBuildBeforeTargets` ve `CustomBuildAfterTargets` XML öğeleri. Bu nedenle, bu hedefleri, proje dosyasında yalnızca bir kez belirtin.  
  
### <a name="to-define-what-is-executed-by-the-custom-build-step"></a>Özel derleme adımı tarafından yürütülen tanımlamak için  
  
1.  Özellik grubu proje dosyasına ekleyin. Bu özellik grubunda, aşağıdaki örnekte gösterildiği gibi komutu, kendi girişleri ve çıkışları ve bir ileti belirtin. Bu örnek, oluşturduğunuz main.cpp dosyasından bir .cab dosyası oluşturur. [izlenecek yol: Visual C++ projesi oluşturmak için MSBuild kullanma](../build/walkthrough-using-msbuild-to-create-a-visual-cpp-project.md).  
  
    ```  
    <ItemDefinitionGroup>  
      <CustomBuildStep>  
        <Command>makecab.exe $(ProjectDir)main.cpp $(TargetName).cab</Command>  
        <Outputs>$(TargetName).cab</Outputs>  
        <Inputs>$(TargetFileName)</Inputs>  
      </CustomBuildStep>  
    </ItemDefinitionGroup>  
    ```  
  
### <a name="to-define-where-in-the-build-the-custom-build-step-will-execute"></a>Derleme özel derleme adımı burada yürütecek tanımlamak için  
  
1.  Aşağıdaki özellik grubu proje dosyasına ekleyin. Her iki hedefleri belirtebilir veya önce veya sonra belirli bir hedefe yürütmek için özel adım yalnızca istiyorsanız bir atlayabilirsiniz. Bu örnek söyler **MSBuild** derleme adımı sonra ancak bağlantı adım önce özel adımı gerçekleştirmek için.  
  
    ```  
    <PropertyGroup>  
      <CustomBuildAfterTargets>ClCompile</CustomBuildAfterTargets>  
      <CustomBuildBeforeTargets>Link</CustomBuildBeforeTargets>  
    </PropertyGroup>  
    ```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İzlenecek yol: Visual C++ projesi oluşturmak için MSBuild kullanma](../build/walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)   
 [Nasıl yapılır: MSBuild projelerinde derleme olaylarını kullanma](../build/how-to-use-build-events-in-msbuild-projects.md)   
 [Nasıl Yapılır: MSBuild Projelerine Özel Derleme Araçları Ekleme](../build/how-to-add-custom-build-tools-to-msbuild-projects.md)