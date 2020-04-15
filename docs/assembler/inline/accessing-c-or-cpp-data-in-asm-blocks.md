---
title: __asm Bloklarında C veya C++ Verilerine Erişme
ms.date: 08/30/2018
helpviewer_keywords:
- data members [C++], in __asm blocks
- data access [C++], in __asm blocks
- __asm keyword [C++], data members
- structure types in __asm blocks
ms.assetid: e99f5a28-0381-4090-8ece-6af8f2436a49
ms.openlocfilehash: b4341f87226118906749dcdb18b9227e68be6a23
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318086"
---
# <a name="accessing-c-or-c-data-in-__asm-blocks"></a>__asm Bloklarında C veya C++ Verilerine Erişme

**Microsoft'a Özgü**

Satır aralarının büyük kolaylığı, C veya C++ değişkenlerine ada göre başvurma yeteneğidir. Blok, `__asm` bloğun göründüğü kapsamda değişken adları da dahil olmak üzere tüm sembollere başvurabilir. Örneğin, C değişkeni `var` kapsam içindeyse, yönerge

```cpp
__asm mov eax, var
```

değerini `var` EAX'ta saklar.

Bir sınıf, yapı veya sendika üyesinin benzersiz `__asm` bir adı varsa, bir blok, dönem ( `typedef` **.**) işlecinden önce değişkeni veya adı belirtmeden yalnızca üye adını kullanarak bu ada başvurabilir. Ancak üye adı benzersiz değilse, dönem işlecinden `typedef` hemen önce bir değişken veya ad yerleştirmeniz gerekir. Örneğin, aşağıdaki örnekteki `same_name` yapı türleri üye adı olarak paylaş:.

Değişkenleri türleri ile bildirirseniz

```cpp
struct first_type hal;
struct second_type oat;
```

üyeye `same_name` yapılan tüm başvurular değişken `same_name` adını kullanmalıdır, çünkü benzersiz değildir. Ancak üyenin `weasel` benzersiz bir adı vardır, bu nedenle yalnızca üye adını kullanarak bu adı başvurabilirsiniz:

```cpp
// InlineAssembler_Accessing_C_asm_Blocks.cpp
// processor: x86
#include <stdio.h>
struct first_type
{
   char *weasel;
   int same_name;
};

struct second_type
{
   int wonton;
   long same_name;
};

int main()
{
   struct first_type hal;
   struct second_type oat;

   __asm
   {
      lea ebx, hal
      mov ecx, [ebx]hal.same_name ; Must use 'hal'
      mov esi, [ebx].weasel       ; Can omit 'hal'
   }
   return 0;
}
```

Değişken adını atlayarak yalnızca bir kodlama kolaylığı olduğunu unutmayın. Değişken adı olup olmadığı aynı derleme yönergeleri oluşturulur.

C++'daki veri üyelerine erişim kısıtlamalarına bakılmaksızın erişebilirsiniz. Ancak, üye işlevleri arayamazsınız.

**END Microsoft Özel**

## <a name="see-also"></a>Ayrıca bkz.

[__asm Bloklarında C veya C++ Kullanma](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)<br/>
