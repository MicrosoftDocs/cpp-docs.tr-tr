---
description: 'Hakkında daha fazla bilgi edinin: Iletişim nesnesinden veri alma'
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
ms.openlocfilehash: 823006b7b892c8e6476d007eb5cc13fb1386458e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97218049"
---
# <a name="retrieving-data-from-the-dialog-object"></a>İletişim Nesnesinden Veriyi Geri Alma

Framework, bir iletişim kutusundaki denetim değerlerini başlatmanın ve denetimlerden değerleri almak için kolay bir yol sağlar. Daha laborious el ile yapılan yaklaşım, `SetDlgItemText` ve `GetDlgItemText` `CWnd` denetim pencereleri için uygulanan sınıfının ve üye işlevleri gibi işlevleri çağırmalıdır. Bu işlevlerle, ve gibi işlevleri çağırarak, her denetime tek tek erişin veya değerini alır `SetWindowText` `GetWindowText` . Çerçevenin yaklaşımı, başlatma ve almayı otomatikleştirir.

İletişim kutusu veri değişimi (DDX), iletişim kutusundaki denetimler ve iletişim kutusu nesnesindeki üye değişkenleri arasında daha kolay veri alışverişi yapmanızı sağlar. Bu değişim her iki şekilde de çalışmaktadır. İletişim kutusundaki denetimleri başlatmak için, iletişim kutusu nesnesindeki veri üyelerinin değerlerini ayarlayabilirsiniz ve çerçeve, iletişim kutusu görüntülenmeden önce değerleri denetimlere aktarır. Ardından, iletişim kutusu veri üyelerini Kullanıcı tarafından girilen verilerle güncelleştirebilirsiniz. Bu noktada, veri üyesi değişkenlerine başvurarak verileri kullanabilirsiniz.

İletişim kutusu veri doğrulama (DDV) ile otomatik olarak doğrulanacak iletişim kutusu denetimlerinin değerlerini de düzenleyebilirsiniz.

DDX ve DDV [Iletişim kutusu veri değişimi ve doğrulaması](../mfc/dialog-data-exchange-and-validation.md)konusunda daha ayrıntılı olarak açıklanmıştır.

Kalıcı bir iletişim kutusu için, Kullanıcı tarafından girilen, ancak iletişim kutusu nesnesi yok edileceği zaman bir veri alabilirsiniz `DoModal` . Kalıcı olmayan iletişim kutusu için, `UpdateData` **true** bağımsız değişkeniyle çağırarak ve ardından iletişim kutusu sınıfı üye değişkenlerine erişerek iletişim kutusu nesnesinden veri alabilirsiniz. Bu konu, [Iletişim kutusu veri değişimi ve doğrulaması](../mfc/dialog-data-exchange-and-validation.md)konusunda daha ayrıntılı olarak ele alınmıştır.

## <a name="see-also"></a>Ayrıca bkz.

[MFC’de İletişim Kutularıyla çalışma](../mfc/life-cycle-of-a-dialog-box.md)
