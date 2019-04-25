---
title: Çift arabirimler ve olaylar
ms.date: 11/04/2016
helpviewer_keywords:
- events [C++], dual interfaces
- dual interfaces, events
ms.assetid: bb382f7c-e885-4274-bf07-83f3602615d2
ms.openlocfilehash: 01233edb63145d69d335349bb9dff91e6a4aca5a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62198271"
---
# <a name="dual-interfaces-and-events"></a>Çift arabirimler ve olaylar

Bir çift olarak bir olay arabirimi tasarlamak mümkün olsa da, bunu yapmak için iyi bir tasarım nedenlerden vardır. Temel nedeni olayının kaynağı, yalnızca bir olay veya vtable aracılığıyla ateşlenir `Invoke`, ikisi birden değil. Olay kaynağı olarak doğrudan vtable yöntem çağrısı, olay gösteriliyorsa `IDispatch` yöntemleri hiçbir zaman kullanılacak ve saf vtable arabirimi arabirimi olmalıydı işaretlenmemiştir. Olay kaynağı için bir çağrı olarak olayı tetikler, `Invoke`vtable yöntemleri hiçbir zaman kullanılmayacaktır ve bu açık arabirim bir dispinterface verilmiş olması. Olay arabirimlerinizi duals tanımlarsanız, hiçbir zaman kullanılacak olan arabirimin bir parçası uygulamak istemcileri gerektiren.

> [!NOTE]
>  Bu bağımsız değişken ikili arabirimler için genel olarak geçerli değildir. Bir uygulama açısından bakıldığında, çok çeşitli istemciler için erişilebilir olan arabirimler uygulama hızlı, güvenli ve iyi desteklenen bir yöntemle duals var.

Daha fazla çift olay arabirimlerden kaçının nedenleri vardır; Visual Basic ya da Internet Explorer bunları destekler.

## <a name="see-also"></a>Ayrıca bkz.

[Çift Arabirimler ve ATL](../atl/dual-interfaces-and-atl.md)
