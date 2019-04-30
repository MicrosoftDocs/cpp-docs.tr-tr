---
title: C (yapılandırılmış) ile C++ özel durumlarını karıştırma
ms.date: 08/14/2018
helpviewer_keywords:
- exceptions [C++], mixed C and C++
- C++ exception handling, mixed-language
- structured exception handling [C++], mixed C and C++
- catch keyword [C++], mixed
- try-catch keyword [C++], mixed-language
ms.assetid: a149154e-36dd-4d1a-980b-efde2a563a56
ms.openlocfilehash: 94d6dc249cb130aaf09d3202b9e8f437d00a9597
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64345963"
---
# <a name="mixing-c-structured-and-c-exceptions"></a>C (yapılandırılmış) ile C++ özel durumlarını karıştırma

Taşınabilir kod yazmak istiyorsanız, yapılandırılmış özel durum (SEH) C++ programında işleme kullanımı önerilmez. Ancak, bazen kullanarak derleme isteyebileceğiniz [/eha](../build/reference/eh-exception-handling-model.md) yapılandırılmış özel durumları ve C++ kaynak kodunu karışımı ve her iki tür özel durumları işlemek için bazı özellik gerekir. Yapılandırılmış özel durum işleyicisi nesneleri veya belirlenmiş özel durumlar kavramı olduğundan, C++ kodu tarafından oluşturulan özel durumları işleyemez. Bununla birlikte, C++ **catch** işleyicileri, yapılandırılmış özel durumları işleyebilir. C++özel durum işleme sözdizimini (**deneyin**, **throw**, **catch**) C derleyicisi ancak yapılandırılmış özel durum işleme sözdizimini tarafından kabul (**__try**, **__except**, **__finally**) tarafından desteklenen C++ derleyici.

Bkz: [_set_se_translator](../c-runtime-library/reference/set-se-translator.md) olarak yapılandırılmış özel durumları işleme hakkında bilgi için C++ özel durumlar.

Yapılandırılmış karışımı varsa ve C++ özel durumlarını, bu olası sorunlarından haberdar olmalı:

- C++ özel durumlarını ve yapılandırılmış özel durumları aynı işlevin içinde karıştırılamaz.

- Sonlandırma işleyicileri (**__finally** blokları) her zaman, bir özel durum oluştuktan sonra bile geriye doğru izleme sırasında yürütülür.

- C++ özel durum işleme yakalayabilir ve koruma geriye doğru izleme semantiği ile derlenmiş tüm modüllerin [/EH](../build/reference/eh-exception-handling-model.md) derleyici seçenekleri, geriye doğru izleme semantiği hangi etkinleştir.

- Hangi yıkıcı işlevleri tüm nesneleri için çağrılmaz bazı durumlar olabilir. Örneğin, işlev bir başlatılmamış işlev işaretçisi çağrısı yapmaya çalışırken bir yapılandırılmış özel durum oluşursa ve bu işlev çağrısından önce oluşturulmuş parametreleri nesneleri alır söz konusu nesnelerin yok ediciler çağrılır değil yığın bırakma sırasında.

## <a name="next-steps"></a>Sonraki adımlar

- [C++ programlarında setjmp veya longjmp kullanma](../cpp/using-setjmp-longjmp.md)

  Kullanımı hakkında daha fazla bilgi `setjmp` ve `longjmp` C++ programlarında.

- [C++ dilinde yapılandırılmış özel durumları işleme](../cpp/exception-handling-differences.md)

  C++ için tanıtıcı yapısal özel durumlar kullanma yollarına örneklere bakın.

## <a name="see-also"></a>Ayrıca bkz.

[C++ Özel Durum İşleme](../cpp/cpp-exception-handling.md)
