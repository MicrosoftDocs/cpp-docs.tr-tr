---
title: Kalıcı iletişim kutuları oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- modal dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
- MFC dialog boxes [MFC], modal
ms.assetid: 26c7a68c-79f6-4862-a5a8-6024984644d2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2a8bc947dbaf9cecc680f3cdbd8e6b429d2bcd5f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33342435"
---
# <a name="creating-modal-dialog-boxes"></a>Kalıcı İletişim Kutuları Oluşturma
Modal bir iletişim kutusu oluşturmak için bildirilen iki ortak oluşturucu birini çağırın [CDialog](../mfc/reference/cdialog-class.md). Ardından, iletişim nesnenin çağrısı [DoModal](../mfc/reference/cdialog-class.md#domodal) üye işlevi iletişim kutusunu görüntülemek ve kullanıcı Tamam seçer kadar onunla etkileşimi yönetmek veya iptal edin. Bu yönetim tarafından `DoModal` ne iletişim kutusu kalıcı kılan unsurdur. Kalıcı iletişim kutuları için `DoModal` iletişim kutusu kaynağı yükler.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bir İletişim Kutusunun Yaşam Döngüsü](../mfc/life-cycle-of-a-dialog-box.md)

