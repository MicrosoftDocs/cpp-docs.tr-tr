---
title: Derleyici Uyarısı (düzey 1) C4744 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4744
dev_langs:
- C++
helpviewer_keywords:
- C4744
ms.assetid: f2a7d0b5-afd5-4926-abc3-cfbd367e3ff5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7a45207f85575c8047f673b415ce802dbac24318
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33282834"
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