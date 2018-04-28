---
title: __Asm bloklarında C veya C++ simgelerini kullanma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- __asm keyword [C++], syntax
- symbols, in __asm blocks
- Visual C, symbols in __asm blocks
- __asm keyword [C++], C/C++ elements in
- Visual C++, in __asm blocks
ms.assetid: 0758ffdc-dfe9-41c8-a5e1-fd395bcac328
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 746614de653649747bf20ae4c223e5687ee53f5c
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2018
---
# <a name="using-c-or-c-symbols-in-asm-blocks"></a>__asm Bloklarında C veya C++ Simgelerini Kullanma
## <a name="microsoft-specific"></a>Microsoft'a Özgü  
 Bir `__asm` blok herhangi bir C veya C++ simge blok göründüğü kapsamında başvurabilir. (C ve C++ simgelerdir değişken adları, işlev adları ve etiketleri; sembolik sabitler olmayan adları veya `enum` üyeleri. C++ üye işlevlerini çağıramazsınız.)  
  
 C ve C++ simgelerini kullanmak için bazı kısıtlamalar:  
  
-   Her derleme dili bildirimi yalnızca bir C veya C++ sembol içerebilir. Birden çok simge yalnızca aynı derleme yönergesindeki görünebilir **UZUNLUĞU**, **türü**, ve **BOYUTU** ifadeler.  
  
-   Başvurulan işlevleri bir `__asm` blok bildirilmelidir (daha önce programın örneklenmiş). Aksi takdirde derleyici işlev adları ve etiketler ayırt edemiyor `__asm` bloğu.  
  
-   Bir `__asm` blok MASM ayrılmış sözcükler (bağımsız olarak durumda) olarak aynı yazım ile C veya C++ semboller kullanamazsınız. MASM ayrılmış sözcükler dahil yönerge adları gibi **anında** ve sı gibi adlar kaydedin.  
  
-   Yapı ve birleşim etiketleri tanınmıyor içinde `__asm` engeller.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [__asm Bloklarında C veya C++ Kullanma](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)