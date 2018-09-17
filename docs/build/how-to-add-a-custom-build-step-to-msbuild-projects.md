---
title: 'Nasıl yapılır: MSBuild projelerine özel derleme adımı ekleme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
f1_keywords:
- msbuild.cpp.howto.addcustombuildstep
dev_langs:
- C++
helpviewer_keywords:
- 'msbuild (c++), howto: add a custom build step'
ms.assetid: a20a0c47-4df4-4754-a1f0-a94a99958916
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ca8206024f4fbaf38b8161a9e12672782551db83
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45712185"
---
# <a name="how-to-add-a-custom-build-step-to-msbuild-projects"></a>Nasıl Yapılır: MSBuild Projelerine Özel Derleme Adımı Ekleme

Özel derleme adımı bir derleme kullanıcı tanımlı bir adımdır. Özel derleme adımı diğer gibi davranır *komut aracını* gibi standart derleme veya bağlantı aracı adım adım.

Özel derleme adımı, proje dosyası (.vcxproj) belirtin. Bu adım yürütülecek, herhangi bir ek giriş veya çıkış dosyalarını ve görüntülenecek bir ileti bir komut satırı belirtebilirsiniz. Varsa **MSBuild** belirleyen çıktı dosyalarınızı onaylamaz, giriş dosyalarınızın güncel değil, bir ileti görüntüler ve komutu yürütür.

Özel derleme konumu adım yapı hedefleri sırayla belirtmek için aşağıdakilerden birini veya her ikisini de kullanın `CustomBuildAfterTargets` ve `CustomBuildBeforeTargets` proje dosyasındaki XML öğeleri. Örneğin, özel derleme adımı aracı hedef sonra ve bildirim aracı hedef önce çalıştığı belirtebilirsiniz. Kullanılabilir hedeflerden gerçek kümesi üzerinde belirli yapı bağlıdır.

Belirtin `CustomBuildBeforeTargets` belirli bir hedefe çalışmadan önce özel derleme adımı yürütülecek öğesi `CustomBuildAfterTargets` belirli bir hedefe çalıştırıldıktan sonra adım yürütülecek öğesi ya da iki bitişik hedefler arasında adımı yürütmeye yönelik her iki öğesi. Sonra varsayılan konumda hiçbiri ögesi belirliyse, özel derleme aracı yürütür **bağlantı** hedef.

Özel derleme adımlarını ve özel derleme araçları içinde belirtilen bilgileri paylaşmak `CustomBuildBeforeTargets` ve `CustomBuildAfterTargets` XML öğeleri. Bu nedenle, bu hedefleri, proje dosyanızda yalnızca bir kez belirtin.

### <a name="to-define-what-is-executed-by-the-custom-build-step"></a>Özel derleme adımı tarafından yürütülen tanımlamak için

1. Proje dosyasına bir özellik grubuna ekleyin. Bu özellik grubunda, aşağıdaki örnekte gösterildiği gibi komutu, girişleri ve çıkışları ve bir ileti belirtin. Bu örnek, oluşturduğunuz Main.cpp öğesi dosyasından bir .cab dosyası oluşturur. [izlenecek yol: Visual C++ projesi oluşturmak için MSBuild kullanma](../build/walkthrough-using-msbuild-to-create-a-visual-cpp-project.md).

    ```
    <ItemDefinitionGroup>
      <CustomBuildStep>
        <Command>makecab.exe $(ProjectDir)main.cpp $(TargetName).cab</Command>
        <Outputs>$(TargetName).cab</Outputs>
        <Inputs>$(TargetFileName)</Inputs>
      </CustomBuildStep>
    </ItemDefinitionGroup>
    ```

### <a name="to-define-where-in-the-build-the-custom-build-step-will-execute"></a>Özel derleme adımının yapı burada yürütülür tanımlamak için

1. Aşağıdaki özellik grubu proje dosyasına ekleyin. Her iki hedefleri belirtebilirsiniz veya yalnızca özel adımı öncesinde veya sonrasında belirli bir hedefe yürütmek için isterseniz bir atlayabilirsiniz. Bu örnekte söyler **MSBuild** derleme adımından sonra ancak bağlantı adımdan önce özel adımı gerçekleştirmek için.

    ```
    <PropertyGroup>
      <CustomBuildAfterTargets>ClCompile</CustomBuildAfterTargets>
      <CustomBuildBeforeTargets>Link</CustomBuildBeforeTargets>
    </PropertyGroup>
    ```

## <a name="see-also"></a>Ayrıca Bkz.

[İzlenecek yol: Visual C++ Projesi Oluşturmak için MSBuild Kullanma](../build/walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)<br/>
[Nasıl Yapılır: MSBuild Projelerinde Derleme Olaylarını Kullanma](../build/how-to-use-build-events-in-msbuild-projects.md)<br/>
[Nasıl Yapılır: MSBuild Projelerine Özel Derleme Araçları Ekleme](../build/how-to-add-custom-build-tools-to-msbuild-projects.md)