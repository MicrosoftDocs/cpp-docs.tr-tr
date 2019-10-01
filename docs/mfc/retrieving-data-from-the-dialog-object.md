---
title: Iletişim nesnesinden verileri alma
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
ms.openlocfilehash: 903d76a1e672d05a3c093e528f7153562df8e3e5
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2019
ms.locfileid: "71685574"
---
# <a name="retrieving-data-from-the-dialog-object"></a>Iletişim nesnesinden verileri alma

Framework, bir iletişim kutusundaki denetim değerlerini başlatmanın ve denetimlerden değerleri almak için kolay bir yol sağlar. Daha fazla laborious el ile yaklaşımı, denetim pencereleri için uygulanan `CWnd` sınıfının `SetDlgItemText` ve `GetDlgItemText` üye işlevleri gibi işlevleri çağırmalıdır. Bu işlevlerle, her denetime, `SetWindowText` ve `GetWindowText` gibi işlevleri çağırarak, değerini ayarlamak veya almak için tek tek erişirsiniz. Çerçevenin yaklaşımı, başlatma ve almayı otomatikleştirir.

İletişim kutusu veri değişimi (DDX), iletişim kutusundaki denetimler ve iletişim kutusu nesnesindeki üye değişkenleri arasında daha kolay veri alışverişi yapmanızı sağlar. Bu değişim her iki şekilde de çalışmaktadır. İletişim kutusundaki denetimleri başlatmak için, iletişim kutusu nesnesindeki veri üyelerinin değerlerini ayarlayabilirsiniz ve çerçeve, iletişim kutusu görüntülenmeden önce değerleri denetimlere aktarır. Ardından, iletişim kutusu veri üyelerini Kullanıcı tarafından girilen verilerle güncelleştirebilirsiniz. Bu noktada, veri üyesi değişkenlerine başvurarak verileri kullanabilirsiniz.

İletişim kutusu veri doğrulama (DDV) ile otomatik olarak doğrulanacak iletişim kutusu denetimlerinin değerlerini de düzenleyebilirsiniz.

DDX ve DDV [Iletişim kutusu veri değişimi ve doğrulaması](../mfc/dialog-data-exchange-and-validation.md)konusunda daha ayrıntılı olarak açıklanmıştır.

Kalıcı bir iletişim kutusu için, `DoModal` ' ı döndürdüğünde, ancak iletişim kutusu nesnesi yok edildiğinde kullanıcı tarafından girilen tüm verileri alabilirsiniz. Kalıcı olmayan iletişim kutusu için, **doğru** bağımsız değişkenle `UpdateData` ' ı çağırarak ve ardından iletişim kutusu sınıfı üye değişkenlerine erişerek, iletişim kutusu nesnesinden veri alabilirsiniz. Bu konu, [Iletişim kutusu veri değişimi ve doğrulaması](../mfc/dialog-data-exchange-and-validation.md)konusunda daha ayrıntılı olarak ele alınmıştır.

## <a name="see-also"></a>Ayrıca bkz.

[MFC 'de Iletişim kutularıyla çalışma](../mfc/life-cycle-of-a-dialog-box.md)
