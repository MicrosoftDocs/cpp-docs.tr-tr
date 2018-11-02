---
title: Çift arabirimler ve olaylar
ms.date: 11/04/2016
helpviewer_keywords:
- events [C++], dual interfaces
- dual interfaces, events
ms.assetid: bb382f7c-e885-4274-bf07-83f3602615d2
ms.openlocfilehash: f94e87f077846af8d61b06145f776f385051e79f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50640602"
---
# <a name="dual-interfaces-and-events"></a>Çift arabirimler ve olaylar

Bir çift olarak bir olay arabirimi tasarlamak mümkün olsa da, bunu yapmak için iyi bir tasarım nedenlerden vardır. Temel nedeni olayının kaynağı, yalnızca bir olay veya vtable aracılığıyla ateşlenir `Invoke`, ikisi birden değil. Olay kaynağı olarak doğrudan vtable yöntem çağrısı, olay gösteriliyorsa `IDispatch` yöntemleri hiçbir zaman kullanılacak ve saf vtable arabirimi arabirimi olmalıydı işaretlenmemiştir. Olay kaynağı için bir çağrı olarak olayı tetikler, `Invoke`vtable yöntemleri hiçbir zaman kullanılmayacaktır ve bu açık arabirim bir dispinterface verilmiş olması. Olay arabirimlerinizi duals tanımlarsanız, hiçbir zaman kullanılacak olan arabirimin bir parçası uygulamak istemcileri gerektiren.

> [!NOTE]
>  Bu bağımsız değişken ikili arabirimler için genel olarak geçerli değildir. Bir uygulama açısından bakıldığında, çok çeşitli istemciler için erişilebilir olan arabirimler uygulama hızlı, güvenli ve iyi desteklenen bir yöntemle duals var.

Daha fazla çift olay arabirimlerden kaçının nedenleri vardır; Visual Basic ya da Internet Explorer bunları destekler.

## <a name="see-also"></a>Ayrıca Bkz.

[Çift Arabirimler ve ATL](../atl/dual-interfaces-and-atl.md)

