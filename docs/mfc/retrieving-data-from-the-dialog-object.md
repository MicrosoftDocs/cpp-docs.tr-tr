---
title: İletişim Nesnesinden Veriyi Geri Alma
ms.date: 11/04/2016
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
ms.openlocfilehash: 345a2894693eace5aa464ca3940c785b2da08784
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50615140"
---
# <a name="retrieving-data-from-the-dialog-object"></a>İletişim Nesnesinden Veriyi Geri Alma

Framework'te iletişim kutusundaki denetimlerin değerleri başlatır ve denetimlerini değerleri almak için kolay bir yol sağlar. Daha zahmetli el ile işlevleri çağırmak için yaklaşımdır `SetDlgItemText` ve `GetDlgItemText` sınıfın üye işlevleri `CWnd`, Denetim windows için geçerlidir. Sahip bu işlevlerin, size her denetimi ayrı ayrı veya kendi değeri gibi işlevleri çağırma erişim `SetWindowText` ve `GetWindowText`. Framework'ün yaklaşım, başlatma ve alma otomatikleştirir.

İletişim kutusu veri değişimi (DDX) daha kolay iletişim nesnesi iletişim kutusu ve üye değişkenlerinde denetimler arasında veri alışverişi sağlar. Bu exchange iki şekilde de çalışır. İletişim kutusundaki denetimler başlatmak için iletişim nesnesi içinde veri üyelerinin değerlerini ayarlayabilirsiniz ve iletişim kutusu görüntülenmeden önce framework denetimlere değerleri aktarın. Ardından kullanıcı tarafından girilen veriler ile iletişim veri üyeleri herhangi bir zamanda güncelleştirebilirsiniz. Bu noktada, veri üye değişkenlerine bakarak verileri kullanabilirsiniz.

İletişim verisi doğrulama (DDV) otomatik olarak doğrulanması için iletişim kutusu denetimleri değerlerinin düzenleyebilirsiniz.

DDX ve DDV daha ayrıntılı olarak açıklanmıştır [iletişim kutusu veri değişimi ve doğrulaması](../mfc/dialog-data-exchange-and-validation.md).

Kalıcı bir iletişim kutusu için kullanıcının girdiği herhangi bir veri alabilirsiniz `DoModal` IDOK döndürür, ancak önce iletişim nesnesi yok. Modsuz iletişim kutusu için veri iletişim nesnesinden herhangi bir zamanda çağırarak alabilirsiniz `UpdateData` bağımsız değişkeniyle **TRUE** ve sonra iletişim kutusu sınıfı üye değişkenlerine erişme. Bu konu içinde daha ayrıntılı olarak ele alınan [iletişim kutusu veri değişimi ve doğrulaması](../mfc/dialog-data-exchange-and-validation.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Bir İletişim Kutusunun Yaşam Döngüsü](../mfc/life-cycle-of-a-dialog-box.md)

