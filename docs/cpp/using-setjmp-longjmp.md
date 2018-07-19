---
title: Setjmp-longjmp kullanma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- longjmp_cpp
- setjmp_cpp
dev_langs:
- C++
helpviewer_keywords:
- C++ exception handling, setjmp/longjmp functions
- setjmpex.h
- longjmp function in C++ programs
- setjmp.h
- setjmp function
- setjmp function, C++ programs
ms.assetid: 96be8816-f6f4-4567-9a9c-0c3c720e37c5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f68cd13304e73282735ad1227510b289b19caed8
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37939773"
---
# <a name="using-setjmplongjmp"></a>setjmp/longjmp Kullanma
Zaman [setjmp](../c-runtime-library/reference/setjmp.md) ve [longjmp](../c-runtime-library/reference/longjmp.md) olan birlikte kullanıldığında, yerel olmayan yürütmek için bir yol sağlarlar **goto**. Bunlar, genellikle standart çağırma kullanmadan daha önce çağrılmış bir yordam hata işleme veya kurtarma koduna yürütme denetimi geçirmek için kullanılan veya dönüş kuralları.  
  
> [!CAUTION]
>  Ancak, çünkü `setjmp` ve `longjmp` C++ nesnesi semantiğini desteklemediğinden ve yerel değişkenlerde iyileştirmeyi engelleyerek performansı düşebilir olduğundan, bunları C++ programlarında kullanmamanızı öneririz. Kullanmanızı öneririz **deneyin**/**catch** yerine oluşturur.  
  
 Kullanmaya karar verirseniz `setjmp` / `longjmp` bir C++ programında de \<setjmp.h > veya \<setjmpex.h > İşlevler ve C++ özel durum işleme arasında doğru etkileşimi sağlamak için. Kullanırsanız [/EH](../build/reference/eh-exception-handling-model.md) derlemek için yerel nesneleri yok ediciler yığın bırakma sırasında çağrılır. Kullanırsanız **EHS** derleme ve biri, işlev çağrıları kullanan bir işlevi [nothrow](../cpp/nothrow-cpp.md) ve kullanan işlev **nothrow** çağrıları `longjmp`, ardından yok edici, iyileştiriciye bağlı değil.  
  
 Taşınabilir kodda, yerel olmayan **goto** çağrılarının `longjmp` yürütüldüğünde, doğru çerçeve tabanlı nesnelerin yok edilmesini güvensiz olabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C (Yapılandırılmış) ile C++ Özel Durumlarını Karıştırma](../cpp/mixing-c-structured-and-cpp-exceptions.md)