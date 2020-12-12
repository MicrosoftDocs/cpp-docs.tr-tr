---
description: 'Hakkında daha fazla bilgi edinin: __asm bloklarında C veya C++ verilerine erişme'
title: __asm Bloklarında C veya C++ Verilerine Erişme
ms.date: 08/30/2018
helpviewer_keywords:
- data members [C++], in __asm blocks
- data access [C++], in __asm blocks
- __asm keyword [C++], data members
- structure types in __asm blocks
ms.assetid: e99f5a28-0381-4090-8ece-6af8f2436a49
ms.openlocfilehash: b24d25b5687dd309c400b17c1e0eb6b35ef986f2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97118088"
---
# <a name="accessing-c-or-c-data-in-__asm-blocks"></a>__asm Bloklarında C veya C++ Verilerine Erişme

**Microsoft'a Özgü**

Satır içi derlemenin harika bir kolaylığı, C veya C++ değişkenlerini ada göre ifade edebilmesidir. Bir **`__asm`** blok, bloğun göründüğü kapsamda değişken adları dahil tüm simgelere başvurabilir. Örneğin, C değişkeni `var` kapsamdadır, yönerge

```cpp
__asm mov eax, var
```

değerini `var` EAX içinde depolar.

Bir sınıf, yapı veya birleşim üyesinin benzersiz bir adı varsa, bir blok, **`__asm`** **`typedef`** nokta (**.**) işlecinden önce değişkeni veya adı belirtmeden yalnızca üye adını kullanarak buna başvurabilir. Ancak üye adı benzersiz değilse, **`typedef`** nokta işlecinden hemen önce bir değişkeni veya adı yerleştirmeniz gerekir. Örneğin, aşağıdaki örnek paylaşımında bulunan yapı türleri `same_name` üye adı:.

Türler ile değişkenler bildirirseniz

```cpp
struct first_type hal;
struct second_type oat;
```

üyenin tüm başvuruları `same_name` değişken adını kullanmalıdır çünkü `same_name` benzersiz değil. Ancak üyenin `weasel` benzersiz bir adı vardır, bu yüzden yalnızca üye adını kullanarak buna başvurabilirsiniz:

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

Değişken adını atlayarak yalnızca bir kodlama rahatlığını unutmayın. Aynı derleme yönergeleri, değişken adının mevcut olup olmadığına bakılmaksızın oluşturulur.

Erişim kısıtlamalarına bakmaksızın C++ ' daki veri üyelerine erişebilirsiniz. Ancak, üye işlevleri çağrılamaz.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__Asm bloklarında C veya C++ kullanma](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)<br/>
