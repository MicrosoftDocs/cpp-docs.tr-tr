---
title: Setjmp longjmp kullanma | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- longjmp_cpp
- setjmp_cpp
dev_langs: C++
helpviewer_keywords:
- C++ exception handling, setjmp/longjmp functions
- SETJMPEX.H
- longjmp function in C++ programs
- SETJMP.H
- setjmp function
- setjmp function, C++ programs
ms.assetid: 96be8816-f6f4-4567-9a9c-0c3c720e37c5
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1ac0f4cdbce193c7124a816e4baf5f91e13c71de
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="using-setjmplongjmp"></a>setjmp/longjmp Kullanma
Zaman [setjmp](../c-runtime-library/reference/setjmp.md) ve [longjmp](../c-runtime-library/reference/longjmp.md) olan birlikte kullanıldığında, yerel olmayan yürütmek için bir yol sağladıkları `goto`. Bunlar, genellikle standart arama kullanmadan önce çağrılan bir yordam hata işleme veya kurtarma kodunda yürütme denetimi geçirmek için kullanılan veya kuralları döndürür.  
  
> [!CAUTION]
>  Ancak, çünkü `setjmp` ve `longjmp` C++ nesne semantiği desteklemez ve yerel değişkenler en iyi duruma getirilmesi engelleyerek performansını azaltabilir, bunları C++ programlarında kullanmamanızı öneririz. Kullanmanızı öneririz `try` / `catch` yerine oluşturur.  
  
 Kullanmaya karar verirseniz `setjmp` / `longjmp` bir C++ programı SETJMP de içerir. H veya SETJMPEX. C++ özel durum işleme ve işlevleri arasında doğru etkileşim güvence altına almak için H. Kullanırsanız [/EH](../build/reference/eh-exception-handling-model.md) derlemek için yerel nesneleri için Yıkıcılar yığını geriye doğru izleme sırasında denir. Kullanırsanız **/EHs** derleme ve, işlev çağrıları kullanan bir işlev bir biri [nothrow](../cpp/nothrow-cpp.md) ve kullanan bir işlev `nothrow` çağrıları `longjmp`, yıkıcı bırakma gerçekleşmeyebilir sonra İyileştirici bağlı olarak.  
  
 Taşınabilir kodda, yerel olmayan zaman `goto` çağırır `longjmp` yürütüldüğünde, çerçeve tabanlı nesnelerin doğru yok etme güvenilir olabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C (yapılandırılmış) ile C++ özel durumlarını karıştırma](../cpp/mixing-c-structured-and-cpp-exceptions.md)