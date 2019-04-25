---
title: Sonlandırma İşleyicisi Yazma
ms.date: 11/04/2016
helpviewer_keywords:
- structured exception handling [C++], termination handlers
- exceptions [C++], terminating
- termination handlers [C++], writing
- handlers [C++]
- handlers [C++], termination
- termination handlers
- exception handling [C++], termination handlers
- try-catch keyword [C++], termination handlers
ms.assetid: 52aa1f8f-f8dd-44b8-be94-5e2fc88d44fb
ms.openlocfilehash: f0b994075a8d59ce5d0955f10bf8c61d357d2db9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62209474"
---
# <a name="writing-a-termination-handler"></a>Sonlandırma İşleyicisi Yazma

Bir özel durum işleyicisinin tersine, bir sonlandırma işleyicisi korunan kod bloğunun normal bir şekilde sonlandırılıp sonlandırılmadığına bakılmaksızın her zaman yürütülür. Sonlandırma işleyicisinin temel amacı bellek, tanıtıcılar ve dosyalar gibi kaynakları bir kod bölümünün yürütülmesinin nasıl sona erdiğine bakılmaksızın uygun bir şekilde kapatmaktır.

Sonlandırma işleyicileri, try-finally deyimini kullanır.

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

- [Try-finally deyimi](../cpp/try-finally-statement.md)

- [Kaynakları temizleme](../cpp/cleaning-up-resources.md)

- [Özel Durum İşlemede eylemlerin zamanlaması](../cpp/timing-of-exception-handling-a-summary.md)

- [Sonlandırma işleyicileri kısıtlamaları](../cpp/restrictions-on-termination-handlers.md)

## <a name="see-also"></a>Ayrıca bkz.

[Yapılandırılmış Özel Durum İşleme (C/C++)](../cpp/structured-exception-handling-c-cpp.md)