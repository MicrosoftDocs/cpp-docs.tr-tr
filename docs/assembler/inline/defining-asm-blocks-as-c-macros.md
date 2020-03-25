---
title: __asm Bloklarını C Makroları olarak tanımlama
ms.date: 08/30/2018
helpviewer_keywords:
- macros, __asm blocks
- Visual C, macros
- __asm keyword [C++], as C macros
ms.assetid: 677ba11c-21c8-4609-bba7-cd47312243b0
ms.openlocfilehash: 46f0a23fcfd949843e3548354f52970b10b6d63b
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80169493"
---
# <a name="defining-__asm-blocks-as-c-macros"></a>__asm Bloklarını C Makroları olarak tanımlama

**Microsoft 'a özgü**

C makroları, kaynak kodunuza derleme kodu eklemek için kullanışlı bir yol sunar, ancak bir makro tek bir mantıksal satıra genişletiğinden ek bir değer talep ederler. Sorun içermeyen makrolar oluşturmak için bu kuralları izleyin:

- `__asm` bloğunu ayraç içine alın.

- `__asm` anahtar sözcüğünü her derleme yönergesinin önüne koyun.

- Bütünleştirilmiş kod stili açıklamaları (`; comment`) veya tek satırlık C açıklamaları (`// comment`) yerine eski stil C açıklamalarını (`/* comment */`) kullanın.

Göstermek için aşağıdaki örnekte basit bir makro tanımlanmaktadır:

```cpp
#define PORTIO __asm      \
/* Port output */         \
{                         \
   __asm mov al, 2        \
   __asm mov dx, 0xD007   \
   __asm out dx, al       \
}
```

İlk bakışta, son üç `__asm` anahtar sözcüğü gereksiz görünür. Ancak, makro tek bir satıra genişletiğinden, bunlar gereklidir:

```cpp
__asm /* Port output */ { __asm mov al, 2  __asm mov dx, 0xD007 __asm out dx, al }
```

Üçüncü ve dördüncü `__asm` anahtar sözcükleri, ifade ayırıcıları olarak gereklidir. `__asm` bloklarından tanınan tek deyimli ayırıcı, yeni satır karakteri ve `__asm` anahtar kelimedir. Makro olarak tanımlanan bir blok tek bir mantıksal satır olduğundan, her yönergeyi `__asm`ayırmanız gerekir.

Küme ayraçları da temel öneme sahiptir. Bunları atlarsanız, derleyici, makro çağrısının sağında aynı satırdaki C veya C++ deyimler tarafından karışıyor olabilir. Kapanış küme ayracı olmadan derleyici, derleme kodunun nerede durdurduğunu söyleyebilir ve derleme yönergeleri olarak `__asm` bloğundan sonra C++ C veya deyimlerini görür.

Noktalı virgül ( **;** ) ile başlayan derleme stili açıklamalar satırın sonuna kadar devam eder. Bu, derleyici açıklamadan sonra, mantıksal satırın sonuna kadar olan her şeyi yok saydığı için makrolarda sorunlara yol açar. Aynı, tek satırlık C veya C++ yorumların (`// comment`) de doğrudur. Hataları engellemek için, makro olarak tanımlanan `__asm` bloklarda eski stil C açıklamalarını (`/* comment */`) kullanın.

C makrosu olarak yazılan `__asm` bloğu bağımsız değişkenler alabilir. Ancak sıradan bir C makrosunun aksine, bir `__asm` makrosu bir değer döndüremez. Bu nedenle, bu makroları C veya C++ ifadelerinde kullanamazsınız.

Bu tür sayısının fark gözetmeden makroları çağırmamaya dikkat edin. Örneğin, bir derleme dili makrosunu `__fastcall` kuralına göre belirtilen bir işlevde çağırmak beklenmedik sonuçlara neden olabilir. (Bkz. [satır Içi derlemede kayıtları kullanma ve koruma](../../assembler/inline/using-and-preserving-registers-in-inline-assembly.md).)

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Satır İçi Assembler](../../assembler/inline/inline-assembler.md)<br/>
