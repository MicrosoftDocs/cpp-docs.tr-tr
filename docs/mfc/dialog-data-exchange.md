---
title: İletişim kutusu veri değişimi
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
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2019
ms.locfileid: "71685811"
---
# <a name="dialog-data-exchange"></a>İletişim kutusu veri değişimi

DDX mekanizmasını kullanırsanız, genellikle `OnInitDialog` işleyicinizde veya iletişim kutusunda, iletişim kutusu nesnesinin üye değişkenlerinin başlangıç değerlerini ayarlarsınız. İletişim kutusu görüntülenmeden hemen önce, Framework 'ün DDX mekanizması, üye değişkenlerinin değerlerini iletişim kutusundaki denetimlere aktarır; burada, iletişim kutusunun kendisi `DoModal` veya `Create` ' e yanıt olarak göründüğünde görüntülenir. @No__t-1 ' deki `OnInitDialog` ' ın varsayılan uygulanması, iletişim kutusundaki denetimleri başlatmak için `CWnd` sınıfının `UpdateData` üye işlevini çağırır.

Aynı mekanizma, Kullanıcı Tamam düğmesine tıkladığında (veya **true**bağımsız değişkeniyle `UpdateData` üye işlevini her çağırdığınızda) denetimleri üye değişkenlerine aktarır. İletişim kutusu veri doğrulama mekanizması, doğrulama kurallarını belirttiğiniz tüm veri öğelerini doğrular.

Aşağıdaki şekilde iletişim kutusu veri değişimi gösterilmektedir.

![İletişim kutusu veri değişimi](../mfc/media/vc379d1.gif "iletişim kutusu veri değişimi") <br/>
İletişim kutusu veri değişimi

`UpdateData`, kendisine geçirilen **bool** parametresi tarafından belirtilen şekilde her iki yönde de işe yarar. Exchange 'i yürütmek için `UpdateData` bir `CDataExchange` nesnesi ayarlar ve iletişim sınıfınızın @no__t 2 `DoDataExchange` üye işlevinin geçersiz kılmasını çağırır. `DoDataExchange` `CDataExchange` türünde bir bağımsız değişken alır. @No__t-1 ' e geçirilen `CDataExchange` nesnesi, Exchange 'in yönü olarak bu tür bilgileri tanımlayarak Exchange bağlamını temsil eder.

(Veya bir kod Sihirbazı) geçersiz kıldığınızda `DoDataExchange`, veri üyesi başına bir DDX işlevine çağrı (denetim) belirtirsiniz. Her DDX işlevi, `UpdateData` ' ye kadar `DoDataExchange` ' e geçirilen `CDataExchange` bağımsız değişkeni tarafından sağlanan bağlam temelinde her iki yönde nasıl veri alışverişi yapılacağını bilir.

MFC, farklı Exchange türleri için birçok DDX işlevi sağlar. Aşağıdaki örnek, iki DDX işlevinin ve bir DDV işlevinin çağrıldığı `DoDataExchange` geçersiz kılmayı gösterir:

[!code-cpp[NVC_MFCControlLadenDialog#49](../mfc/codesnippet/cpp/dialog-data-exchange_1.cpp)]

@No__t-0 ve `DDV_` satırları bir veri eşlemedir. Gösterilen örnek DDX ve DDV işlevleri, sırasıyla bir onay kutusu denetimi ve bir düzenleme kutusu denetimi içindir.

Kullanıcı kalıcı iletişim kutusunu iptal ederse, `OnCancel` üye işlevi iletişim kutusunu sonlandırır ve `DoModal`, **IDCANCEL**değerini döndürür. Bu durumda, iletişim kutusu ve iletişim kutusu nesnesi arasında veri alışverişi yapılmaz.

## <a name="see-also"></a>Ayrıca bkz.

[İletişim kutusu veri değişimi ve doğrulaması](../mfc/dialog-data-exchange-and-validation.md)<br/>
[MFC 'de Iletişim kutularıyla çalışma](../mfc/life-cycle-of-a-dialog-box.md)<br/>
[İletişim kutusu verileri doğrulaması](../mfc/dialog-data-validation.md)
