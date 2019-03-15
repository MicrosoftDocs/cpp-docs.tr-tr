---
title: 'Nasıl yapılır: MSBuild projelerine özel derleme araçları ekleme'
ms.date: 11/04/2016
f1_keywords:
- msbuild.cpp.howto.addcustombuildtools
helpviewer_keywords:
- 'msbuild (c++), howto: add custom build tools'
ms.assetid: de03899a-371d-4396-9bf9-34f45a65e909
ms.openlocfilehash: 05f160e650c0dd717d7ce0f29259f866d751fdba
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57815274"
---
# <a name="how-to-add-custom-build-tools-to-msbuild-projects"></a>Nasıl yapılır: MSBuild projelerine özel derleme araçları ekleme

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

## <a name="see-also"></a>Ayrıca bkz.

[İzlenecek yol: Visual C++ Projesi Oluşturmak için MSBuild Kullanma](walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)<br/>
[Nasıl yapılır: MSBuild Projelerinde Derleme Olaylarını Kullanma](how-to-use-build-events-in-msbuild-projects.md)<br/>
[Nasıl yapılır: MSBuild Projelerine Özel Derleme Adımı Ekleme](how-to-add-a-custom-build-step-to-msbuild-projects.md)
