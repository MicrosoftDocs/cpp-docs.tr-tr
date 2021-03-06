---
description: 'Daha fazla bilgi edinin: nasıl yapılır: MSBuild projelerine özel derleme adımı ekleme'
title: 'Nasıl Yapılır: MSBuild Projelerine Özel Derleme Adımı Ekleme'
ms.date: 10/16/2019
helpviewer_keywords:
- 'msbuild (c++), howto: add a custom build step'
ms.assetid: a20a0c47-4df4-4754-a1f0-a94a99958916
ms.openlocfilehash: 1373aa2333fda6e0be9c7c574c5acc7840b9721a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97156404"
---
# <a name="how-to-add-a-custom-build-step-to-msbuild-projects"></a>Nasıl Yapılır: MSBuild Projelerine Özel Derleme Adımı Ekleme

Özel derleme adımı, bir derlemede Kullanıcı tanımlı bir adımdır. Özel bir yapı adımı, standart derleme veya bağlantı araç adımı gibi diğer tüm *komut aracı* adımıyla aynı şekilde davranır.

Proje dosyasında (. vcxproj) özel bir yapı adımı belirtin. Adım, yürütülecek bir komut satırı, herhangi bir ek giriş veya çıkış dosyası ve görüntülenecek bir ileti belirtebilir. **MSBuild** , çıkış dosyalarınızın giriş dosyalarınıza göre güncel olmadığını belirlerse, iletiyi görüntüler ve komutu yürütür.

Yapı hedefleri dizisinde özel derleme adımının konumunu belirtmek için `CustomBuildAfterTargets` Proje dosyasındaki ve XML öğelerinden birini veya her ikisini kullanın `CustomBuildBeforeTargets` . Örneğin, özel derleme adımının bağlantı aracı hedefinden sonra ve bildirim aracı hedefinden önce çalışacağını belirtebilirsiniz. Kullanılabilir hedeflerin gerçek kümesi, özel derlemeniz temelinde değişir.

`CustomBuildBeforeTargets`Belirli bir hedefin çalıştırılmadan önce özel derleme adımını yürütmek için bir öğe, `CustomBuildAfterTargets` belirli bir hedef çalıştıktan sonra adımı yürütmek için öğesi veya iki bitişik hedef arasında adımı yürütmek için her iki öğeyi de belirtin. Hiçbiri öğesi belirtilmemişse, özel yapı aracınız varsayılan konumunda yürütülür ve bu, **bağlantı** hedefinden sonra olur.

Özel derleme adımları ve özel derleme araçları, `CustomBuildBeforeTargets` ve XML öğelerinde belirtilen bilgileri paylaşır `CustomBuildAfterTargets` . Bu nedenle, bu hedefleri proje dosyanızda yalnızca bir kez belirtin.

### <a name="to-define-what-is-executed-by-the-custom-build-step"></a>Özel derleme adımı tarafından yürütülen öğeleri tanımlamak için

1. Proje dosyasına bir özellik grubu ekleyin. Bu özellik grubunda, aşağıdaki örnekte gösterildiği gibi, komut, giriş ve çıkış ve bir ileti belirtin. Bu örnek, [Izlenecek yol: bir C++ projesi oluşturmak Için MSBuild kullanma](walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)bölümünde oluşturduğunuz Main. cpp dosyasından bir. cab dosyası oluşturur.

    ```
    <ItemDefinitionGroup>
      <CustomBuildStep>
        <Command>makecab.exe $(ProjectDir)main.cpp $(TargetName).cab</Command>
        <Outputs>$(TargetName).cab</Outputs>
        <Inputs>$(ProjectDir)main.cpp</Inputs>
      </CustomBuildStep>
    </ItemDefinitionGroup>
    ```

### <a name="to-define-where-in-the-build-the-custom-build-step-will-execute"></a>Yapı içinde özel derleme adımının nerede yürütüleceğini tanımlamak için

1. Aşağıdaki özellik grubunu proje dosyasına ekleyin. Her iki hedefi de belirtebilirsiniz ya da yalnızca özel adımın belirli bir hedeften önce veya sonra yürütmesini istiyorsanız birini atlayabilirsiniz. Bu örnek, **MSBuild** 'in derleme adımından sonra, bağlantı adımından önce özel adımı gerçekleştirmesini söyler.

    ```
    <PropertyGroup>
      <CustomBuildAfterTargets>ClCompile</CustomBuildAfterTargets>
      <CustomBuildBeforeTargets>Link</CustomBuildBeforeTargets>
    </PropertyGroup>
    ```

## <a name="see-also"></a>Ayrıca bkz.

[İzlenecek yol: C++ projesi oluşturmak için MSBuild kullanma](walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)<br/>
[Nasıl yapılır: MSBuild projelerinde derleme olaylarını kullanma](how-to-use-build-events-in-msbuild-projects.md)<br/>
[Nasıl yapılır: MSBuild projelerine özel derleme araçları ekleme](how-to-add-custom-build-tools-to-msbuild-projects.md)
