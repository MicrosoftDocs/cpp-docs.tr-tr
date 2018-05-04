---
title: Tek bir pencere birden fazla denetiminde barındırmak? | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- controls [ATL], hosting multiple
- windows [C++], hosting multiple controls
ms.assetid: 3a967a1a-7e7e-42e3-8eed-f7bde912363f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ceb9444b6371e261115bbf52ef5a249100772d1f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="can-i-host-more-than-one-control-in-a-single-window"></a>Tek bir pencere birden fazla denetiminde barındırmak?
Bir tek ATL ana penceresinde birden fazla denetim barındırmak mümkün değildir. Her konak penceresi (Bu ileti yansıma ve denetim başına ortam özelliklerine işlemek için basit bir mekanizma sağlar) bir defada tek bir denetim tutmak için tasarlanmıştır. Ancak, tek bir pencere birden çok denetimlerinde görmek için kullanıcının gerekir, birden çok ana bilgisayar windows penceresinin alt öğesi oluşturmak için atmaktan olur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Denetim kapsamı SSS](../atl/atl-control-containment-faq.md)

