---
title: AtlAxWinInit çağırmak ne zaman gerekiyor mu? | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- AtlAxWinInit
dev_langs:
- C++
helpviewer_keywords:
- AtlAxWinInit method
ms.assetid: 080b9cfe-d85a-4439-a9e9-ab3966ebaa8e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bd9aa1dd14ccae555d4ab9acbbac15e9b66cafe6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="when-do-i-need-to-call-atlaxwininit"></a>AtlAxWinInit çağırmak ne zaman gerekiyor mu?

[AtlAxWinInit](reference/composite-control-global-functions.md#atlaxwininit) kaydeder **"AtlAxWin80"** ana penceresinin oluşturmadan önce bu işlev çağrılması gerekir böylece pencere sınıfı (birkaç özel pencere iletileri). Bununla birlikte, her zaman API'leri (ve bunları sınıfları) barındırma itibaren açıkça, bu işlevi çağırmak kullanmadığınız genellikle sizin için bu işlevini çağırın. Bu işlev birden çok kez çağırma içinde hiçbir zarar yoktur. biçimindeki telefon numarasıdır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 AtlAxWinTerm çağırmak ne zaman gerekiyor mu     
 [Denetim kapsamı SSS](../atl/atl-control-containment-faq.md)
