---
description: 'Hakkında daha fazla bilgi edinin: __asm bloklarını C makroları olarak tanımlama'
title: __asm Bloklarını C Makroları olarak tanımlama
ms.date: 08/30/2018
helpviewer_keywords:
- macros, __asm blocks
- Visual C, macros
- __asm keyword [C++], as C macros
ms.assetid: 677ba11c-21c8-4609-bba7-cd47312243b0
ms.openlocfilehash: a0fe13acdd5a75fd86fd8107396632a5c6e7c283
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97117843"
---
# <a name="defining-__asm-blocks-as-c-macros"></a>__asm Bloklarını C Makroları olarak tanımlama

**Microsoft'a Özgü**

C makroları, kaynak kodunuza derleme kodu eklemek için kullanışlı bir yol sunar, ancak bir makro tek bir mantıksal satıra genişletiğinden ek bir değer talep ederler. Sorun içermeyen makrolar oluşturmak için bu kuralları izleyin:

- **`__asm`** Bloğu küme ayraçları içine alın.

- **`__asm`** Anahtar sözcüğünü her derleme yönergesinin önüne koyun.

- `/* comment */`Bütünleştirilmiş kod stili açıklamaları ( `; comment` ) veya tek satırlık c açıklamaları () yerine eski stil c açıklamalarını () kullanın `// comment` .

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

İlk bakışta, son üç **`__asm`** anahtar sözcük gereksiz görünür. Ancak, makro tek bir satıra genişletiğinden, bunlar gereklidir:

```cpp
__asm /* Port output */ { __asm mov al, 2  __asm mov dx, 0xD007 __asm out dx, al }
```

Üçüncü ve dördüncü **`__asm`** anahtar sözcükler, ifade ayırıcıları olarak gereklidir. **`__asm`** Bloklara tanınan tek deyimler, yeni satır karakteri ve **`__asm`** anahtar kelimedir. Makro olarak tanımlanan bir blok tek bir mantıksal satır olduğundan, her yönergeyi ile ayırmanız gerekir **`__asm`** .

Küme ayraçları da temel öneme sahiptir. Bunları atlarsanız, derleyici, makro çağrısının sağında aynı satırdaki C veya C++ deyimleri tarafından karışıyor olabilir. Kapanış küme ayracı olmadan derleyici, derleme kodunun nerede durdurduğunu söyleyebilir ve **`__asm`** derleme yönergeleri olarak bloğundan sonra C veya C++ deyimlerini görür.

Noktalı virgül (**;**) ile başlayan derleme stili açıklamalar satırın sonuna kadar devam eder. Bu, derleyici açıklamadan sonra, mantıksal satırın sonuna kadar olan her şeyi yok saydığı için makrolarda sorunlara yol açar. Aynı, tek satırlık C veya C++ yorumlarının () aynısını de doğrudur `// comment` . Hataları engellemek için `/* comment */` **`__asm`** makrolar olarak tanımlanan bloklarda eski stil C açıklamalarını () kullanın.

**`__asm`** C makrosu olarak yazılmış bir blok bağımsız değişken alabilir. Ancak sıradan bir C makrosunun aksine, bir **`__asm`** makro bir değer döndüremez. Bu nedenle, C veya C++ ifadelerinde bu makroları kullanamazsınız.

Bu tür sayısının fark gözetmeden makroları çağırmamaya dikkat edin. Örneğin, kurala göre belirtilen bir işlevde derleme dili makrosunu çağırmak **`__fastcall`** beklenmedik sonuçlara neden olabilir. (Bkz. [satır Içi derlemede kayıtları kullanma ve koruma](../../assembler/inline/using-and-preserving-registers-in-inline-assembly.md).)

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Satır içi assembler](../../assembler/inline/inline-assembler.md)<br/>
