---
description: 'Hakkında daha fazla bilgi edinin: setjmp ve longjmp kullanma'
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
ms.openlocfilehash: 5d0f62eeed8b2401309f339a59872c7dd0ac3107
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97116749"
---
# <a name="using-setjmp-and-longjmp"></a>Setjmp ve longjmp kullanma

[Setjmp](../c-runtime-library/reference/setjmp.md) ve [longjmp](../c-runtime-library/reference/longjmp.md) birlikte kullanıldığında, yerel olmayan bir yürütmek için bir yol sağlar **`goto`** . Bunlar genellikle, Standart çağırma veya döndürme kurallarını kullanmadan daha önce çağrılan bir yordamın hata işleme veya kurtarma koduna yürütme denetimini geçirmek için C kodunda kullanılır.

> [!CAUTION]
> `setjmp` `longjmp` Ayrıca, c++ derleyicileri arasında yığın çerçeve nesnelerinin düzgün bir şekilde yok edilmesiyle ve yerel değişkenlerde iyileştirmeyi önleyerek performansı düşürebileceğinden, c++ programlarında kullanımını önermiyoruz. **`try`** **`catch`** Bunun yerine ve yapılarını kullanmanızı öneririz.

`setjmp`Bir C++ programında ve ' ı kullanmaya karar verirseniz `longjmp` , \<setjmp.h> \<setjmpex.h> Işlevler ve yapılandırılmış özel durum işleme (SEH) veya C++ özel durum işleme arasında doğru etkileşimi güvence altına almak için ya da dahil edin.

**Microsoft'a Özgü**

C++ kodunu derlemek için bir [/Eh](../build/reference/eh-exception-handling-model.md) seçeneği kullanırsanız, yerel nesneler için yok ediciler yığın geriye doğru çağrılır. Ancak, derlemek için **/EHS** veya **/EHsc** kullanırsanız ve [noexcept](../cpp/noexcept-cpp.md) çağrıları kullanan işlevleriniz varsa `longjmp` , bu işlev için yıkıcının açılımı, iyileştirici durumuna bağlı olarak gerçekleşmeyebilir.

Taşınabilir kodda, bir `longjmp` çağrı yürütüldüğünde, çerçeve tabanlı nesnelerin doğru olarak yok edilmesi standart tarafından garanti edilmez ve diğer derleyiciler tarafından desteklenmeyebilir. Uyarı düzeyi 4 ' te bir çağrı, uyarı `setjmp` C4611: ' _Setjmp ' Ile C++ nesne yok etme arasındaki etkileşim taşınabilir değildir.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[C (yapılandırılmış) ve C++ özel durumlarını karıştırma](../cpp/mixing-c-structured-and-cpp-exceptions.md)
