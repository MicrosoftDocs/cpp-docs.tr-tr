---
title: Standart komut ve pencere kimlikleri | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.mfc.macros
dev_langs: C++
helpviewer_keywords: standard command and Window IDs
ms.assetid: 0424805c-fff8-4531-8f0c-15cfb13aa612
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2c8195b1ab967a0d6692e839b1db1e89ee6694d5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="standard-command-and-window-ids"></a>Standart Komut ve Pencere Kimlikleri
Microsoft Foundation Class Kitaplığı Afxres.h içinde bir dizi standart komut ve pencere kimlikleri tanımlar. Bu kimlikleri, ileti işleyicisi işlevlerinizi eşlemesi için kaynak düzenleyicileri ve Özellikler penceresini içinde en yaygın olarak kullanılır. Tüm standart komutları sahip bir **ID_** öneki. Menü Düzenleyicisi'ni kullandığınızda, örneğin, normal olarak Dosya Aç menü öğesi standart bağladığınız `ID_FILE_OPEN` komut kimliği.  
  
 İleti eşlemeleri kendi birincil framework sınıflardaki komutları framework işlemesi nedeniyle en standart komutlar için uygulama kodu komut kimliği başvurun gerekmez ( `CWinThread`, `CWinApp`, < c4 > `CView` , **CDocument**, vb.).  
  
 Bir önek olan diğer standart kimlikleri sayısı tanımlanan standart komut kimlikleri yanı sıra, **AFX_ID**. Bu kimlikleri standart pencere kimlikleri içerir (önek **AFX_IDW_**), kimlikleri dize (önek **AFX_IDS_**) ve diğer çeşitli türleri.  
  
 İle başlayan kimlikleri **AFX_ID** öneki nadiren programcıları tarafından kullanılır, ancak bu kimlikleri için de bkz framework işlevleri geçersiz kılarken başvurmanız gerekebilir **AFX_ID**s.  
  
 Kimlikleri bu başvuruda ayrı ayrı açıklanmamıştır. Teknik notları bunları hakkında daha fazla bilgi bulabilirsiniz [20](../../mfc/tn020-id-naming-and-numbering-conventions.md), [21](../../mfc/tn021-command-and-message-routing.md), ve [22](../../mfc/tn022-standard-commands-implementation.md).  
  
> [!NOTE]
>  Üstbilgi dosyası Afxres.h dolaylı Afxwin.h dahil edilir. Aşağıdaki deyim açıkça uygulamanızın kaynak (.rc) komut dosyası şunları içermelidir:  
  
 [!code-cpp[NVC_MFC_Utilities#47](../../mfc/codesnippet/cpp/standard-command-and-window-ids_1.h)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md)
