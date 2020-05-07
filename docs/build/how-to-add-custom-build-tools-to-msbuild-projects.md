---
title: 'Nasıl Yapılır: MSBuild Projelerine Özel Derleme Araçları Ekleme'
ms.date: 11/04/2016
helpviewer_keywords:
- 'msbuild (c++), howto: add custom build tools'
ms.assetid: de03899a-371d-4396-9bf9-34f45a65e909
ms.openlocfilehash: 812932d9e668ab5ee0eb75eadbf75be3d791cddb
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65220710"
---
# <a name="how-to-add-custom-build-tools-to-msbuild-projects"></a>Nasıl Yapılır: MSBuild Projelerine Özel Derleme Araçları Ekleme

Özel bir yapı aracı, belirli bir dosyayla ilişkili kullanıcı tanımlı, komut satırı aracıdır.

Belirli bir dosya için, proje dosyasında (. vcxproj) yürütülecek komut satırını, ek girdi veya çıktı dosyalarını ve görüntülenecek bir iletiyi belirtin. **MSBuild** , çıkış dosyalarınızın giriş dosyalarınıza göre güncel olmadığını belirlerse, iletiyi görüntüler ve komut satırı aracını yürütür.

Özel yapı aracının ne zaman yürüttüğünü belirtmek için, proje dosyasındaki `CustomBuildBeforeTargets` ve `CustomBuildAfterTargets` XML öğelerinden birini veya her ikisini kullanın. Örneğin, özel yapı araclarınızın MıDL derleyicisinden sonra ve C/C++ derleyicisinden önce çalışacağını belirtebilirsiniz. Belirli bir `CustomBuildBeforeTargets` hedefin çalıştırılmadan önce aracın yürütüleceği öğeyi belirtin; belirli `CustomBuildAfterTargets` bir hedeften sonra aracın yürütüleceği öğe; ya da iki hedefin yürütülmesi arasında aracı çalıştırmak için her iki öğe. Öğesi belirtilmemişse, özel yapı aracınız, **MIDL** hedefinden önce olan varsayılan konumunda yürütülür.

Özel derleme adımları ve özel derleme araçları, `CustomBuildBeforeTargets` ve `CustomBuildAfterTargets` XML öğelerinde belirtilen bilgileri paylaşır. Bu hedefleri proje dosyanızda bir kez belirtin.

### <a name="to-add-a-custom-build-tool"></a>Özel bir yapı aracı eklemek için

1. Proje dosyasına bir öğe grubu ekleyin ve her giriş dosyası için bir öğe ekleyin. Burada gösterildiği gibi, komutu, ek girişleri, çıkışları ve öğe meta verileri olarak bir ileti belirtin. Bu örnek, bir "SSS. txt" dosyasının projenizle aynı dizinde olduğunu varsayar.

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
[Nasıl Yapılır: MSBuild Projelerinde Derleme Olaylarını Kullanma](how-to-use-build-events-in-msbuild-projects.md)<br/>
[Nasıl Yapılır: MSBuild Projelerine Özel Derleme Adımı Ekleme](how-to-add-a-custom-build-step-to-msbuild-projects.md)
