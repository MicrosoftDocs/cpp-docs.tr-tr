---
title: Sonlandırma işleyicisi yazma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 85241d9dde87e929b02328a6e7d0c75b5ce068ef
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46116236"
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