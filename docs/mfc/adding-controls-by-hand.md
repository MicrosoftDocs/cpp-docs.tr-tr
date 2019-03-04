---
title: El İle Denetim Ekleme
ms.date: 11/04/2016
helpviewer_keywords:
- Windows common controls [MFC], adding
- dialog box controls [MFC], adding to dialog boxes
- controlling input focus
- input focus control
- focus, controlling input [MFC]
- controls [MFC], adding to dialog boxes
- common controls [MFC], adding
ms.assetid: bc843e59-0c51-4b5b-8bf2-343f716469d2
ms.openlocfilehash: c70539b49fcf2aa87f0bee375a87b38277b6ed42
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57270767"
---
# <a name="adding-controls-by-hand"></a>El İle Denetim Ekleme

Yapabilirsiniz veya [iletişim kutusu Düzenleyicisi ile iletişim kutusuna denetimler ekleme](../mfc/using-the-dialog-editor-to-add-controls.md) veya bunları kendiniz ile kod ekleme.

Denetim nesnesi kendiniz oluşturmanız için genellikle C++ denetim nesnesi bir C++ iletişim kutusu veya çerçeve-pencere nesnesi katıştırır. Diğer birçok nesne gibi Framework'te, denetimler için iki aşamalı yapımı gerekiyor. Denetimin çağırmalıdır **Oluştur** üst iletişim kutusu veya çerçeve penceresi oluşturma işleminin parçası olarak üye işlevi. İletişim kutuları için bu genellikle yapılabilir [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog)ve çerçeve pencereleri için de [OnCreate](../mfc/reference/cwnd-class.md#oncreate).

Aşağıdaki örnek nasıl bildirdiğiniz gösterir bir `CEdit` nesne türetilmiş iletişim kutusu sınıfı sınıf bildiriminde ve sonra çağrı `Create` üye işlevinde `OnInitDialog`. Çünkü `CEdit` iletişim nesnesi oluşturulur, ancak bu yine de kendi ile başlatılmalıdır otomatik olarak oluşturulur, nesne katıştırılmış nesne olarak bildirilen `Create` üye işlevi.

[!code-cpp[NVC_MFCControlLadenDialog#1](../mfc/codesnippet/cpp/adding-controls-by-hand_1.h)]

Aşağıdaki `OnInitDialog` işlevi bir dikdörtgen ayarlar daha sonra çağırır `Create` Windows düzenleme denetimi oluşturup başlatılmamış eklemek için `CEdit` nesne.

[!code-cpp[NVC_MFCControlLadenDialog#2](../mfc/codesnippet/cpp/adding-controls-by-hand_2.cpp)]

Düzenleme nesnesini oluşturduktan sonra da giriş odağı denetimi çağırarak ayarlayabilirsiniz `SetFocus` üye işlevi. Son olarak, 0'dan iade `OnInitDialog` odağı ayarlamasını gösterilecek. Sıfır olmayan bir değer döndürürse, iletişim kutusu yöneticisini odak ilk iletişim kutusu öğe listesi denetim öğesini ayarlar. Çoğu durumda, denetimleri, iletişim kutuları için iletişim kutusu Düzenleyicisi ile eklemek isteyebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Denetimleri Yapma ve Kullanma](../mfc/making-and-using-controls.md)<br/>
[Denetimler](../mfc/controls-mfc.md)<br/>
[CDialog::OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog)
