---
title: Çift Arayüzler ve Etkinlikler
ms.date: 11/04/2016
helpviewer_keywords:
- events [C++], dual interfaces
- dual interfaces, events
ms.assetid: bb382f7c-e885-4274-bf07-83f3602615d2
ms.openlocfilehash: 4ce5048c25bd55feb0f1eb20fc04ec6bfeead746
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319614"
---
# <a name="dual-interfaces-and-events"></a>Çift Arayüzler ve Etkinlikler

Bir olay arabirimini ikili olarak tasarlamak mümkün olsa da, bunu yapmamak için bir dizi iyi tasarım nedeni vardır. Temel nedeni, olayın kaynağı sadece vtable veya üzerinden `Invoke`olay ateş olacak , her ikisi de değil. Olay kaynağı olayı doğrudan vtable yöntemi çağrısı olarak `IDispatch` çalıştırıyorsa, yöntemler asla kullanılmaz ve arabirimin saf bir vtable arabirimi olması gerektiği açıktır. Olay kaynağı olayı bir çağrı olarak `Invoke`çalıştırıyorsa, vtable yöntemleri asla kullanılmaz ve arabirimin bir dispinterface olması gerektiği açıktır. Olay arabirimlerinizi çift olarak tanımlarsanız, istemcilerin asla kullanılmayacak bir arabirimin bir bölümünü uygulamalarını gerekir.

> [!NOTE]
> Bu bağımsız değişken, genel olarak çift arabirimler için geçerli değildir. Uygulama açısından bakıldığında, ikililer çok çeşitli istemciler tarafından erişilebilen arabirimleri hızlı, kullanışlı ve iyi desteklenen bir yoldur.

Çift olay arabirimlerinden kaçınmak için başka nedenler de vardır; ne Visual Basic ne de Internet Explorer bunları desteklemez.

## <a name="see-also"></a>Ayrıca bkz.

[Çift Arayüzler ve ATL](../atl/dual-interfaces-and-atl.md)
