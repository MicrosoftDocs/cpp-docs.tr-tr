---
title: 'Nasıl yapılır: MSBuild projelerine özel derleme araçları ekleme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
f1_keywords:
- msbuild.cpp.howto.addcustombuildtools
dev_langs:
- C++
helpviewer_keywords:
- 'msbuild (c++), howto: add custom build tools'
ms.assetid: de03899a-371d-4396-9bf9-34f45a65e909
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4e06a2a545862c0fa9cfdcf6311334ecc86de2bf
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45714408"
---
# <a name="how-to-add-custom-build-tools-to-msbuild-projects"></a>Nasıl Yapılır: MSBuild Projelerine Özel Derleme Araçları Ekleme

Özel derleme aracı belirli bir dosya ile ilişkili kullanıcı tanımlı, komut satırı bir araçtır.

Belirli bir dosyayı yürütmek için proje dosyasını (.vcxproj) komut satırı, herhangi bir ek giriş veya çıkış dosyalarını ve görüntülenecek bir ileti belirtin. Varsa **MSBuild** belirleyen çıktı dosyalarınızı onaylamaz, giriş dosyalarınızın güncel değil, bir ileti görüntüler ve komut satırı aracı yürütür.

Ne zaman özel derleme aracı yürütür belirtmek için aşağıdakilerden birini veya her ikisini de kullanın `CustomBuildBeforeTargets` ve `CustomBuildAfterTargets` proje dosyasındaki XML öğeleri. Örneğin, Özel Yapı aracınızı MIDL derleyicisi sonra ve C/C++ Derleyici önce çalıştırmanızı belirtebilirsiniz. Belirtin `CustomBuildBeforeTargets` belirli bir hedefe çalışmadan önce; aracı yürütülecek öğesi `CustomBuildAfterTargets` sonra belirli bir hedefe; aracı çalıştırmak için veya birden çok iki hedefi yürütülmesi arasında aracı çalıştırmak için her iki öğe. Hiçbiri ögesi belirliyse, önce kendi varsayılan konumda, özel derleme aracı yürütür **MIDL** hedef.

Özel derleme adımlarını ve özel derleme araçları içinde belirtilen bilgileri paylaşmak `CustomBuildBeforeTargets` ve `CustomBuildAfterTargets` XML öğeleri. Bu hedefleri, proje dosyanızda bir kez belirtin.

### <a name="to-add-a-custom-build-tool"></a>Özel derleme aracı eklemek için

1. Bir öğe grubunu proje dosyasına ekleyin ve her giriş dosyası için bir öğe ekleyin. Komutu, ek girişler, çıkışlar ve bir ileti öğesi olarak meta veriler, aşağıda gösterildiği gibi belirtin. Bu örnek, bir "faq.txt" dosyası proje ile aynı dizinde bulunduğunu varsayar.

    ```
    <ItemGroup>
      <CustomBuild Include="faq.txt">
        <Message>Copying readme...</Message>
        <Command>copy %(Identity) $(OutDir)%(Identity)</Command>
        <Outputs>$(OutDir)%(Identity)</Outputs>
      </CustomBuild>
    </ItemGroup>
    ```

### <a name="to-define-where-in-the-build-the-custom-build-tools-will-execute"></a>Derleme özel derleme araçları burada yürütecek tanımlamak için

1. Aşağıdaki özellik grubu proje dosyasına ekleyin. Hedefleri en az birini belirtmeniz gerekir, ancak yalnızca derleme adımınız, önce (veya sonrasında) yürütme etmeyle ilgileniyorsanız diğer atlayabilirsiniz belirli bir hedef. Bu örnekte, derleme sonra ancak bağlama önce özel adımı gerçekleştirir.

    ```
    <PropertyGroup>
      <CustomBuildAfterTargets>ClCompile</CustomBuildAfterTargets>
      <CustomBuildBeforeTargets>Link</CustomBuildBeforeTargets>
    </PropertyGroup>
    ```

## <a name="see-also"></a>Ayrıca Bkz.

[İzlenecek yol: Visual C++ Projesi Oluşturmak için MSBuild Kullanma](../build/walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)<br/>
[Nasıl Yapılır: MSBuild Projelerinde Derleme Olaylarını Kullanma](../build/how-to-use-build-events-in-msbuild-projects.md)<br/>
[Nasıl Yapılır: MSBuild Projelerine Özel Derleme Adımı Ekleme](../build/how-to-add-a-custom-build-step-to-msbuild-projects.md)