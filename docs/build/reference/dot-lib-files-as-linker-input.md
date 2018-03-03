---
title: ". Bağlayıcı girişi dosyaları lib | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.AdditionalDependencies
dev_langs:
- C++
helpviewer_keywords:
- OMF libraries
- linking [C++], OMF libraries
- import libraries, linker files
- libraries [C++], .lib files as linker input
- COFF files, import libraries
- default libraries [C++], linker output
- default libraries [C++]
- defaults [C++], libraries
- .lib files
ms.assetid: dc5d2b1c-2487-41fa-aa71-ad1e0647958b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 181c8c3e5e762f2f20d99ca2acadaf285e717b6c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="lib-files-as-linker-input"></a>Bağlayıcı Girişi olarak .Lib Dosyaları
BAĞLANTI kabul COFF standart kitaplıkları ve COFF içeri aktarma kitaplıkları, her ikisi de genellikle sahip uzantısı. lib. Standart kitaplıkları nesneleri içerir ve LIB aracı tarafından oluşturulur. İçeri aktarma kitaplıkları ya da bağlantı dışarı aktarmaları içeren bir program oluşturduğunda veya LIB aracı tarafından oluşturulan ve diğer programlarda dışarı ilgili bilgiler içerir. Standart oluşturmak veya kitaplıkları içeri aktarma için LIB kullanma hakkında daha fazla bilgi için bkz: [LIB başvurusu](../../build/reference/lib-reference.md). İçeri aktarma kitaplığı oluşturmak için bağlantı kullanma hakkında daha fazla bilgi için bkz [/dll](../../build/reference/dll-build-a-dll.md) seçeneği.  
  
Kitaplığa bağlantı bir dosya adı bağımsız değişkeni veya varsayılan kitaplık olarak belirtilir. BAĞLANTI, komut satırında belirtilen kitaplıklarında ilk arayarak dış başvuruları çözümler ve ardından varsayılan kitaplıkları ile belirtilen [/DEFAULTLIB](../../build/reference/defaultlib-specify-default-library.md) seçeneğini ve ardından varsayılan kitaplıkları adlı .obj dosyaları. Bir yol kitaplığı adı ile belirtilirse, bu dizine kitaplıkta bağlantı arar. Yol belirtilmezse, bağlantıyı bağlantı çalıştıran dizininde, ardından LIB ortam değişkeninde belirtilen herhangi bir dizin ilk durur.  
  
## <a name="to-add-lib-files-as-linker-input-in-the-development-environment"></a>Geliştirme ortamında bağlayıcı girişi olarak .lib dosyaları eklemek için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Seçin **giriş** özellik sayfasında **bağlayıcı** klasör.  
  
3.  Değiştirme **ek bağımlılıklar** .lib dosyaları ekleme özelliği.  
  
## <a name="to-programmatically-add-lib-files-as-linker-input"></a>Bağlayıcı girişi .lib dosyaları programlı olarak ekleme  
  
-   Bkz: [AdditionalDependencies](https://msdn.microsoft.com/library/microsoft.visualstudio.vcprojectengine.vclinkertool.additionaldependencies.aspx).  
  
## <a name="example"></a>Örnek  
Aşağıdaki örnek .lib dosyası oluşturun ve nasıl kullanılacağını gösterir. İlk olarak, bir .lib dosyası oluşturun:  
  
```cpp  
// lib_link_input_1.cpp  
// compile by using: cl /LD lib_link_input_1.cpp  
__declspec(dllexport) int Test() {  
   return 213;  
}  
```  
  
Ve ardından yeni oluşturduğunuz .lib dosyası kullanarak bu örnek derleyin:  
  
```cpp  
// lib_link_input_2.cpp  
// compile by using: cl /EHsc lib_link_input_1.lib lib_link_input_2.cpp   
__declspec(dllimport) int Test();  
#include <iostream>  
int main() {  
   std::cout << Test() << std::endl;  
}  
```  
  
```Output  
213  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [LINK giriş dosyaları](../../build/reference/link-input-files.md)   
 [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)