---
title: "nonextensible özniteliği | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: nonextensible
dev_langs: C++
helpviewer_keywords:
- nonextensible attribute
- dual interfaces, nonextensible attribute
ms.assetid: 02a4a18b-ffd3-4d53-8fd1-feb1c05ad5ac
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: af16748bb3b2048ce854ccc7a03b2400039184a6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="nonextensible-attribute"></a>nonextensible özniteliği
Çift arabirim çalışma zamanında uzatılır değil, (diğer bir deyişle, yöntemleri veya özellikleri aracılığıyla sağlamayacak **IDispatch::Invoke** vtable kullanılabilir olmayan), uygulamanız gerekir **nonextensible** Arabirim tanımınızı öznitelik. Bu öznitelik derleme zamanında tam kod doğrulamayı etkinleştirmek için kullanılan istemci dillerini (Visual Basic gibi) bilgileri sağlar. Bu öznitelik sağlanmazsa, hataların çalışma zamanına kadar istemci kodu gizli kalabilir.  
  
 Daha fazla bilgi için **nonextensible** özniteliğini ve bir örnek görmek, [nonextensible](../windows/nonextensible.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çift Arabirimler ve ATL](../atl/dual-interfaces-and-atl.md)

