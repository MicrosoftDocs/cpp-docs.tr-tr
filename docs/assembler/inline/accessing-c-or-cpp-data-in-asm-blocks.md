---
title: __asm Bloklarında C veya C++ Verilerine Erişme
ms.date: 08/30/2018
helpviewer_keywords:
- data members [C++], in __asm blocks
- data access [C++], in __asm blocks
- __asm keyword [C++], data members
- structure types in __asm blocks
ms.assetid: e99f5a28-0381-4090-8ece-6af8f2436a49
ms.openlocfilehash: 1f56cc5c049c1501ea09c76f31be3ab9dea5ed10
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50433065"
---
# <a name="accessing-c-or-c-data-in-asm-blocks"></a>__asm Bloklarında C veya C++ Verilerine Erişme

**Microsoft'a özgü**

Satır içi derlemenin harika bir kolaylık sağlamak adına göre C veya C++ değişkenlerine başvurmak için yeteneğidir. Bir `__asm` blok kapsamlı bloğunu göründüğü değişken adları da dahil olmak üzere tüm sembolleri başvurabilir. Örneğin, C değişkeni `var` kapsamındaki yönergesi

```cpp
__asm mov eax, var
```

değerini depolar `var` eax'daki.

Bir sınıf, yapı veya birleşim üyesi benzersiz bir ad varsa bir `__asm` bloğu değişkeni belirtmeden üye adı yalnızca kendisine başvurabilir veya `typedef` süre önce ad (**.**) işleci. Ancak, üye adı benzersiz değilse, bir değişken yerleştirmeniz gerekir veya `typedef` hemen önce dönem işleç adı. Örneğin, aşağıdaki örnek paylaşımı yapısı türlerini `same_name` kendi üye adıyla:.

Değişkenleri türlerle bildirirseniz

```cpp
struct first_type hal;
struct second_type oat;
```

tüm başvuruları üye `same_name` değişken adı kullanmanız gerekir çünkü `same_name` benzersiz değil. Ancak üye `weasel` benzersiz bir ad olduğundan, yalnızca üye adını kullanarak başvurabilirsiniz:

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

Değişken adı atlama yalnızca bir kodlama kullanışlı olduğunu unutmayın. Değişken adı mevcut olup olmadığını aynı derleme yönergelerini oluşturulur.

C++ veri üyelerine erişim kısıtlamalarını dikkate almaksızın erişebilirsiniz. Ancak, üye işlevleri çağrılamıyor.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__asm Bloklarında C veya C++ Kullanma](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)<br/>