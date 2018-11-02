---
title: Setjmp ve longjmp kullanma
ms.date: 08/14/2018
f1_keywords:
- longjmp_cpp
- setjmp_cpp
helpviewer_keywords:
- C++ exception handling, setjmp/longjmp functions
- setjmpex.h
- longjmp function in C++ programs
- setjmp.h
- setjmp function
- setjmp function, C++ programs
ms.assetid: 96be8816-f6f4-4567-9a9c-0c3c720e37c5
ms.openlocfilehash: 4ead12f79701899b3977993c9de3c3803023150f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50525725"
---
# <a name="using-setjmp-and-longjmp"></a>Setjmp ve longjmp kullanma

Zaman [setjmp](../c-runtime-library/reference/setjmp.md) ve [longjmp](../c-runtime-library/reference/longjmp.md) olan birlikte kullanıldığında, yerel olmayan yürütmek için bir yol sağlarlar **goto**. Bunlar, genellikle standart çağırma kullanmadan daha önce çağrılmış bir yordam hata işleme veya kurtarma koduna yürütme denetimi geçirmek için C kodunda kullanılan veya dönüş kuralları.

> [!CAUTION]
> Çünkü `setjmp` ve `longjmp` yığın çerçevesi nesneleri C++ Derleyicileri temelinizi arasında doğru yok edilmesini desteklemez ve yerel değişkenlerde iyileştirmeyi engelleyerek performansı düşebilir olduğundan, C++, bunların kullanılması önerilmemektedir programları. Kullanmanızı öneririz **deneyin** ve **catch** yerine oluşturur.

Kullanmaya karar verirseniz `setjmp` ve `longjmp` bir C++ programında de \<setjmp.h > veya \<setjmpex.h > yapılandırılmış özel durum işleme (SEH) ya da C++ özel durum ve işlevler arasında doğru etkileşimi sağlamak için işleme.

**Microsoft'a özgü**

Kullanıyorsanız bir [/EH](../build/reference/eh-exception-handling-model.md) C++ kodu derlemek için seçeneğinde, yerel nesneleri yok ediciler yığın bırakma sırasında çağrılır. Ancak, kullanırsanız **EHS** veya **/ehsc** derleme ve işlevlerinizi kullanan bir [noexcept](../cpp/noexcept-cpp.md) çağrıları `longjmp`, yok edici bırakma sonra bu işlev için , iyileştirici durumuna bağlı olarak gerçekleşmeyebilir.

Taşınabilir kodda olduğunda bir `longjmp` çağrı yürütüldüğünde, doğru çerçeve tabanlı nesnelerin yok edilmesini standardına göre garanti açıkça ve diğer derleyiciler tarafından desteklenmiyor olabilir. Bildiren, 4, uyarı düzeyinde bir çağrı `setjmp` uyarı C4611 neden: '_setjmp' ile C++ nesne yok etme arasındaki etkileşim taşınabilir.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[C (Yapılandırılmış) ile C++ Özel Durumlarını Karıştırma](../cpp/mixing-c-structured-and-cpp-exceptions.md)
