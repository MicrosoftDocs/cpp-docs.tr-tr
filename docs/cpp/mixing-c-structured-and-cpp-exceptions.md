---
title: C (yapılandırılmış) ve C++ özel durumları karıştırma
ms.date: 08/14/2018
helpviewer_keywords:
- exceptions [C++], mixed C and C++
- C++ exception handling, mixed-language
- structured exception handling [C++], mixed C and C++
- catch keyword [C++], mixed
- try-catch keyword [C++], mixed-language
ms.assetid: a149154e-36dd-4d1a-980b-efde2a563a56
ms.openlocfilehash: e49731f1c81057002eaae2bef16cda4a5cf86f8d
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2019
ms.locfileid: "74246456"
---
# <a name="mixing-c-structured-and-c-exceptions"></a>C (yapılandırılmış) ve C++ özel durumları karıştırma

Taşınabilir kod yazmak isterseniz, bir C++ programda yapılandırılmış özel durum Işleme (SEH) kullanılması önerilmez. Ancak, bazen [/EHa](../build/reference/eh-exception-handling-model.md) kullanarak derlemek ve yapılandırılmış özel durumları ve C++ kaynak kodu karıştırmak ve her iki özel durum türünü işlemek için bazı tesislerin olması gerekebilir. Yapılandırılmış bir özel durum işleyicisinin nesne kavramı olmadığından veya türü belirlenmiş özel durumlar olmadığından, kod tarafından C++ oluşturulan özel durumları işleyemez. Ancak, C++ **catch** işleyicileri yapılandırılmış özel durumları işleyebilir. C++özel durum işleme sözdizimi **(TRY**, **throw**, **catch**) C derleyicisi tarafından kabul edilmez, ancak yapılandırılmış özel durum işleme sözdizimi ( **__try**, **__except**, **__finally**) C++ derleyici tarafından desteklenir.

Yapılandırılmış [](../c-runtime-library/reference/set-se-translator.md) özel durumları özel durum olarak C++ işleme hakkında bilgi için bkz. _set_se_translator.

Yapılandırılmış ve C++ özel durumları karıştırırsanız, bu olası sorunları göz önünde bulundurun:

- C++özel durumlar ve yapılandırılmış özel durumlar aynı işlev içinde karıştırılamaz.

- Sonlandırma işleyicileri ( **__finally** blokları), bir özel durum oluşturulduktan sonra geri sarma sırasında bile her zaman yürütülür.

- C++özel durum işleme, geriye doğru izleme semantiği sağlayan [/Eh](../build/reference/eh-exception-handling-model.md) derleyici seçenekleriyle derlenen tüm modüllerde geri alma semantiğini yakalayabilir ve koruyabilir.

- Yok edicisi işlevlerinin tüm nesneler için çağrılmadığı bazı durumlar olabilir. Örneğin, başlatılmamış bir işlev işaretçisi aracılığıyla işlev çağrısı yapmaya çalışırken yapılandırılmış bir özel durum oluşursa ve bu işlev, çağrıdan önce oluşturulmuş parametre nesneleri olarak alırsa, bu nesnelerin yıkıcıları çağrılmaz yığın geriye doğru izleme sırasında.

## <a name="next-steps"></a>Sonraki adımlar

- [C++ Programlarda setjmp veya longjmp kullanma](../cpp/using-setjmp-longjmp.md)

  C++ Programlar `setjmp` ve `longjmp` kullanımı hakkında daha fazla bilgi için bkz.

- [C++ dilinde yapılandırılmış özel durumları işleme](../cpp/exception-handling-differences.md)

  Yapılandırılmış özel durumları işlemek için kullanabileceğiniz C++ yöntemlere yönelik örneklere bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Özel C++ durumlar ve hata işleme için modern en iyi uygulamalar](../cpp/errors-and-exception-handling-modern-cpp.md)
