---
title: C (yapılandırılmış) ve C++ özel durumlarını karıştırma
description: Yapılandırılmış özel durum işleme ve C++ özel durumlarını ve bazı olası sorunları karıştırma.
ms.date: 08/24/2020
helpviewer_keywords:
- exceptions [C++], mixed C and C++
- C++ exception handling, mixed-language
- structured exception handling [C++], mixed C and C++
- catch keyword [C++], mixed
- try-catch keyword [C++], mixed-language
ms.assetid: a149154e-36dd-4d1a-980b-efde2a563a56
ms.openlocfilehash: 98ce2335ff3b08b7a5d71e03305c481ba068e5e6
ms.sourcegitcommit: efc8c32205c9d610f40597556273a64306dec15d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/26/2020
ms.locfileid: "88898414"
---
# <a name="mixing-c-structured-and-c-exceptions"></a>C (yapılandırılmış) ve C++ özel durumlarını karıştırma

Taşınabilir kod yazmak isterseniz, yapılandırılmış özel durum işleme (SEH) bir C++ programında kullanılması önerilmez. Ancak, bazen [`/EHa`](../build/reference/eh-exception-handling-model.md) yapılandırılmış özel durumları ve C++ kaynak kodunu kullanarak derleyip karıştırarak, her iki özel durum türünü de işlemek için bazı olanaklara ihtiyacınız olabilir. Yapılandırılmış bir özel durum işleyicisinin nesne kavramı olmadığından veya türü belirlenmiş özel durumlar olmadığından, C++ kodu tarafından oluşturulan özel durumları işleyemez. Ancak, C++ **`catch`** işleyicileri yapılandırılmış özel durumları işleyebilir. C++ özel durum işleme sözdizimi ( **`try`** , **`throw`** , **`catch`** ) C derleyicisi tarafından kabul edilmez, ancak yapılandırılmış özel durum işleme sözdizimi ( **`__try`** , **`__except`** , **`__finally`** ) C++ derleyicisi tarafından desteklenir.

[`_set_se_translator`](../c-runtime-library/reference/set-se-translator.md)Yapılandırılmış özel durumları C++ özel durumları olarak işleme hakkında bilgi için bkz..

Yapılandırılmış ve C++ özel durumlarını karıştırırsanız, bu olası sorunları göz önünde bulundurun:

- C++ özel durumları ve yapılandırılmış özel durumlar aynı işlev içinde karıştırılamaz.

- Sonlandırma işleyicileri ( **`__finally`** bloklar), bir özel durum oluşturulduktan sonra geri sarma sırasında bile her zaman yürütülür.

- C++ özel durum işleme, derleme seçenekleriyle derlenen tüm modüllerde geriye doğru izleme semantiği sağlayan geri alma semantiğini yakalayabilir ve koruyabilir [`/EH`](../build/reference/eh-exception-handling-model.md) .

- Yok edicisi işlevlerinin tüm nesneler için çağrılmadığı bazı durumlar olabilir. Örneğin, başlatılmamış bir işlev işaretçisi aracılığıyla işlev çağrısı yapılmaya çalışılırken yapılandırılmış bir özel durum oluşabilir. İşlev parametreleri çağrıdan önce oluşturulmuş nesnelerdir, bu nesnelerin yıkıcıları yığın geriye doğru çağrılmaz.

## <a name="next-steps"></a>Sonraki adımlar

- [`setjmp` `longjmp` C++ programlarında veya kullanma](../cpp/using-setjmp-longjmp.md)

  C++ programlarının kullanımı hakkında daha fazla bilgi için bkz `setjmp` `longjmp` ..

- [C++ dilinde yapılandırılmış özel durumları işleme](../cpp/exception-handling-differences.md)

  Yapılandırılmış özel durumları işlemek için C++ kullanma yöntemlerinin örneklerine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Özel durumlar ve hata işleme için modern C++ en iyi uygulamaları](../cpp/errors-and-exception-handling-modern-cpp.md)
