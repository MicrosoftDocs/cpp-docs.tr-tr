---
title: "döngü | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- loop_CPP
- vc-pragma.loop
dev_langs: C++
ms.assetid: 6d5bb428-cead-47e7-941d-7513bbb162c7
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c1bb28abd8ba1bf02e6dff8b508e43d4c761bb98
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="loop"></a>loop
Döngü kodunun otomatik paralel hale getirici tarafından nasıl kullanılacağını denetler ve/veya bir döngünün otomatik vektör hale getirici tarafından dikkate alınmamasını sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
#pragma loop( hint_parallel(n) )  
```  
  
```  
  
#pragma loop( no_vector )  
```  
  
```  
  
#pragma loop( ivdep )  
```  
  
#### <a name="parameters"></a>Parametreler  
 `hint_parallel(` `n` `)`  
 Derleyiciye, bu döngünün `n` iş parçacıklarında paralel hale getirilmesi gerektiğini belirtir; burada `n` bir pozitif tamsayı değişmez değeri ya da sıfırdır. `n` sıfırsa, çalışma zamanında en çok iş parçacığı sayısı kullanılır. Bu komut değil derleyici için yol gösteren bir ipucudur ve döngünün paralel hale getirileceğinin garantisi yoktur. Döngüde veri bağımlılıkları veya yapısal sorunlar varsa (örneğin, döngü, döngü gövdesinin dışında kullanılan bir skalara depoluyor), döngü paralel hale getirilmez.  
  
 Derleyici sürece bu seçeneği yoksayar [/Qpar](../build/reference/qpar-auto-parallelizer.md) derleyici anahtarı belirtilir.  
  
 `no_vector`  
 Varsayılan olarak, otomatik vektör hale getirici açıktır ve ondan yararlanıyor olarak değerlendirdiği tüm döngüleri vektör hale getirmeye çalışır. Kendisini takip eden döngü için, otomatik vektör hale getiriciyi devre dışı bırakmak üzere bu pragmayı belirtin.  
  
 `ivdep`  
 Bu döngü için vektör bağımlılıklarını yoksayma konusunda derleyici için ipuçları. Bunu `hint_parallel` ile birlikte kullanın.  
  
## <a name="remarks"></a>Açıklamalar  
 `loop` pragmasını kullanmak için, onu bir döngü tanımının içine değil hemen öncesine yerleştirin. Pragma, onu takip eden döngü kapsamı için etkili olur. Bir döngüye herhangi bir sırada birden fazla pragma uygulayabilirsiniz, ancak her birini ayrı bir pragma deyimi içinde belirtmelisiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Otomatik Paralelleştirme ve otomatik Vektörleştirme](../parallel/auto-parallelization-and-auto-vectorization.md)   
 [Pragma yönergeleri ve __Pragma anahtar sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)