---
title: . Bağlayıcı girişi dosyaları lib | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 774fe236b66bbe6222956de05efbfe89fab3de9f
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45706504"
---
# <a name="lib-files-as-linker-input"></a>Bağlayıcı Girişi olarak .Lib Dosyaları

BAĞLANTIYI kabul eden COFF standart kitaplıkları ve COFF içeri aktarma kitaplıkları, ikisi için de genellikle uzantılıdır. LIB. Standart kitaplıkları nesneleri içerir ve LIB araç tarafından oluşturulur. İçeri aktarma kitaplıkları diğer programlarda dışarı aktarmalar hakkında bilgiler içerir ve bağlantı tarafından dışarı aktarmaları içeren bir program oluşturduğunda veya LIB aracı tarafından oluşturulur. LIB standart oluşturmak veya kitaplıkları içeri aktarma için kullanma hakkında daha fazla bilgi için bkz: [LIB başvurusu](../../build/reference/lib-reference.md). İçeri aktarma kitaplığı oluşturmak için bağlantıyı kullanarak hakkında daha fazla bilgi için bkz [/dll](../../build/reference/dll-build-a-dll.md) seçeneği.

Kitaplığa bağlantı bir dosya adı bağımsız değişkeni ya da varsayılan kitaplık olarak belirtilir. İlk komut satırında belirtilen kitaplıklarda arama yaparak bağlantı dış başvuruları çözümleniyor ve kitaplıkları varsayılan belirtilen [/DEFAULTLIB](../../build/reference/defaultlib-specify-default-library.md) seçeneğini ve ardından varsayılan kitaplıkları adlı .obj dosyalarında. Kitaplık adı ile bir yol belirtilmezse, bağlantıyı bu dizine kitaplıkta arar. Hiçbir yol belirtilmezse, bağlantı ilk bağlantı çalıştıran dizinde ve LIB ortam değişkeninde belirtilen dizinde arar.

## <a name="to-add-lib-files-as-linker-input-in-the-development-environment"></a>Geliştirme ortamındaki bağlayıcı girişi olarak .lib dosyaları eklemek için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Seçin **giriş** özellik sayfasında **bağlayıcı** klasör.

1. Değiştirme **ek bağımlılıklar** .lib dosyaları ekleme özelliği.

## <a name="to-programmatically-add-lib-files-as-linker-input"></a>Program aracılığıyla bağlayıcı girişi .lib dosyaları eklemek için

- Bkz: [AdditionalDependencies](https://msdn.microsoft.com/library/microsoft.visualstudio.vcprojectengine.vclinkertool.additionaldependencies.aspx).

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

## <a name="see-also"></a>Ayrıca Bkz.

[LINK Giriş Dosyaları](../../build/reference/link-input-files.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)