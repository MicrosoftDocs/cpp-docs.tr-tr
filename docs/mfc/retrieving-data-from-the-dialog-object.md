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
ms.openlocfilehash: 3055468c04bba7c9cb999d0a642c0819524ff7e7
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46391416"
---
# <a name="retrieving-data-from-the-dialog-object"></a>İletişim Nesnesinden Veriyi Geri Alma

Framework'te iletişim kutusundaki denetimlerin değerleri başlatır ve denetimlerini değerleri almak için kolay bir yol sağlar. Daha zahmetli el ile işlevleri çağırmak için yaklaşımdır `SetDlgItemText` ve `GetDlgItemText` sınıfın üye işlevleri `CWnd`, Denetim windows için geçerlidir. Sahip bu işlevlerin, size her denetimi ayrı ayrı veya kendi değeri gibi işlevleri çağırma erişim `SetWindowText` ve `GetWindowText`. Framework'ün yaklaşım, başlatma ve alma otomatikleştirir.

İletişim kutusu veri değişimi (DDX) daha kolay iletişim nesnesi iletişim kutusu ve üye değişkenlerinde denetimler arasında veri alışverişi sağlar. Bu exchange iki şekilde de çalışır. İletişim kutusundaki denetimler başlatmak için iletişim nesnesi içinde veri üyelerinin değerlerini ayarlayabilirsiniz ve iletişim kutusu görüntülenmeden önce framework denetimlere değerleri aktarın. Ardından kullanıcı tarafından girilen veriler ile iletişim veri üyeleri herhangi bir zamanda güncelleştirebilirsiniz. Bu noktada, veri üye değişkenlerine bakarak verileri kullanabilirsiniz.

İletişim verisi doğrulama (DDV) otomatik olarak doğrulanması için iletişim kutusu denetimleri değerlerinin düzenleyebilirsiniz.

DDX ve DDV daha ayrıntılı olarak açıklanmıştır [iletişim kutusu veri değişimi ve doğrulaması](../mfc/dialog-data-exchange-and-validation.md).

Kalıcı bir iletişim kutusu için kullanıcının girdiği herhangi bir veri alabilirsiniz `DoModal` IDOK döndürür, ancak önce iletişim nesnesi yok. Modsuz iletişim kutusu için veri iletişim nesnesinden herhangi bir zamanda çağırarak alabilirsiniz `UpdateData` bağımsız değişkeniyle **TRUE** ve sonra iletişim kutusu sınıfı üye değişkenlerine erişme. Bu konu içinde daha ayrıntılı olarak ele alınan [iletişim kutusu veri değişimi ve doğrulaması](../mfc/dialog-data-exchange-and-validation.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Bir İletişim Kutusunun Yaşam Döngüsü](../mfc/life-cycle-of-a-dialog-box.md)

