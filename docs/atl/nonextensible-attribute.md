---
title: nonextensible özniteliği | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- nonextensible
dev_langs:
- C++
helpviewer_keywords:
- nonextensible attribute
- dual interfaces, nonextensible attribute
ms.assetid: 02a4a18b-ffd3-4d53-8fd1-feb1c05ad5ac
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 40b4b79701862ca07e704aca098419479923ef1a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="nonextensible-attribute"></a>nonextensible özniteliği
Çift arabirim çalışma zamanında uzatılır değil, (diğer bir deyişle, yöntemleri veya özellikleri aracılığıyla sağlamayacak **IDispatch::Invoke** vtable kullanılabilir olmayan), uygulamanız gerekir **nonextensible** Arabirim tanımınızı öznitelik. Bu öznitelik derleme zamanında tam kod doğrulamayı etkinleştirmek için kullanılan istemci dillerini (Visual Basic gibi) bilgileri sağlar. Bu öznitelik sağlanmazsa, hataların çalışma zamanına kadar istemci kodu gizli kalabilir.  
  
 Daha fazla bilgi için **nonextensible** özniteliğini ve bir örnek görmek, [nonextensible](../windows/nonextensible.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çift Arabirimler ve ATL](../atl/dual-interfaces-and-atl.md)

