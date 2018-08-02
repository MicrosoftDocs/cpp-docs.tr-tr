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
ms.openlocfilehash: 2073729fc5445fc36e3d8a6f52c4f69b079c8b47
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39462137"
---
# <a name="using-setjmplongjmp"></a>setjmp/longjmp Kullanma
Zaman [setjmp](../c-runtime-library/reference/setjmp.md) ve [longjmp](../c-runtime-library/reference/longjmp.md) olan birlikte kullanıldığında, yerel olmayan yürütmek için bir yol sağlarlar **goto**. Bunlar, genellikle standart çağırma kullanmadan daha önce çağrılmış bir yordam hata işleme veya kurtarma koduna yürütme denetimi geçirmek için kullanılan veya dönüş kuralları.  
  
> [!CAUTION]
>  Ancak, çünkü **setjmp** ve **longjmp** C++ nesnesi semantiğini desteklemediğinden ve yerel değişkenlerde iyileştirmeyi engelleyerek performansı düşebilir gerektiğinden, kullanmanızı öneririz bunları C++ programlarında. Kullanmanızı öneririz **deneyin**/**catch** yerine oluşturur.  
  
 Kullanmaya karar verirseniz **setjmp**/**longjmp** bir C++ programında de \<setjmp.h > veya \<setjmpex.h > arasında doğru etkileşimi sağlamak için İşlevler ve C++ özel durum işleme. Kullanırsanız [/EH](../build/reference/eh-exception-handling-model.md) derlemek için yerel nesneleri yok ediciler yığın bırakma sırasında çağrılır. Kullanırsanız **EHS** derleme ve biri, işlev çağrıları kullanan bir işlevi [nothrow](../cpp/nothrow-cpp.md) ve kullanan işlev **nothrow** çağrıları **longjmp**, sonra da yok edici, iyileştiriciye bağlı değil.  
  
 Taşınabilir kodda, yerel olmayan **goto** çağrılarının **longjmp** yürütüldüğünde, doğru çerçeve tabanlı nesnelerin yok edilmesini güvensiz olabilir.  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [C (Yapılandırılmış) ile C++ Özel Durumlarını Karıştırma](../cpp/mixing-c-structured-and-cpp-exceptions.md)