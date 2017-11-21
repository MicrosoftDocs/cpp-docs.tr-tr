---
title: "Derleyici Uyarısı (düzey 1) C4744 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4744
dev_langs: C++
helpviewer_keywords: C4744
ms.assetid: f2a7d0b5-afd5-4926-abc3-cfbd367e3ff5
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 75f06d9edff4d437c841a022193e276505c8b1b6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4744"></a>Derleyici Uyarısı (düzey 1) C4744
'var' 'dosya1' ve 'dosya2' farklı türe sahip: 'type1' ve 'type2'  
  
 Başvurulan veya iki dosyasında tanımlanan bir dış değişkeni, bu dosyaları farklı türleri vardır.  Çözmek için aynı tür tanımları olun veya dosyalarından biri, değişken adını değiştirin.  
  
 Yalnızca dosya ile /GL. derlendiğinde C4744 yayılan  Daha fazla bilgi için bkz: [/GL (bütün Program iyileştirmesi)](../../build/reference/gl-whole-program-optimization.md).  
  
> [!NOTE]
>  C++'da bir değişken adı türü bilgileri ile donatılmış olduğundan C4744 genellikle C (C++ değil) dosyalarında ortaya çıkar.  (Aşağıda) örnek C++ derlerken olduğunda, bağlayıcı hatası LNK2019 alırsınız.  
  
## <a name="example"></a>Örnek  
 Bu örnek ilk tanım içerir.  
  
```  
// C4744.c  
// compile with: /c /GL  
int global;  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4744 oluşturur.  
  
```  
// C4744b.c  
// compile with: C4744.c /GL /W1  
// C4744 expected  
#include <stdio.h>  
  
extern unsigned global;  
  
main()   
{  
    printf_s("%d\n", global);  
}  
```