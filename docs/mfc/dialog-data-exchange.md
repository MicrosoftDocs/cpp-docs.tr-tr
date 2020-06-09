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
ms.openlocfilehash: c12953ab0b9922788747246a97115188b2f686ed
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84616813"
---
# <a name="dialog-data-exchange"></a>İletişim Kutusu Veri Değişimi

DDX mekanizmasını kullanırsanız, genellikle `OnInitDialog` işleyicinizde veya iletişim kutusunda, iletişim kutusu nesnesinin üye değişkenlerinin başlangıç değerlerini ayarlarsınız. İletişim kutusu görüntülenmeden hemen önce, Framework 'ün DDX mekanizması, üye değişkenlerinin değerlerini iletişim kutusundaki denetimlere aktarır. Bu, iletişim kutusunun kendisi veya ' a yanıt olarak göründüğünde görünürler `DoModal` `Create` . İçindeki öğesinin varsayılan uygulanması `OnInitDialog` , `CDialog` `UpdateData` `CWnd` iletişim kutusundaki denetimleri başlatmak için sınıfının üye işlevini çağırır.

Aynı mekanizma, Kullanıcı Tamam düğmesine tıkladığında (veya `UpdateData` **true**bağımsız değişkeniyle üye işlevini her çağırdığınızda) denetimleri üye değişkenlerine aktarır. İletişim kutusu veri doğrulama mekanizması, doğrulama kurallarını belirttiğiniz tüm veri öğelerini doğrular.

Aşağıdaki şekilde iletişim kutusu veri değişimi gösterilmektedir.

![İletişim kutusu veri değişimi](../mfc/media/vc379d1.gif "İletişim kutusu veri değişimi") <br/>
İletişim Kutusu Veri Değişimi

`UpdateData`, kendisine geçirilen **bool** parametresi tarafından belirtilen şekilde her iki yönde de işe yarar. Exchange 'i yürütmek için `UpdateData` bir `CDataExchange` nesnesi kurar ve iletişim kutusu sınıfınızın üye işlevini geçersiz kılmayı çağırır `CDialog` `DoDataExchange` . `DoDataExchange`türünde bir bağımsız değişken alır `CDataExchange` . `CDataExchange`Geçirilen nesne, değişim `UpdateData` yönü olarak bu tür bilgileri tanımlayarak Exchange bağlamını temsil eder.

(Veya bir kod Sihirbazı) geçersiz kıldığınızda `DoDataExchange` , veri üyesi başına BIR DDX işlevine (denetim) bir çağrı belirlersiniz. Her DDX işlevi, ' `CDataExchange` a geçirilen bağımsız değişkenin sağladığı içeriğe göre her iki yönde de verileri nasıl değiş tokuş etmek gerektiğini `DoDataExchange` bilir `UpdateData` .

MFC, farklı Exchange türleri için birçok DDX işlevi sağlar. Aşağıdaki örnekte, `DoDataExchange` ıkı DDX işlevinin ve bır DDV işlevinin çağrıldığı bir geçersiz kılma gösterilmektedir:

[!code-cpp[NVC_MFCControlLadenDialog#49](codesnippet/cpp/dialog-data-exchange_1.cpp)]

`DDX_`Ve `DDV_` satırları bir veri haritalardır. Gösterilen örnek DDX ve DDV işlevleri, sırasıyla bir onay kutusu denetimi ve bir düzenleme kutusu denetimi içindir.

Kullanıcı kalıcı iletişim kutusunu iptal ederse, `OnCancel` üye işlevi iletişim kutusunu sonlandırır ve `DoModal` **IDCANCEL**değerini döndürür. Bu durumda, iletişim kutusu ve iletişim kutusu nesnesi arasında veri alışverişi yapılmaz.

## <a name="see-also"></a>Ayrıca bkz.

[İletişim Kutusu Veri Değişimi ve Doğrulaması](dialog-data-exchange-and-validation.md)<br/>
[MFC’de İletişim Kutularıyla çalışma](life-cycle-of-a-dialog-box.md)<br/>
[İletişim kutusu verileri doğrulaması](dialog-data-validation.md)
