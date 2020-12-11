---
description: 'Daha fazla bilgi edinin: nasıl yapılır: MSBuild projelerine özel derleme araçları ekleme'
title: 'Nasıl Yapılır: MSBuild Projelerine Özel Derleme Araçları Ekleme'
ms.date: 11/04/2016
helpviewer_keywords:
- 'msbuild (c++), howto: add custom build tools'
ms.assetid: de03899a-371d-4396-9bf9-34f45a65e909
ms.openlocfilehash: 66ec4a488fd2a089f09ac775d1150300ff662ff2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97162826"
---
# <a name="how-to-add-custom-build-tools-to-msbuild-projects"></a>Nasıl Yapılır: MSBuild Projelerine Özel Derleme Araçları Ekleme

Özel bir yapı aracı, belirli bir dosyayla ilişkili kullanıcı tanımlı, komut satırı aracıdır.

Belirli bir dosya için, proje dosyasında (. vcxproj) yürütülecek komut satırını, ek girdi veya çıktı dosyalarını ve görüntülenecek bir iletiyi belirtin. **MSBuild** , çıkış dosyalarınızın giriş dosyalarınıza göre güncel olmadığını belirlerse, iletiyi görüntüler ve komut satırı aracını yürütür.

Özel yapı aracının ne zaman yürüttüğünü belirtmek için, `CustomBuildBeforeTargets` Proje dosyasındaki ve XML öğelerinden birini veya her ikisini kullanın `CustomBuildAfterTargets` . Örneğin, özel yapı araclarınızın MıDL derleyicisinden sonra ve C/C++ derleyicisinden önce çalışacağını belirtebilirsiniz. `CustomBuildBeforeTargets`Belirli bir hedefin çalıştırılmadan önce aracı yürütmek için öğesini belirtin; Aracı, `CustomBuildAfterTargets` belirli bir hedeften sonra yürütülecek öğe veya iki hedefin yürütülmesi arasında aracı çalıştırmak için her iki öğe de vardır. Öğesi belirtilmemişse, özel yapı aracınız, **MIDL** hedefinden önce olan varsayılan konumunda yürütülür.

Özel derleme adımları ve özel derleme araçları, `CustomBuildBeforeTargets` ve XML öğelerinde belirtilen bilgileri paylaşır `CustomBuildAfterTargets` . Bu hedefleri proje dosyanızda bir kez belirtin.

### <a name="to-add-a-custom-build-tool"></a>Özel bir yapı aracı eklemek için

1. Proje dosyasına bir öğe grubu ekleyin ve her giriş dosyası için bir öğe ekleyin. Burada gösterildiği gibi, komutu, ek girişleri, çıkışları ve öğe meta verileri olarak bir ileti belirtin. Bu örnek, bir "faq.txt" dosyasının, projenizle aynı dizinde olduğunu varsayar.

    ```
    <ItemGroup>
      <CustomBuild Include="faq.txt">
        <Message>Copying readme...</Message>
        <Command>copy %(Identity) $(OutDir)%(Identity)</Command>
        <Outputs>$(OutDir)%(Identity)</Outputs>
      </CustomBuild>
    </ItemGroup>
    ```

### <a name="to-define-where-in-the-build-the-custom-build-tools-will-execute"></a>Derlemede özel derleme araçlarının nerede yürütüleceğini tanımlamak için

1. Aşağıdaki özellik grubunu proje dosyasına ekleyin. Hedeflerden en az birini belirtmeniz gerekir, ancak yalnızca derleme adımlarınızın belirli bir hedefin önüne (veya bundan sonra) olmasını istiyorsanız diğerini atlayabilirsiniz. Bu örnek, yapılandırmadan sonra, ancak bağlamadan önce özel adımı gerçekleştirir.

    ```
    <PropertyGroup>
      <CustomBuildAfterTargets>ClCompile</CustomBuildAfterTargets>
      <CustomBuildBeforeTargets>Link</CustomBuildBeforeTargets>
    </PropertyGroup>
    ```

## <a name="see-also"></a>Ayrıca bkz.

[İzlenecek yol: C++ projesi oluşturmak için MSBuild kullanma](walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)<br/>
[Nasıl yapılır: MSBuild projelerinde derleme olaylarını kullanma](how-to-use-build-events-in-msbuild-projects.md)<br/>
[Nasıl yapılır: MSBuild projelerine özel derleme adımı ekleme](how-to-add-a-custom-build-step-to-msbuild-projects.md)
