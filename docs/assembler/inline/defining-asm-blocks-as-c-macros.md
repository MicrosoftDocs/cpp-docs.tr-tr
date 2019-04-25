---
title: __asm Bloklarını C Makroları olarak tanımlama
ms.date: 08/30/2018
helpviewer_keywords:
- macros, __asm blocks
- Visual C, macros
- __asm keyword [C++], as C macros
ms.assetid: 677ba11c-21c8-4609-bba7-cd47312243b0
ms.openlocfilehash: c48298cf802600995dbbf68885896b6feccb807d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62167032"
---
# <a name="defining-asm-blocks-as-c-macros"></a>__asm Bloklarını C Makroları olarak tanımlama

**Microsoft'a özgü**

C makroları kaynak kodunuza bütünleştirilmiş kodu eklemek için kullanışlı bir yol sunar, ancak bir makro tek bir mantıksal satıra genişlettiğinden, çok dikkatli talep. Makrolar sorunsuz oluşturmak için bu kuralları izleyin:

- İçine `__asm` bloğunu ayraç içinde.

- PUT `__asm` her bir derleme yönergesinin önüne anahtar sözcüğü.

- Eski stil C açıklamaları kullanın ( `/* comment */`) yerine derleme stili açıklamaları ( `; comment`) veya tek satırlık C açıklamaları ( `// comment`).

Aşağıdaki örnek, göstermek için basit bir makro tanımlar:

```cpp
#define PORTIO __asm      \
/* Port output */         \
{                         \
   __asm mov al, 2        \
   __asm mov dx, 0xD007   \
   __asm out dx, al       \
}
```

İlk bakışta son üç `__asm` anahtar sözcükleri gereksiz görünüyor. Tek bir satıra makro genişler çünkü bunlar, ancak gereklidir:

```cpp
__asm /* Port output */ { __asm mov al, 2  __asm mov dx, 0xD007 __asm out dx, al }
```

Üçüncü ve dördüncü `__asm` anahtar sözcükler, deyim ayırıcısı olarak gereklidir. İçinde yalnızca bir deyim ayırıcısı tanınan `__asm` taşlarıdır yeni satır karakteri ve `__asm` anahtar sözcüğü. Makro olarak tanımlanan bir blok mantıksal bir satır olduğundan, her yönerge ile ayrı `__asm`.

Küme ayraçları de gereklidir. Bunları atlarsanız, derleyici C veya C++ deyimlerinin makro çağrısı sağındaki aynı satırda çakışabilir. Kapanış ayracı derleyici burada bütünleştirilmiş kodu durdurur ve bu bildiremez C veya C++ deyimlerinin görür `__asm` blok olarak derleme yönergeleri.

Noktalı virgül ile başlayan açıklamaları bütünleştirilmiş kod stili (**;**) satırın sonuna kadar devam edin. Her şeyi yoksayar derleyici yorumundan mantıksal satırın sonuna kadar çünkü bu makrolar sorunlara neden olur. C veya C++ tek satırlı yorumlar aynı geçerlidir ( `// comment`). Hataları önlemek için eski stil C açıklamaları kullanın ( `/* comment */`) içinde `__asm` blokları makrolar tanımlanır.

Bir `__asm` C makro bağımsız değişken alabilir olarak yazılmış bir blok. Bir normal C makrosu, ancak farklı bir `__asm` makrosu değer döndüremez. Bu nedenle, C veya C++ ifadelerinde bu tür makroları kullanamazsınız.

Bu tür makroları incelemelerin çağırma kullanılamaz dikkat edin. Örneğin, bir derleme dili makro bir işlev Çağırma ile bildirilen `__fastcall` kuralı, beklenmeyen sonuçlara neden olabilir. (Bkz [satır içi bütünleştirilmiş kodda kayıtları kullanma ve koruma](../../assembler/inline/using-and-preserving-registers-in-inline-assembly.md).)

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Satır İçi Assembler](../../assembler/inline/inline-assembler.md)<br/>