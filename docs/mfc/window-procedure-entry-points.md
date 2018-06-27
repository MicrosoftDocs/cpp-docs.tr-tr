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
ms.openlocfilehash: 315526a8f95a1d62ac89f3a76fab492c9b136715
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36956388"
---
# <a name="window-procedure-entry-points"></a>Pencere Yordamı Giriş Noktaları
MFC pencere yordamları, özel pencere yordamı uygulama modülü statik bağlantılarıyla korumak için. MFC ile modülü bağlandığında bağlantı otomatik olarak gerçekleşir. Bu pencere yordamı etkili Modül durumu düzgün şekilde AFX_MANAGE_STATE makrosu kullanır ve ardından çağırır `AfxWndProc`, hangi sırayla temsilci için `WindowProc` üye işlevini uygun `CWnd`-nesne türetilmiş.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC Modüllerinin Durum Verisini Yönetme](../mfc/managing-the-state-data-of-mfc-modules.md)

