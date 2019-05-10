---
title: 'Nasıl yapılır: MSBuild projelerine özel derleme adımı ekleme'
ms.date: 11/04/2016
helpviewer_keywords:
- 'msbuild (c++), howto: add a custom build step'
ms.assetid: a20a0c47-4df4-4754-a1f0-a94a99958916
ms.openlocfilehash: d70f145a9d43463266a9c0bbff68e8e7f36ef2c6
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65220734"
---
# <a name="how-to-add-a-custom-build-step-to-msbuild-projects"></a>Nasıl yapılır: MSBuild projelerine özel derleme adımı ekleme

Özel derleme adımı bir derleme kullanıcı tanımlı bir adımdır. Özel derleme adımı diğer gibi davranır *komut aracını* gibi standart derleme veya bağlantı aracı adım adım.

Özel derleme adımı, proje dosyası (.vcxproj) belirtin. Bu adım yürütülecek, herhangi bir ek giriş veya çıkış dosyalarını ve görüntülenecek bir ileti bir komut satırı belirtebilirsiniz. Varsa **MSBuild** belirleyen çıktı dosyalarınızı onaylamaz, giriş dosyalarınızın güncel değil, bir ileti görüntüler ve komutu yürütür.

Özel derleme konumu adım yapı hedefleri sırayla belirtmek için aşağıdakilerden birini veya her ikisini de kullanın `CustomBuildAfterTargets` ve `CustomBuildBeforeTargets` proje dosyasındaki XML öğeleri. Örneğin, özel derleme adımı aracı hedef sonra ve bildirim aracı hedef önce çalıştığı belirtebilirsiniz. Kullanılabilir hedeflerden gerçek kümesi üzerinde belirli yapı bağlıdır.

Belirtin `CustomBuildBeforeTargets` belirli bir hedefe çalışmadan önce özel derleme adımı yürütülecek öğesi `CustomBuildAfterTargets` belirli bir hedefe çalıştırıldıktan sonra adım yürütülecek öğesi ya da iki bitişik hedefler arasında adımı yürütmeye yönelik her iki öğesi. Sonra varsayılan konumda hiçbiri ögesi belirliyse, özel derleme aracı yürütür **bağlantı** hedef.

Özel derleme adımlarını ve özel derleme araçları içinde belirtilen bilgileri paylaşmak `CustomBuildBeforeTargets` ve `CustomBuildAfterTargets` XML öğeleri. Bu nedenle, bu hedefleri, proje dosyanızda yalnızca bir kez belirtin.

### <a name="to-define-what-is-executed-by-the-custom-build-step"></a>Özel derleme adımı tarafından yürütülen tanımlamak için

1. Proje dosyasına bir özellik grubuna ekleyin. Bu özellik grubunda, aşağıdaki örnekte gösterildiği gibi komutu, girişleri ve çıkışları ve bir ileti belirtin. Bu örnek, oluşturduğunuz Main.cpp öğesi dosyasından bir .cab dosyası oluşturur. [izlenecek yol: Oluşturmak için MSBuild'ı kullanarak bir C++ proje](walkthrough-using-msbuild-to-create-a-visual-cpp-project.md).

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

## <a name="see-also"></a>Ayrıca bkz.

[İzlenecek yol: C++ Projesi Oluşturmak için MSBuild Kullanma](walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)<br/>
[Nasıl yapılır: MSBuild Projelerinde Derleme Olaylarını Kullanma](how-to-use-build-events-in-msbuild-projects.md)<br/>
[Nasıl yapılır: MSBuild Projelerine Özel Derleme Araçları Ekleme](how-to-add-custom-build-tools-to-msbuild-projects.md)
