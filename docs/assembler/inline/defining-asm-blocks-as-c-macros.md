---
title: "__Asm bloklarını C makroları olarak tanımlama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- macros, __asm blocks
- Visual C, macros
- __asm keyword [C++], as C macros
ms.assetid: 677ba11c-21c8-4609-bba7-cd47312243b0
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7b2751e966f93b760898b6869ffa684f4fed323c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="defining-asm-blocks-as-c-macros"></a>__asm Bloklarını C Makroları olarak tanımlama
**Microsoft özel**  
  
 C makroları kaynak kodunuza bütünleştirilmiş kodu eklemek için kolay bir yol sunar ancak makro tek bir mantıksal satıra genişlettiğinden bunlar ek dikkatli talep. Sorunsuz makrolar oluşturmak için bu kurallar izleyin:  
  
-   İçine `__asm` ayraçlar içinde engelleyin.  
  
-   PUT `__asm` anahtar sözcüğü her derleme yönergesi önünde.  
  
-   Eski Tarz C açıklamaları kullanın ( `/* comment */`) derleme stili açıklamaları yerine ( `; comment`) veya tek satırlık C açıklamaları ( `// comment`).  
  
 Göstermek için aşağıdaki örnekte basit makrosu tanımlar:  
  
```  
#define PORTIO __asm      \  
/* Port output */         \  
{                         \  
   __asm mov al, 2        \  
   __asm mov dx, 0xD007   \  
   __asm out dx, al       \  
}  
```  
  
 İlk bakışta son üç `__asm` anahtar sözcükler gibi görünebilir gereksiz. Makro tek bir satıra genişlettiğinden bunlar, ancak gerekir:  
  
```  
__asm /* Port output */ { __asm mov al, 2  __asm mov dx, 0xD007 __asm out dx, al }  
```  
  
 Üçüncü ve dördüncü `__asm` anahtar sözcükleri deyimi ayırıcı olarak gereklidir. İçinde yalnızca deyimi ayırıcılar tanınan `__asm` taşlarıdır yeni satır karakteri ve `__asm` anahtar sözcüğü. Bir mantıksal satır makro olarak tanımlanan bir blok bağlı olduğundan, her talimatıyla ayırmalısınız `__asm`.  
  
 Küme ayraçları de gereklidir. Bunları atlarsanız, derleyicinin C veya C++ deyimleri makrosu çağırma sağındaki aynı satırda çakışabilir. Kapatılan parantez derleyici burada bütünleştirilmiş kodu durdurur ve onu bildiremez C veya C++ deyimleri görür `__asm` bloğu derleme yönergeleri olarak.  
  
 Noktalı virgül Başlat derleme stili açıklamaları (**;**) satırın sonuna kadar devam edin. Her şeyi yoksayar derleyici açıklama, tüm mantıksal satırın sonuna sonra çünkü bu makroları sorunlara neden olur. Aynı tek satırlı C veya C++ açıklamaları geçerlidir ( `// comment`). Hataları önlemek için eski Tarz C açıklamaları kullanın ( `/* comment */`) içinde `__asm` makroları olarak tanımlanan engeller.  
  
 Bir `__asm` C makrosu bağımsız değişkenleri alabilir olarak yazılmış bloğu. Bir sıradan C makrosu, ancak, farklı bir `__asm` makrosu bir değer döndüremiyor. Bu nedenle C veya C++ ifadelerinde bu tür makroları kullanamazsınız.  
  
 Bu tür makroları ölçüsüzce çağırma kullanılamaz dikkat edin. Örneğin, bir derleme dili makrosu bir işlev Çağırma ile bildirilen `__fastcall` kuralı beklenmeyen sonuçlara neden olabilir. (Bkz [kullanma ve satır içi derlemede kayıtları koruma](../../assembler/inline/using-and-preserving-registers-in-inline-assembly.md).)  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Satır içi derleyicisi](../../assembler/inline/inline-assembler.md)