---
title: "Kalıcı iletişim kutuları oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- modal dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
- MFC dialog boxes [MFC], modal
ms.assetid: 26c7a68c-79f6-4862-a5a8-6024984644d2
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 662455a3ad0c45b287f485e3b87cc5437343bffb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="creating-modal-dialog-boxes"></a>Kalıcı İletişim Kutuları Oluşturma
Modal bir iletişim kutusu oluşturmak için bildirilen iki ortak oluşturucu birini çağırın [CDialog](../mfc/reference/cdialog-class.md). Ardından, iletişim nesnenin çağrısı [DoModal](../mfc/reference/cdialog-class.md#domodal) üye işlevi iletişim kutusunu görüntülemek ve kullanıcı Tamam seçer kadar onunla etkileşimi yönetmek veya iptal edin. Bu yönetim tarafından `DoModal` ne iletişim kutusu kalıcı kılan unsurdur. Kalıcı iletişim kutuları için `DoModal` iletişim kutusu kaynağı yükler.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İletişim kutusunun yaşam döngüsü](../mfc/life-cycle-of-a-dialog-box.md)

