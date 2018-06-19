---
title: Pencere yordamı giriş noktaları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- state management, window procedures
- MFC, managing state data
- window procedure entry points
- entry points, window procedures
ms.assetid: a6b46a7f-6e42-45f2-9ae6-82e19fc57148
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1095061cce8ff8f189984aca99a06eb741a46e83
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33382079"
---
# <a name="window-procedure-entry-points"></a>Pencere Yordamı Giriş Noktaları
MFC pencere yordamları, özel pencere yordamı uygulama modülü statik bağlantılarıyla korumak için. MFC ile modülü bağlandığında bağlantı otomatik olarak gerçekleşir. Bu pencere yordamı kullanır `AFX_MANAGE_STATE` çağırır sonra etkin Modül durumu düzgün bir şekilde ayarlamak için makrosu **AfxWndProc**, hangi sırayla temsilci için `WindowProc` üye işlevini uygun `CWnd`-türetilen nesne.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC Modüllerinin Durum Verisini Yönetme](../mfc/managing-the-state-data-of-mfc-modules.md)

