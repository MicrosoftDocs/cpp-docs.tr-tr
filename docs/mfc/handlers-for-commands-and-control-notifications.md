---
title: Komutlar ve denetim bildirimleri için işleyiciler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- commands [MFC], handlers for
- functions [MFC], handler
- handlers [MFC]
- controls [MFC], notifications
- handlers [MFC], control notification [MFC]
- notifications [MFC], handlers for control
- handlers [MFC], command
ms.assetid: 20f57f4a-f577-4c09-80a2-43faf32a1c2e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 60c66beb3c0c8874bd3d678bfc4331dc766c443a
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36929137"
---
# <a name="handlers-for-commands-and-control-notifications"></a>Komutlar ve Denetim Bildirimleri için İşleyiciler
Komutları veya denetim bildirimi iletileri için hiçbir varsayılan işleyiciler vardır. Bu nedenle, bu kategorilerdeki iletileri için işleyicileri adlandırma, yalnızca kural tarafından bağlıdır. Bir işleyiciye komut veya denetim bildirim eşlediğinizde özellikleri windows komut kimliği veya denetim bildirimi koduna göre bir ad önerir. Önerilen adı kabul edin veya değiştirmek.  
  
 Kuralı, hem kategorilerdeki işleyicileri temsil ettikleri kullanıcı arabirimi nesnesi için ad önerir. Bu nedenle Düzen menüsünde kesme komutu için bir işleyici adlandırılmış olabilir  
  
 [!code-cpp[NVC_MFCMessageHandling#4](../mfc/codesnippet/cpp/handlers-for-commands-and-control-notifications_1.h)]  
  
 Cut komutu kadar sık uygulamalarda uygulanan çünkü framework Kes komut olarak komut kimliği önceden belirler **ıd_edıt_cut**. Tüm önceden tanımlanmış komut kimlikleri listesi için AFXRES dosyasına bakın. H. Daha fazla bilgi için bkz: [standart komutları](../mfc/standard-commands.md).  
  
 Buna ek olarak, kural için bir işleyici öneren **BN_CLICKED** "My Button" etiketli bir düğme bildirim iletisi adlandırılmış  
  
 [!code-cpp[NVC_MFCMessageHandling#5](../mfc/codesnippet/cpp/handlers-for-commands-and-control-notifications_2.h)]  
  
 Bu komut kimliği atayabilecek **IDC_MY_BUTTON** , uygulamaya özgü kullanıcı arabirimi nesneye eşdeğer olduğundan.  
  
 Her iki kategorilerdeki iletileri bağımsız değişkenler almayan ve herhangi bir değer döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İleti İşleyici İşlevlerini Bildirme](../mfc/declaring-message-handler-functions.md)
