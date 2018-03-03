---
title: "Pencere yordamı giriş noktaları | Microsoft Docs"
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
- state management, window procedures
- MFC, managing state data
- window procedure entry points
- entry points, window procedures
ms.assetid: a6b46a7f-6e42-45f2-9ae6-82e19fc57148
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5f4e99ce38bd5ae472d688dc779bdd4ccf9fd4c5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="window-procedure-entry-points"></a>Pencere Yordamı Giriş Noktaları
MFC pencere yordamları, özel pencere yordamı uygulama modülü statik bağlantılarıyla korumak için. MFC ile modülü bağlandığında bağlantı otomatik olarak gerçekleşir. Bu pencere yordamı kullanır `AFX_MANAGE_STATE` çağırır sonra etkin Modül durumu düzgün bir şekilde ayarlamak için makrosu **AfxWndProc**, hangi sırayla temsilci için `WindowProc` üye işlevini uygun `CWnd`-türetilen nesne.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC Modüllerinin Durum Verisini Yönetme](../mfc/managing-the-state-data-of-mfc-modules.md)

