---
description: 'Daha fazla bilgi edinin: çift arabirimler ve olaylar'
title: Çift arabirimler ve olaylar
ms.date: 11/04/2016
helpviewer_keywords:
- events [C++], dual interfaces
- dual interfaces, events
ms.assetid: bb382f7c-e885-4274-bf07-83f3602615d2
ms.openlocfilehash: 231df7a0dfc8376acd6a9a0f9d85d0ed68fdd0b9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97153033"
---
# <a name="dual-interfaces-and-events"></a>Çift arabirimler ve olaylar

Bir olay arabirimini çift olarak tasarlamak mümkün olsa da, bunu yapamayan bazı iyi tasarım nedenleri vardır. Temel neden, olayın kaynağının yalnızca vtable veya aracılığıyla olayı tetiklemesi, `Invoke` her ikisiyle değil. Olay kaynağı olayı doğrudan bir vtable Yöntem çağrısı olarak `IDispatch` tetiklediğinde, Yöntemler asla kullanılmaz ve arabirimin saf bir vtable arabirimi olması gerekir. Olay kaynağı olayı öğesine çağrı olarak `Invoke` tetiklediğinde, vtable yöntemleri asla kullanılmaz ve arabirimin bir dispınterface olması gerekir. Olay arabirimlerinizi duals olarak tanımlarsanız, istemcilerin hiçbir daha kullanılamayacak bir arabirimin parçasını uygulamasını zorunlu kılcaksınız.

> [!NOTE]
> Bu bağımsız değişken, genel olarak çift arabirimler için geçerlidir. Uygulama açısından, duals, çok sayıda istemci tarafından erişilebilen arabirimleri uygulamanın hızlı, kolay ve iyi desteklenen bir yoludur.

İkili olay arabirimlerinden kaçınmanın başka nedenleri vardır; Ne Visual Basic ne de Internet Explorer bunları desteklemez.

## <a name="see-also"></a>Ayrıca bkz.

[Çift arabirimler ve ATL](../atl/dual-interfaces-and-atl.md)
