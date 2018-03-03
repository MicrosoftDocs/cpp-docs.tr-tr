---
title: "AtlAxWinInit çağırmak ne zaman gerekiyor mu? | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- AtlAxWinInit
dev_langs:
- C++
helpviewer_keywords:
- AtlAxWinInit method
ms.assetid: 080b9cfe-d85a-4439-a9e9-ab3966ebaa8e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 69dfcfbe0c8c05d275a5f3a8f86c30b0e59bd3a5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="when-do-i-need-to-call-atlaxwininit"></a>AtlAxWinInit çağırmak ne zaman gerekiyor mu?

[AtlAxWinInit](reference/composite-control-global-functions.md#atlaxwininit) kaydeder **"AtlAxWin80"** ana penceresinin oluşturmadan önce bu işlev çağrılması gerekir böylece pencere sınıfı (birkaç özel pencere iletileri). Bununla birlikte, her zaman API'leri (ve bunları sınıfları) barındırma itibaren açıkça, bu işlevi çağırmak kullanmadığınız genellikle sizin için bu işlevini çağırın. Bu işlev birden çok kez çağırma içinde hiçbir zarar yoktur. biçimindeki telefon numarasıdır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 AtlAxWinTerm çağırmak ne zaman gerekiyor mu     
 [Denetim kapsamı SSS](../atl/atl-control-containment-faq.md)
