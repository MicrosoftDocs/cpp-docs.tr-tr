---
title: Çift arabirimler ve olaylar | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- events [C++], dual interfaces
- dual interfaces, events
ms.assetid: bb382f7c-e885-4274-bf07-83f3602615d2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a482486be66811954602849c4bdde5b8955c887f
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43763220"
---
# <a name="dual-interfaces-and-events"></a>Çift arabirimler ve olaylar

Bir çift olarak bir olay arabirimi tasarlamak mümkün olsa da, bunu yapmak için iyi bir tasarım nedenlerden vardır. Temel nedeni olayının kaynağı, yalnızca bir olay veya vtable aracılığıyla ateşlenir `Invoke`, ikisi birden değil. Olay kaynağı olarak doğrudan vtable yöntem çağrısı, olay gösteriliyorsa `IDispatch` yöntemleri hiçbir zaman kullanılacak ve saf vtable arabirimi arabirimi olmalıydı işaretlenmemiştir. Olay kaynağı için bir çağrı olarak olayı tetikler, `Invoke`vtable yöntemleri hiçbir zaman kullanılmayacaktır ve bu açık arabirim bir dispinterface verilmiş olması. Olay arabirimlerinizi duals tanımlarsanız, hiçbir zaman kullanılacak olan arabirimin bir parçası uygulamak istemcileri gerektiren.

> [!NOTE]
>  Bu bağımsız değişken ikili arabirimler için genel olarak geçerli değildir. Bir uygulama açısından bakıldığında, çok çeşitli istemciler için erişilebilir olan arabirimler uygulama hızlı, güvenli ve iyi desteklenen bir yöntemle duals var.

Daha fazla çift olay arabirimlerden kaçının nedenleri vardır; Visual Basic ya da Internet Explorer bunları destekler.

## <a name="see-also"></a>Ayrıca Bkz.

[Çift Arabirimler ve ATL](../atl/dual-interfaces-and-atl.md)

