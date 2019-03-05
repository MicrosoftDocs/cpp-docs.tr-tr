---
title: İletişim Kutusu Veri Değişimi
ms.date: 11/19/2018
helpviewer_keywords:
- initializing dialog boxes
- canceling data exchange
- dialog box data, retrieving
- DDX (dialog data exchange), data exchange mechanism
- dialog boxes [MFC], initializing
- dialog boxes [MFC], retrieving user input using DDX
- dialog box data
- dialog boxes [MFC], data exchange
- CDataExchange class [MFC], using DDX
- DoDataExchange method [MFC]
- user input [MFC], retrieving from MFC dialog boxes
- capturing user input [MFC]
- transferring dialog box data
- DDX (dialog data exchange), canceling
- UpdateData method [MFC]
- retrieving dialog box data [MFC]
ms.assetid: 4675f63b-41d2-45ed-b6c3-235ad8ab924b
ms.openlocfilehash: 338630aef358d9490461179288d5c45a2d3b821c
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57302328"
---
# <a name="dialog-data-exchange"></a>İletişim Kutusu Veri Değişimi

DDX mekanizması kullanırsanız, iletişim kutusunun Başlangıç değerlerini nesnenin üye değişkenleri genellikle içinde ayarladığınız, `OnInitDialog` işleyicisi ya da iletişim Oluşturucusu. İletişim kutusu görüntülenmeden önce framework'ün DDX mekanizması göründüğü iletişim kutusu denetimleri için üye değişkenlerinin değerlerini aktarır hemen iletişim kutusu göründüğünde yanıt olarak `DoModal` veya `Create`. Varsayılan uygulaması `OnInitDialog` içinde `CDialog` çağrıları `UpdateData` sınıfının üye işlevinde `CWnd` iletişim kutusu denetimleri başlatılamadı.

Kullanıcı Tamam düğmesine tıkladığında mekanizma değerleri denetimleri için üye değişkenleri aktarır (veya çağırmanızı her `UpdateData` üye işlevi bağımsız değişken ile **TRUE**). İletişim kutusu veri doğrulama mekanizmasını doğrulama kuralları belirtilen tüm veri öğeleri doğrular.

Aşağıdaki şekil, iletişim kutusu veri değişimi gösterir.

![İletişim kutusu veri değişimi](../mfc/media/vc379d1.gif "iletişim kutusu veri değişimi") <br/>
İletişim Kutusu Veri Değişimi

`UpdateData` Her iki yönde belirtildiği gibi çalışır **BOOL** kendisine geçirilen parametre. Exchange taşımak için `UpdateData` ayarlayan bir `CDataExchange` iletişim sınıfınızın geçersiz nesne ve çağrıları `CDialog`'s `DoDataExchange` üye işlevi. `DoDataExchange` türünde bir bağımsız değişken `CDataExchange`. `CDataExchange` Geçirilen nesne `UpdateData` gibi bilgiler exchange yönünü tanımlama exchange bağlamını temsil eder.

Ne zaman (veya bir kod Sihirbazı) geçersiz kılma `DoDataExchange`, veri üyesi (Denetim) başına tek bir DDX işlevi çağrısı belirtin. Her DDX işlevi tarafından sağlanan bağlam göre her iki yönde veri değişimi nasıl bilir `CDataExchange` geçirilen bağımsız değişken, `DoDataExchange` tarafından `UpdateData`.

MFC exchange farklı türde birçok DDX işlevleri sağlar. Aşağıdaki örnekte gösterildiği bir `DoDataExchange` geçersiz kılma iki hangi DDX işlevleri ve bir DDV işlevi çağrılır:

[!code-cpp[NVC_MFCControlLadenDialog#49](../mfc/codesnippet/cpp/dialog-data-exchange_1.cpp)]

`DDX_` Ve `DDV_` satırla veri eşlemesi. Gösterilen örnek DDX ve DDV işlevleri sırasıyla bir onay kutusu denetimi ve bir düzenleme kutusu denetim içindir.

Kalıcı bir iletişim kutusu, kullanıcı iptal ederse `OnCancel` üye işlevi iletişim kutusunu sonlandırır ve `DoModal` değeri döndürür **IDCANCEL**. Bu durumda, veri iletişim nesnesi iletişim kutusu arasında değiştirilir.

## <a name="see-also"></a>Ayrıca bkz.

[İletişim Kutusu Veri Değişimi ve Doğrulaması](../mfc/dialog-data-exchange-and-validation.md)<br/>
[Bir İletişim Kutusunun Yaşam Döngüsü](../mfc/life-cycle-of-a-dialog-box.md)<br/>
[İletişim Verisi Doğrulama](../mfc/dialog-data-validation.md)
