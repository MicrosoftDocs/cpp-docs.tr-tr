---
title: "Pencere yordamı giriş noktaları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- state management, window procedures
- MFC, managing state data
- window procedure entry points
- entry points, window procedures
ms.assetid: a6b46a7f-6e42-45f2-9ae6-82e19fc57148
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 99a4cf3fe356cf888101935aba5bec9a599135f9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="window-procedure-entry-points"></a>Pencere Yordamı Giriş Noktaları
MFC pencere yordamları, özel pencere yordamı uygulama modülü statik bağlantılarıyla korumak için. MFC ile modülü bağlandığında bağlantı otomatik olarak gerçekleşir. Bu pencere yordamı kullanır `AFX_MANAGE_STATE` çağırır sonra etkin Modül durumu düzgün bir şekilde ayarlamak için makrosu **AfxWndProc**, hangi sırayla temsilci için `WindowProc` üye işlevini uygun `CWnd`-türetilen nesne.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC modüllerinin durum verisini yönetme](../mfc/managing-the-state-data-of-mfc-modules.md)

