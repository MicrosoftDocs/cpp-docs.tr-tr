---
title: "Tek bir pencere birden fazla denetiminde barındırmak? | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- controls [ATL], hosting multiple
- windows [C++], hosting multiple controls
ms.assetid: 3a967a1a-7e7e-42e3-8eed-f7bde912363f
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5fa1a1b914d7d9725e8f2d9858f0481bb7aa24a4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="can-i-host-more-than-one-control-in-a-single-window"></a>Tek bir pencere birden fazla denetiminde barındırmak?
Bir tek ATL ana penceresinde birden fazla denetim barındırmak mümkün değildir. Her konak penceresi (Bu ileti yansıma ve denetim başına ortam özelliklerine işlemek için basit bir mekanizma sağlar) bir defada tek bir denetim tutmak için tasarlanmıştır. Ancak, tek bir pencere birden çok denetimlerinde görmek için kullanıcının gerekir, birden çok ana bilgisayar windows penceresinin alt öğesi oluşturmak için atmaktan olur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Denetim kapsamı SSS](../atl/atl-control-containment-faq.md)

