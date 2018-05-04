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
ms.openlocfilehash: 3793e4223d00f219cc4f1d7b09e67453901bd6d1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="how-to-add-custom-build-tools-to-msbuild-projects"></a>Nasıl Yapılır: MSBuild Projelerine Özel Derleme Araçları Ekleme
Belirli bir dosya ile ilişkilendirilmiş bir kullanıcı tarafından tanımlanan, komut satırı aracı bir özel derleme aracıdır.  
  
 Belirli bir dosya için yürütmek için proje dosyası (.vcxproj) komut satırı, herhangi bir ek giriş veya çıkış dosyaları ve görüntülenecek bir ileti belirtin. Varsa **MSBuild** belirler, çıktı dosyaları göre giriş dosyalarınızın güncel, komut satırı aracı yürütür ve ileti görüntüler.  
  
 Özel derleme aracı zaman yürütür belirtmek için birini veya her ikisini kullanın `CustomBuildBeforeTargets` ve `CustomBuildAfterTargets` proje dosyasındaki XML öğeleri. Örneğin, özel derleme aracınızı MIDL derleyici sonra ve C/C++ derleyicisi önce çalıştırmak belirtebilir. Belirtin `CustomBuildBeforeTargets` öğesinin belirli bir hedefe çalışmadan önce; Aracı'nı çalıştırmak için `CustomBuildAfterTargets` sonra belirli bir hedef; Aracı'nı çalıştırmak için veya birden çok iki hedefleri yürütme arasında aracı çalıştırmak için her iki öğe. Hiçbiri öğesi belirtilmişse, önce kendi varsayılan konumda özel derleme aracınızı yürütür **MIDL** hedef.  
  
 Özel derleme adımlarını ve özel derleme araçları belirtilen bilgileri paylaşabilir `CustomBuildBeforeTargets` ve `CustomBuildAfterTargets` XML öğeleri. Bu hedefleri, proje dosyasında bir kez belirtin.  
  
### <a name="to-add-a-custom-build-tool"></a>Özel derleme aracı eklemek için  
  
1.  Proje dosyasına bir madde grubu ekleyin ve her giriş dosyası için bir öğe ekleyin. Komutu, ek giriş, çıkış ve bir ileti olarak öğe meta veriler, aşağıda gösterildiği gibi belirtin. Bu örnek, projenizin ile aynı dizinde bir "faq.txt" dosyanın var olduğunu varsayar.  
  
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
  
1.  Aşağıdaki özellik grubu proje dosyasına ekleyin. Hedefleri en az birini belirtmeniz gerekir, ancak yalnızca önceki (veya sonraki) yürütmek, derleme adımı elde etmeyle ilgileniyorsanız diğer atlayabilirsiniz belirli bir hedef. Bu örnekte, derleme sonra ancak bağlama önce özel adım gerçekleştirir.  
  
    ```  
    <PropertyGroup>  
      <CustomBuildAfterTargets>ClCompile</CustomBuildAfterTargets>  
      <CustomBuildBeforeTargets>Link</CustomBuildBeforeTargets>  
    </PropertyGroup>  
    ```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İzlenecek yol: Visual C++ projesi oluşturmak için MSBuild kullanma](../build/walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)   
 [Nasıl yapılır: MSBuild projelerinde derleme olaylarını kullanma](../build/how-to-use-build-events-in-msbuild-projects.md)   
 [Nasıl Yapılır: MSBuild Projelerine Özel Derleme Adımı Ekleme](../build/how-to-add-a-custom-build-step-to-msbuild-projects.md)