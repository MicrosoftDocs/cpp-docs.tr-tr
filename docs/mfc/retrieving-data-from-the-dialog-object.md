---
title: İletişim nesnesinden veriyi geri alma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- dialog boxes [MFC], retrieving user data
- dialog box data [MFC]
- data [MFC], retrieving
- GetDlgItemText method [MFC]
- SetDlgItemText method [MFC]
- SetWindowText method [MFC]
- dialog box data [MFC], retrieving
- retrieving data [MFC]
- user input [MFC], retrieving from MFC dialog boxes
- capturing user input [MFC]
- dialog box controls [MFC], initializing values
- DDX (dialog data exchange) [MFC]
- MFC dialog boxes [MFC], retrieving user input
- data retrieval [MFC], dialog boxes
- data [MFC], dialog boxes
- DDX (dialog data exchange) [MFC], about DDX
- DDX (dialog data exchange) [MFC], retrieving data from Dialog object
- GetWindowText method [MFC]
ms.assetid: bdca2b61-6b53-4c2e-b426-8712c7a38ec0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0ac243333c8dc778486dd18323658f262c6d6610
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33380214"
---
# <a name="retrieving-data-from-the-dialog-object"></a>İletişim Nesnesinden Veriyi Geri Alma
Framework'te iletişim kutusu denetimleri değerlerini başlatılamadı ve denetimlerden değerleri almak için kolay bir yol sağlar. Daha fazla zahmetli el ile işlevleri gibi çağırmak için yaklaşımdır `SetDlgItemText` ve `GetDlgItemText` sınıfının üye işlevleri `CWnd`, Denetim windows için geçerlidir. Bu işlevler ile tek tek ayarlamak veya kendi değerini almak için her denetim işlevleri gibi çağırma erişim `SetWindowText` ve `GetWindowText`. Framework'ün yaklaşım, başlatma ve alma otomatikleştirir.  
  
 İletişim kutusu veri değişimi (DDX) daha kolay iletişim nesnesi iletişim kutusu ve üye değişkenleri denetimlerinde arasında veri değişimi olanak sağlar. Bu exchange her iki yönde çalışır. İletişim kutusunda denetimleri başlatmak için iletişim nesnesinde veri üyelerinin değerlerini ayarlayabilirsiniz ve iletişim kutusu görüntülenmeden önce framework denetimlere değerleri aktarın. Ardından kullanıcı tarafından girilen verilerle iletişim veri üyeleri herhangi bir zamanda güncelleştirebilirsiniz. Bu noktada, veri üye değişkenlerine başvurarak verileri kullanabilirsiniz.  
  
 İletişim verisi doğrulama (DDV) otomatik olarak doğrulanacak iletişim kutusu denetimleri değerleri düzenleyebilirsiniz.  
  
 DDX ve DDV daha ayrıntılı olarak açıklanmıştır [iletişim kutusu veri değişimi ve doğrulaması](../mfc/dialog-data-exchange-and-validation.md).  
  
 Kalıcı iletişim kutusu için kullanıcı girilen herhangi bir veri alabilirsiniz `DoModal` döndürür **IDOK** ancak önce iletişim nesnesi yok. Kalıcı olmayan iletişim kutusu için veri iletişim nesnesinden herhangi bir zamanda çağırarak alabilirsiniz `UpdateData` bağımsız değişkeniyle **doğru** ve iletişim sınıf üye değişkenlerine erişme. Bu konu içinde daha ayrıntılı olarak ele alınmıştır [iletişim kutusu veri değişimi ve doğrulaması](../mfc/dialog-data-exchange-and-validation.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bir İletişim Kutusunun Yaşam Döngüsü](../mfc/life-cycle-of-a-dialog-box.md)

