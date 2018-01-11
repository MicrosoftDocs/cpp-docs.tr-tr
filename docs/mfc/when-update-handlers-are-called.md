---
title: "Güncelleştirme işleyicilerini çağırma zamanı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- updating user interface objects [MFC]
- command routing [MFC], update commands
- toolbar buttons [MFC], enabling
- disabling toolbar buttons
- menus [MFC], initializing
- update handlers [MFC]
- disabling menu items
- toolbars [MFC], updating
- menus [MFC], updating as context changes
- toolbar controls [MFC], updated during OnIdle method [MFC]
- menu items, enabling
- command routing [MFC], update handlers
- update handlers, calling
ms.assetid: 7359f6b1-4669-477d-bd99-690affed08d9
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: eaf2773a2d9e393c783a39e01c75f8efa62796df
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="when-update-handlers-are-called"></a>Güncelleştirme İşleyicilerini Çağırma Zamanı
Kullanıcının oluşturduğu Dosya menüsünde fare tıklamaları varsayalım bir `WM_INITMENUPOPUP` ileti. Kullanıcı görebilmesi menüyü aşağı bırakır önce framework'ün güncelleştirme mekanizması topluca Dosya menüsünden tüm öğeleri güncelleştirir.  
  
 Bunu yapmak için standart komut yönlendirmeyi boyunca açılır menüde tüm menü öğeleri için komutları framework yollar güncelleştirin. Yönlendirme komut hedefleri tüm menü öğelerini güncelleştirme komutu bir uygun ileti eşleme girişi ile eşleştirerek güncelleştirme fırsatına sahip (form `ON_UPDATE_COMMAND_UI`) ve bir "Güncelleştirme işleyici" işlevi çağırma. Bu nedenle, altı menü öğelerini içeren bir menü için altı güncelleştirme komutları gönderilir. Menü öğesi komut kimliği için bir güncelleştirme işleyici zaten varsa, güncelleştirme yapmak için çağrılır. Aksi durumda, framework bu komut kimliği için bir işleyici varlığını denetler ve etkinleştirir veya menü öğesi uygun olarak devre dışı bırakır.  
  
 Framework değil bulamazsa bir `ON_UPDATE_COMMAND_UI` komut yönlendirme sırasında girişi, onu otomatik olarak etkinleştirir kullanıcı arabirimi nesne varsa bir `ON_COMMAND` girişi yerde aynı komut kimliği. Aksi takdirde, kullanıcı arabirimi nesne devre dışı bırakır. Bu nedenle, bir kullanıcı arabirimi nesnesi etkinleştirildiğinden emin olmak için bir işleyici nesnesi oluşturur komutu için sağlayın veya bir güncelleştirme işleyici için sağlayın. Şekil konusunda bkz [kullanıcı arabirimi nesneleri ve komut kimlikleri](../mfc/user-interface-objects-and-command-ids.md).  
  
 Devre dışı bırakma varsayılan kullanıcı arabirimi nesnelerini devre dışı bırakmak mümkündür. Daha fazla bilgi için bkz: [m_bAutoMenuEnable](../mfc/reference/cframewnd-class.md#m_bautomenuenable) sınıf üyesi `CFrameWnd` içinde *MFC başvurusu*.  
  
 Menü başlatma uygulama aldığında gerçekleşen Framework'te otomatik bir `WM_INITMENUPOPUP` ileti. Boşta döngü sırasında menüleri için yaptığı gibi komut düğmesi güncelleştirme işleyicileri için benzer şekilde yönlendirme framework arar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: Kullanıcı Arabirimi Nesnelerini Güncelleştirme](../mfc/how-to-update-user-interface-objects.md)

