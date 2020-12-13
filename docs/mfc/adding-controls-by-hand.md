---
description: 'Hakkında daha fazla bilgi edinin: El Ile denetim ekleme'
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
ms.openlocfilehash: f6dfa65baa037aa168697aa7abcd3eedc76cc4d2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339088"
---
# <a name="adding-controls-by-hand"></a>El İle Denetim Ekleme

İletişim [kutusuna iletişim kutusu Düzenleyicisi ile denetim ekleyebilir](using-the-dialog-editor-to-add-controls.md) veya bunları kod ile kendiniz ekleyebilirsiniz.

Kendi kendinize bir denetim nesnesi oluşturmak için genellikle c++ denetim nesnesini bir C++ iletişim kutusuna veya çerçeve pencere nesnesine gömebilirsiniz. Çerçevede birçok diğer nesne gibi, denetimler iki aşamalı oluşturma gerektirir. Üst iletişim kutusu veya çerçeve penceresi oluşturma işlemi kapsamında denetimin üye **Oluştur** işlevini çağırmanız gerekir. İletişim kutuları için, bu genellikle [OnInitDialog](reference/cdialog-class.md#oninitdialog)ve frame pencereleri Için [OnCreate](reference/cwnd-class.md#oncreate)içinde yapılır.

Aşağıdaki örnek, `CEdit` türetilmiş bir iletişim sınıfının sınıf bildiriminde bir nesne bildirme ve sonra `Create` içinde üye işlevini çağırma işlemlerinin nasıl yapılacağını gösterir `OnInitDialog` . `CEdit`Nesne gömülü bir nesne olarak bildirildiği için, iletişim kutusu nesnesi oluşturulduğunda otomatik olarak oluşturulur, ancak yine de kendi üye işleviyle başlatılmış olması gerekir `Create` .

[!code-cpp[NVC_MFCControlLadenDialog#1](codesnippet/cpp/adding-controls-by-hand_1.h)]

Aşağıdaki `OnInitDialog` işlev bir dikdörtgen kurar, ardından `Create` Windows düzenleme denetimi oluşturmak ve başlatılmamış nesneye iliştirmek için çağırır `CEdit` .

[!code-cpp[NVC_MFCControlLadenDialog#2](codesnippet/cpp/adding-controls-by-hand_2.cpp)]

Düzenleme nesnesini oluşturduktan sonra, üye işlevini çağırarak giriş odağını denetime de ayarlayabilirsiniz `SetFocus` . Son olarak, `OnInitDialog` odağı ayarlatığınızı göstermek için öğesinden 0 döndürün. Sıfır dışında bir değer döndürdüğünüzde, iletişim kutusu Yöneticisi odağı iletişim kutusu öğesi listesindeki ilk denetim öğesine ayarlar. Çoğu durumda, iletişim kutularına iletişim kutusu Düzenleyicisi ile denetim eklemek isteyeceksiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Denetimleri yapma ve kullanma](making-and-using-controls.md)<br/>
[Denetimler](controls-mfc.md)<br/>
[CDialog:: OnInitDialog](reference/cdialog-class.md#oninitdialog)
