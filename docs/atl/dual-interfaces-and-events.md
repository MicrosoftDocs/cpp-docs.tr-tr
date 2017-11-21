---
title: "Çift arabirimler ve olayları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- events [C++], dual interfaces
- dual interfaces, events
ms.assetid: bb382f7c-e885-4274-bf07-83f3602615d2
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d18124646f4d4fcb02246234bf74b5870246e7e4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="dual-interfaces-and-events"></a>Çift arabirimler ve olaylar
Bir olay arabirimi bir çift olarak tasarlamanız mümkün olsa da, pek çok Bunu yapmak için iyi tasarım vardır. Temel nedeni olay kaynağı olay vtable aracılığıyla veya aracılığıyla yalnızca ateşlenir `Invoke`, ikisi birden değil. Olay kaynağı olarak doğrudan vtable yöntem çağrısı, olay gönderir, `IDispatch` yöntemleri hiçbir zaman kullanılacak ve arabirim saf vtable arabirimi olması gereken işaretlenmemiştir. Olay kaynağı için bir çağrı olarak olay gönderir, `Invoke`vtable yöntemleri hiç kullanılmadı ve bu Temizle arabirimi bir görüntüleme arabirimi verilmiş olması. Olay arabirimlerinizi duals tanımlarsanız, hiçbir zaman kullanılacak bir arabirim parçası uygulamak istemcileri gerektiren.  
  
> [!NOTE]
>  Bu bağımsız değişken çift arabirimler için genel olarak uygulanmaz. Bir uygulama açısından duals çeşitli istemciler için erişilebilir arabirimler uygulama, bir hızlı, kolay ve iyi desteklenen yoludur.  
  
 Daha fazla çift olay arabirimleri önlemek için nedenleri vardır; Visual Basic ya da Internet Explorer bunları destekler.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çift arabirimler ve ATL](../atl/dual-interfaces-and-atl.md)

