---
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
ms.openlocfilehash: 02f719b3101b04ad6b219bf882a50a994061af0c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62293647"
---
# <a name="lib-files-as-linker-input"></a>Bağlayıcı Girişi olarak .Lib Dosyaları

BAĞLANTIYI kabul eden COFF standart kitaplıkları ve COFF içeri aktarma kitaplıkları, ikisi için de genellikle uzantılıdır. LIB. Standart kitaplıkları nesneleri içerir ve LIB araç tarafından oluşturulur. İçeri aktarma kitaplıkları diğer programlarda dışarı aktarmalar hakkında bilgiler içerir ve bağlantı tarafından dışarı aktarmaları içeren bir program oluşturduğunda veya LIB aracı tarafından oluşturulur. LIB standart oluşturmak veya kitaplıkları içeri aktarma için kullanma hakkında daha fazla bilgi için bkz: [LIB başvurusu](lib-reference.md). İçeri aktarma kitaplığı oluşturmak için bağlantıyı kullanarak hakkında daha fazla bilgi için bkz [/dll](dll-build-a-dll.md) seçeneği.

Kitaplığa bağlantı bir dosya adı bağımsız değişkeni ya da varsayılan kitaplık olarak belirtilir. İlk komut satırında belirtilen kitaplıklarda arama yaparak bağlantı dış başvuruları çözümleniyor ve kitaplıkları varsayılan belirtilen [/DEFAULTLIB](defaultlib-specify-default-library.md) seçeneğini ve ardından varsayılan kitaplıkları adlı .obj dosyalarında. Kitaplık adı ile bir yol belirtilmezse, bağlantıyı bu dizine kitaplıkta arar. Hiçbir yol belirtilmezse, bağlantı ilk bağlantı çalıştıran dizinde ve LIB ortam değişkeninde belirtilen dizinde arar.

## <a name="to-add-lib-files-as-linker-input-in-the-development-environment"></a>Geliştirme ortamındaki bağlayıcı girişi olarak .lib dosyaları eklemek için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Seçin **giriş** özellik sayfasında **bağlayıcı** klasör.

1. Değiştirme **ek bağımlılıklar** .lib dosyaları ekleme özelliği.

## <a name="to-programmatically-add-lib-files-as-linker-input"></a>Program aracılığıyla bağlayıcı girişi .lib dosyaları eklemek için

- Bkz: [AdditionalDependencies](/dotnet/api/microsoft.visualstudio.vcprojectengine.vclinkertool.additionaldependencies).

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir .lib dosyası oluşturup gösterilmektedir. İlk olarak, bir .lib dosyası oluşturun:

```cpp
// lib_link_input_1.cpp
// compile by using: cl /LD lib_link_input_1.cpp
__declspec(dllexport) int Test() {
   return 213;
}
```

Ve ardından yeni oluşturduğunuz .lib dosyası kullanarak bu örneği derleyin:

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

[LINK Giriş Dosyaları](link-input-files.md)<br/>
[MSVC Bağlayıcı Seçenekleri](linker-options.md)
