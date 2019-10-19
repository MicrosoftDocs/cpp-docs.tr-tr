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
ms.openlocfilehash: 9a0199577ea46520c2eadc308812de8a1ce4b514
ms.sourcegitcommit: 8178d22701047d24f69f10d01ba37490e3d67241
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2019
ms.locfileid: "71685811"
---
# <a name="dialog-data-exchange"></a>İletişim Kutusu Veri Değişimi

DDX mekanizmasını kullanırsanız, genellikle `OnInitDialog` işleyicinizde veya iletişim kutusunda, iletişim kutusu nesnesinin üye değişkenlerinin başlangıç değerlerini ayarlarsınız. İletişim kutusu görüntülenmeden hemen önce, Framework 'ün DDX mekanizması, üye değişkenlerinin değerlerini iletişim kutusundaki denetimlere aktarır. Bu, iletişim kutusunun kendisi `DoModal` veya `Create` yanıt olarak göründüğünde görünürler. @No__t_1 `OnInitDialog` varsayılan uygulanması, iletişim kutusundaki denetimleri başlatmak için `CWnd` `UpdateData` üye işlevini çağırır.

Aynı mekanizma, Kullanıcı Tamam düğmesine tıkladığında (ya da **true**bağımsız değişkeniyle `UpdateData` member işlevini çağırdığınızda) denetimlerindeki değerleri üye değişkenlerine aktarır. İletişim kutusu veri doğrulama mekanizması, doğrulama kurallarını belirttiğiniz tüm veri öğelerini doğrular.

Aşağıdaki şekilde iletişim kutusu veri değişimi gösterilmektedir.

![İletişim kutusu veri değişimi](../mfc/media/vc379d1.gif "İletişim kutusu veri değişimi") <br/>
İletişim Kutusu Veri Değişimi

`UpdateData`, kendisine geçirilen **bool** parametresi tarafından belirtilen şekilde her iki yönde de işe yarar. Exchange 'i yürütmek için, `UpdateData` bir `CDataExchange` nesnesi kurar ve iletişim sınıfınızın `CDialog` `DoDataExchange` üye işlevinin geçersiz kılmasını çağırır. `DoDataExchange` `CDataExchange` türünde bir bağımsız değişken alır. @No__t_1 geçirilen `CDataExchange` nesnesi, değişim yönü olarak bu tür bilgileri tanımlayarak Exchange bağlamını temsil eder.

(Veya bir kod Sihirbazı) `DoDataExchange` geçersiz kıldığınızda, veri üyesi başına bir DDX işlevine (denetim) bir çağrı belirlersiniz. Her DDX işlevi, `UpdateData` tarafından `DoDataExchange` geçirilen `CDataExchange` bağımsız değişkeni tarafından sağlanan bağlam temelinde her iki yönde nasıl veri alışverişi yapılacağını bilir.

MFC, farklı Exchange türleri için birçok DDX işlevi sağlar. Aşağıdaki örnekte, iki DDX işlevinin ve bir DDV işlevinin çağrıldığı `DoDataExchange` bir geçersiz kılma gösterilmektedir:

[!code-cpp[NVC_MFCControlLadenDialog#49](../mfc/codesnippet/cpp/dialog-data-exchange_1.cpp)]

@No__t_0 ve `DDV_` satırları bir veri haritalardır. Gösterilen örnek DDX ve DDV işlevleri, sırasıyla bir onay kutusu denetimi ve bir düzenleme kutusu denetimi içindir.

Kullanıcı kalıcı iletişim kutusunu iptal ederse, `OnCancel` üye işlevi iletişim kutusunu sonlandırır ve `DoModal` **IDCANCEL**değerini döndürür. Bu durumda, iletişim kutusu ve iletişim kutusu nesnesi arasında veri alışverişi yapılmaz.

## <a name="see-also"></a>Ayrıca bkz.

[İletişim Kutusu Veri Değişimi ve Doğrulaması](../mfc/dialog-data-exchange-and-validation.md)<br/>
[MFC 'de Iletişim kutularıyla çalışma](../mfc/life-cycle-of-a-dialog-box.md)<br/>
[İletişim Verisi Doğrulama](../mfc/dialog-data-validation.md)
