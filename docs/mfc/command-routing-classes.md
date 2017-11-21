---
title: "Komut yönlendirme sınıfları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.classes.command
dev_langs: C++
helpviewer_keywords:
- MFC, command routing
- command routing [MFC], classes
ms.assetid: 4b50e689-2c54-4e6c-90f0-37333e22b2a1
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5e1fb5446a05b8b4227812be77124071abbed2b8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="command-routing-classes"></a>Komut Yönlendirme Sınıfları
Menüleri veya denetim çubuğu düğmelerini fareyle seçerek kullanıcı uygulama ile etkileşim gibi uygulamanın uygun komut hedefi nesneye etkilenen kullanıcı arabirimi nesnesinden iletileri gönderir. Komut hedefi sınıfları türetilen `CCmdTarget` dahil [CWinApp](../mfc/reference/cwinapp-class.md), [CWnd](../mfc/reference/cwnd-class.md), [CDocTemplate](../mfc/reference/cdoctemplate-class.md), [CDocument](../mfc/reference/cdocument-class.md), [CView](../mfc/reference/cview-class.md), ve bunlardan türetilmiş sınıfları. Böylece komutları uygulama şu anda etkin en uygun nesnesi tarafından işlenip otomatik komut yönlendirme framework destekler.  
  
 Sınıfın bir nesnesi `CCmdUI` komut hedefleri update komutunun UI geçirilen ([on_update_command_uı](reference/message-map-macros-mfc.md#on_update_command_ui)), belirli bir komut için kullanıcı arabirimi durumunu güncelleştirmek izin vermek için işleyiciler (örneğin, için onay veya kaldırma onay menü öğelerinden). Üye işlevlerini çağırın `CCmdUI` UI nesnenin durumunu güncelleştirmek için nesne. Menü öğesi veya bir düğme veya her ikisi de belirli bir komutla ilişkili kullanıcı Arabirimi nesnesi olup olmadığını bu işlemi aynıdır.  
  
 [CCmdTarget](../mfc/reference/ccmdtarget-class.md)  
 Alabilir ve iletileri yanıtlayın nesnelerin tüm sınıflar için temel sınıf olarak görev yapar.  
  
 [Ccmduı](../mfc/reference/ccmdui-class.md)  
 Menü öğeleri veya denetim çubuğu düğmelerini gibi kullanıcı arabirimi nesnelerini güncelleştirme için programa dayalı bir arabirim sağlar. Komut hedef nesnesi etkinleştirir, devre dışı bırakır, denetler ve/veya bu nesne kullanıcı arabirimi nesnesiyle temizler.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../mfc/class-library-overview.md)

