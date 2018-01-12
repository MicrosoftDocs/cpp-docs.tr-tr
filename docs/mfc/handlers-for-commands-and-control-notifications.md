---
title: "Komutlar ve denetim bildirimleri için işleyiciler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- commands [MFC], handlers for
- functions [MFC], handler
- handlers [MFC]
- controls [MFC], notifications
- handlers [MFC], control notification [MFC]
- notifications [MFC], handlers for control
- handlers [MFC], command
ms.assetid: 20f57f4a-f577-4c09-80a2-43faf32a1c2e
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 748bdd1a2ce6b94a2c935df94de68767ee36875e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="handlers-for-commands-and-control-notifications"></a>Komutlar ve Denetim Bildirimleri için İşleyiciler
Komutları veya denetim bildirimi iletileri için hiçbir varsayılan işleyiciler vardır. Bu nedenle, bu kategorilerdeki iletileri için işleyicileri adlandırma, yalnızca kural tarafından bağlıdır. Bir işleyiciye komut veya denetim bildirim eşlediğinizde özellikleri windows komut kimliği veya denetim bildirimi koduna göre bir ad önerir. Önerilen adı kabul edin veya değiştirmek.  
  
 Kuralı, hem kategorilerdeki işleyicileri temsil ettikleri kullanıcı arabirimi nesnesi için ad önerir. Bu nedenle Düzen menüsünde kesme komutu için bir işleyici adlandırılmış olabilir  
  
 [!code-cpp[NVC_MFCMessageHandling#4](../mfc/codesnippet/cpp/handlers-for-commands-and-control-notifications_1.h)]  
  
 Cut komutu kadar sık uygulamalarda uygulanan çünkü framework Kes komut olarak komut kimliği önceden belirler **ıd_edıt_cut**. Tüm önceden tanımlanmış komut kimlikleri listesi için AFXRES dosyasına bakın. H. Daha fazla bilgi için bkz: [standart komutları](../mfc/standard-commands.md).  
  
 Buna ek olarak, kural için bir işleyici öneren **BN_CLICKED** "My Button" etiketli bir düğme bildirim iletisi adlandırılmış  
  
 [!code-cpp[NVC_MFCMessageHandling#5](../mfc/codesnippet/cpp/handlers-for-commands-and-control-notifications_2.h)]  
  
 Bu komut kimliği atayabilecek `IDC_MY_BUTTON` , uygulamaya özgü kullanıcı arabirimi nesneye eşdeğer olduğundan.  
  
 Her iki kategorilerdeki iletileri bağımsız değişkenler almayan ve herhangi bir değer döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İleti İşleyici İşlevlerini Bildirme](../mfc/declaring-message-handler-functions.md)
