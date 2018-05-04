---
title: Çift arabirimler ve olayları | Microsoft Docs
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
ms.openlocfilehash: 99dc173f3dde8ea81f6dc11d02298cd94673f999
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="dual-interfaces-and-events"></a>Çift arabirimler ve olaylar
Bir olay arabirimi bir çift olarak tasarlamanız mümkün olsa da, pek çok Bunu yapmak için iyi tasarım vardır. Temel nedeni olay kaynağı olay vtable aracılığıyla veya aracılığıyla yalnızca ateşlenir `Invoke`, ikisi birden değil. Olay kaynağı olarak doğrudan vtable yöntem çağrısı, olay gönderir, `IDispatch` yöntemleri hiçbir zaman kullanılacak ve arabirim saf vtable arabirimi olması gereken işaretlenmemiştir. Olay kaynağı için bir çağrı olarak olay gönderir, `Invoke`vtable yöntemleri hiç kullanılmadı ve bu Temizle arabirimi bir görüntüleme arabirimi verilmiş olması. Olay arabirimlerinizi duals tanımlarsanız, hiçbir zaman kullanılacak bir arabirim parçası uygulamak istemcileri gerektiren.  
  
> [!NOTE]
>  Bu bağımsız değişken çift arabirimler için genel olarak uygulanmaz. Bir uygulama açısından duals çeşitli istemciler için erişilebilir arabirimler uygulama, bir hızlı, kolay ve iyi desteklenen yoludur.  
  
 Daha fazla çift olay arabirimleri önlemek için nedenleri vardır; Visual Basic ya da Internet Explorer bunları destekler.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çift Arabirimler ve ATL](../atl/dual-interfaces-and-atl.md)

