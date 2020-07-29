---
title: C (yapılandırılmış) ve C++ özel durumlarını karıştırma
ms.date: 08/14/2018
helpviewer_keywords:
- exceptions [C++], mixed C and C++
- C++ exception handling, mixed-language
- structured exception handling [C++], mixed C and C++
- catch keyword [C++], mixed
- try-catch keyword [C++], mixed-language
ms.assetid: a149154e-36dd-4d1a-980b-efde2a563a56
ms.openlocfilehash: 72ddde9bc284a005c77694d599a8e9a3908cb2d0
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233697"
---
# <a name="mixing-c-structured-and-c-exceptions"></a>C (yapılandırılmış) ve C++ özel durumlarını karıştırma

Taşınabilir kod yazmak isterseniz, yapılandırılmış özel durum işleme (SEH) bir C++ programında kullanılması önerilmez. Ancak, bazen [/EHa](../build/reference/eh-exception-handling-model.md) kullanarak derlemek ve yapılandırılmış özel durumları ve C++ kaynak kodunu karıştırmak ve her iki özel durum türünü işlemek için bazı tesislerin olması gerekebilir. Yapılandırılmış bir özel durum işleyicisinin nesne kavramı olmadığından veya türü belirlenmiş özel durumlar olmadığından, C++ kodu tarafından oluşturulan özel durumları işleyemez. Ancak, C++ **`catch`** işleyicileri yapılandırılmış özel durumları işleyebilir. C++ özel durum işleme sözdizimi ( **`try`** , **`throw`** , **`catch`** ) C derleyicisi tarafından kabul edilmez, ancak yapılandırılmış özel durum işleme sözdizimi (**__try**, **`__except`** **`__finally`** ) c++ derleyicisi tarafından desteklenir.

Yapılandırılmış özel durumları C++ özel durumları olarak işleme hakkında bilgi için bkz. [_set_se_translator](../c-runtime-library/reference/set-se-translator.md) .

Yapılandırılmış ve C++ özel durumlarını karıştırırsanız, bu olası sorunları göz önünde bulundurun:

- C++ özel durumları ve yapılandırılmış özel durumlar aynı işlev içinde karıştırılamaz.

- Sonlandırma işleyicileri ( **`__finally`** bloklar), bir özel durum oluşturulduktan sonra geri sarma sırasında bile her zaman yürütülür.

- C++ özel durum işleme, geriye doğru izleme semantiği sağlayan [/Eh](../build/reference/eh-exception-handling-model.md) derleyici seçenekleriyle derlenen tüm modüllerde geri alma semantiğini yakalayabilir ve koruyabilir.

- Yok edicisi işlevlerinin tüm nesneler için çağrılmadığı bazı durumlar olabilir. Örneğin, başlatılmamış bir işlev işaretçisi aracılığıyla işlev çağrısı yapmaya çalışırken yapılandırılmış bir özel durum oluşursa ve bu işlev, çağrıdan önce oluşturulmuş parametre nesneleri olarak alırsa, bu nesnelerin yıkıcıları yığın geriye doğru çağırılmaz.

## <a name="next-steps"></a>Sonraki adımlar

- [C++ programlarında setjmp veya longjmp kullanma](../cpp/using-setjmp-longjmp.md)

  C++ programlarının kullanımı hakkında daha fazla bilgi için bkz `setjmp` `longjmp` ..

- [C++ dilinde yapılandırılmış özel durumları işleme](../cpp/exception-handling-differences.md)

  Yapılandırılmış özel durumları işlemek için C++ kullanma yöntemlerinin örneklerine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Özel durumlar ve hata işleme için modern C++ en iyi uygulamaları](../cpp/errors-and-exception-handling-modern-cpp.md)
