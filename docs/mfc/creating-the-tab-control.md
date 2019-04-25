---
title: Sekme Denetimi Oluşturma
ms.date: 11/04/2016
f1_keywords:
- TCS_EX_REGISTERDROP
- TCS_EX_FLATSEPARATORS
helpviewer_keywords:
- TCS_EX_REGISTERDROP extended style [MFC]
- tab controls [MFC], creating
- CTabCtrl class [MFC], creating
- TCS_EX_FLATSEPARATORS extended style
ms.assetid: 3a9c2d64-f5f4-41ea-84ab-fceb73c3dbdc
ms.openlocfilehash: 4627009e2e07d1c5692d83d8d6262a9fcd37977e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62241968"
---
# <a name="creating-the-tab-control"></a>Sekme Denetimi Oluşturma

Sekme denetiminin nasıl oluşturulduğunu denetimi bir iletişim kutusunu kullanarak veya bir nondialog penceresinde oluşturma bağlıdır.

### <a name="to-use-ctabctrl-directly-in-a-dialog-box"></a>CTabCtrl doğrudan iletişim kutusunda kullanmak için

1. İletişim kutusu Düzenleyicisi'nde iletişim şablonu kaynağınıza Sekme denetimine ekleyin. Denetim kimliğini belirtin

1. Kullanım [üye değişkeni Ekleme Sihirbazı'nı](../ide/adding-a-member-variable-visual-cpp.md) türündeki üye değişkeni eklemek için [CTabCtrl](../mfc/reference/ctabctrl-class.md) denetimi özelliğine sahip. Bu üye çağırmak için kullanabileceğiniz `CTabCtrl` üye işlevleri.

1. İşleyici işlevleri işlemeniz gereken sekme denetimi bildirim iletileri için iletişim kutusu sınıfında eşleyin. Daha fazla bilgi için [iletileri işlevlere eşleme](../mfc/reference/mapping-messages-to-functions.md).

1. İçinde [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog), stillerini ayarlama `CTabCtrl`.

### <a name="to-use-ctabctrl-in-a-nondialog-window"></a>CTabCtrl nondialog penceresinde kullanmak için

1. Denetim görünüm veya pencere sınıfı tanımlayın.

1. Denetimin çağrı [Oluştur](../mfc/reference/ctabctrl-class.md#create) üye işlev, büyük olasılıkla buna [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate), büyük olasılıkla, ana pencerenin olabildiğince erken [OnCreate](../mfc/reference/cwnd-class.md#oncreate) (kullanıcısıysanız işleyici işlevi denetimini alt sınıf yapma). Denetimi için stiller ayarlayın.

Sonra `CTabCtrl` nesnesi oluşturuldu, ayarlama veya genişletilmiş stiller aşağıdaki temizleyin:

- **TCS_EX_FLATSEPARATORS** sekme denetimi ayırıcıları arasında sekme öğeleri çizer. Sahip denetimlerini etkiler sekmesinde yalnızca bu genişletilmiş stili **TCS_BUTTONS** ve **TCS_FLATBUTTONS** stilleri. Sekme denetimi ile varsayılan olarak, oluşturma **TCS_FLATBUTTONS** stilini ayarlar bu genişletilmiş stili.

- **TCS_EX_REGISTERDROP** sekme denetimi oluşturur **TCN_GETOBJECT** bildirim iletileri bir bırakma hedefi istemek için bir nesne denetimin sekme öğeler üzerinden sürüklendiğinde nesne.

    > [!NOTE]
    >  Almaya **TCN_GETOBJECT** bildirimi çağrısıyla OLE kitaplıklarının başlatmak gerekir [Afxoleınit](../mfc/reference/ole-initialization.md#afxoleinit).

Bu stiller alınır ve ayarlama, Denetim, ilgili çağrılarıyla oluşturulduktan sonra [GetExtendedStyle](../mfc/reference/ctabctrl-class.md#getextendedstyle) ve [SetExtendedStyle](../mfc/reference/ctabctrl-class.md#setextendedstyle) üye işlevleri.

Örneğin, ayarlayın **TCS_EX_FLATSEPARATORS** aşağıdaki kod satırlarını stili:

[!code-cpp[NVC_MFCControlLadenDialog#33](../mfc/codesnippet/cpp/creating-the-tab-control_1.cpp)]

NET **TCS_EX_FLATSEPARATORS** gelen stili bir `CTabCtrl` aşağıdaki kod satırlarını nesnesiyle:

[!code-cpp[NVC_MFCControlLadenDialog#34](../mfc/codesnippet/cpp/creating-the-tab-control_2.cpp)]

Bu düğmeler arasında görünür ayırıcılar kaldırır, `CTabCtrl` nesne.

## <a name="see-also"></a>Ayrıca bkz.

[CTabCtrl Kullanma](../mfc/using-ctabctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
