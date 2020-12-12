---
description: Hakkında daha fazla bilgi edinin:. Bağlayıcı girişi olarak lib dosyaları
title: Bağlayıcı Girişi olarak .Lib Dosyaları
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.AdditionalDependencies
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
ms.openlocfilehash: f4a3b6c6487947772fb72135fb26f67857f0937e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201267"
---
# <a name="lib-files-as-linker-input"></a>Bağlayıcı Girişi olarak .Lib Dosyaları

BAĞLANTı, genellikle. lib uzantısına sahip olan COFF standart kitaplıklarını ve COFF içeri aktarma kitaplıklarını kabul eder. Standart kitaplıklar nesneleri içerir ve LıB aracı tarafından oluşturulur. İçeri aktarma kitaplıkları, diğer programlardaki dışarı aktarmalar hakkında bilgi içerir ve dışarı aktarmalar ya da LıB aracı tarafından oluşturulan bir program oluşturduğunda bağlantı tarafından oluşturulur. Standart veya içeri aktarma kitaplığı oluşturmak üzere LıB kullanma hakkında bilgi için, bkz. [LIB Reference](lib-reference.md). İçeri aktarma kitaplığı oluşturmak için bağlantı kullanma hakkında ayrıntılı bilgi için bkz. [/DLL](dll-build-a-dll.md) seçeneği.

Bir kitaplık, bir dosya adı bağımsız değişkeni ya da varsayılan kitaplık olarak bağlanacak şekilde belirtilir. BAĞLANTı, ilk olarak komut satırında belirtilen kitaplıklarda arama yaparak dış başvuruları çözer, ardından varsayılan kitaplıklarda [/defaultlib](defaultlib-specify-default-library.md) seçeneğiyle belirtilen varsayılan kitaplıklarda ve. obj dosyalarında adlı varsayılan kitaplıklarda. Kitaplık adıyla bir yol belirtilirse, bağlantı bu dizindeki kitaplığı arar. Yol belirtilmemişse, bağlantı önce BAĞLANTıNıN üzerinde çalıştığı dizinde, sonra LıB ortam değişkeninde belirtilen dizinlerde görünür.

## <a name="to-add-lib-files-as-linker-input-in-the-development-environment"></a>Geliştirme ortamında bağlayıcı girişi olarak. lib dosyaları eklemek için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Bağlayıcı** klasöründe **giriş** özelliği sayfasını seçin.

1. . Lib dosyalarını eklemek için **ek bağımlılıklar** özelliğini değiştirin.

## <a name="to-programmatically-add-lib-files-as-linker-input"></a>Program aracılığıyla. lib dosyalarını bağlayıcı girişi olarak eklemek için

- [AdditionalDependencies](/dotnet/api/microsoft.visualstudio.vcprojectengine.vclinkertool.additionaldependencies)'e bakın.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir. lib dosyasının nasıl oluşturulacağını ve kullanılacağını göstermektedir. İlk olarak, bir. lib dosyası oluşturun:

```cpp
// lib_link_input_1.cpp
// compile by using: cl /LD lib_link_input_1.cpp
__declspec(dllexport) int Test() {
   return 213;
}
```

Ardından, yeni oluşturduğunuz. lib dosyasını kullanarak bu örneği derleyin:

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

## <a name="see-also"></a>Ayrıca bkz.

[Giriş dosyalarını bağlama](link-input-files.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
