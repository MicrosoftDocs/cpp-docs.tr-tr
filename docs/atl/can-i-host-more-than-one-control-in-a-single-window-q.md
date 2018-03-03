---
title: "Tek bir pencere birden fazla denetiminde barındırmak? | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- controls [ATL], hosting multiple
- windows [C++], hosting multiple controls
ms.assetid: 3a967a1a-7e7e-42e3-8eed-f7bde912363f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: be87c0bad9ab250593847cc24d16158030040054
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="can-i-host-more-than-one-control-in-a-single-window"></a>Tek bir pencere birden fazla denetiminde barındırmak?
Bir tek ATL ana penceresinde birden fazla denetim barındırmak mümkün değildir. Her konak penceresi (Bu ileti yansıma ve denetim başına ortam özelliklerine işlemek için basit bir mekanizma sağlar) bir defada tek bir denetim tutmak için tasarlanmıştır. Ancak, tek bir pencere birden çok denetimlerinde görmek için kullanıcının gerekir, birden çok ana bilgisayar windows penceresinin alt öğesi oluşturmak için atmaktan olur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Denetim kapsamı SSS](../atl/atl-control-containment-faq.md)

