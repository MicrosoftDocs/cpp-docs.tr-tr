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
ms.openlocfilehash: 6d5aa6873966ecb4c845f1c503b24c07b6c0c7a3
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84619616"
---
# <a name="creating-the-tab-control"></a>Sekme Denetimi Oluşturma

Sekme denetiminin nasıl oluşturulduğu, denetimi bir iletişim kutusunda kullanıp kullanmayacağınızı veya iletişim kutusu olmayan bir pencerede oluşturmayı gösterir.

### <a name="to-use-ctabctrl-directly-in-a-dialog-box"></a>CTabCtrl ' i doğrudan bir iletişim kutusunda kullanmak için

1. İletişim kutusu düzenleyicisinde iletişim kutusu şablonu kaynağına bir sekme denetimi ekleyin. Denetim KIMLIĞINI belirtin.

1. Denetim özelliğiyle [CTabCtrl](reference/ctabctrl-class.md) türünde bir üye değişkeni eklemek Için [üye değişkeni Ekleme Sihirbazı](../ide/adding-a-member-variable-visual-cpp.md) ' nı kullanın. Bu üyeyi, üye işlevlerini çağırmak için kullanabilirsiniz `CTabCtrl` .

1. İşlemek için gerekli olan herhangi bir sekme denetimi bildirim iletisi için İletişim sınıfındaki işleyici işlevlerini eşleştirin. Daha fazla bilgi için bkz. [Iletileri IŞLEVLERE eşleme](reference/mapping-messages-to-functions.md).

1. [OnInitDialog](reference/cdialog-class.md#oninitdialog)' da, için stilleri ayarlayın `CTabCtrl` .

### <a name="to-use-ctabctrl-in-a-nondialog-window"></a>İletişim kutusu olmayan bir pencerede CTabCtrl kullanma

1. Görünümü veya pencere sınıfında denetimi tanımlayın.

1. Denetimin üye [Oluştur](reference/ctabctrl-class.md#create) işlevini, büyük olasılıkla üst pencerenin [OnCreate](reference/cwnd-class.md#oncreate) Handler işlevi (denetim Altsınıflama kullanıyorsanız) olarak [OnInitialUpdate](reference/cview-class.md#oninitialupdate)içinde çağırın. Denetimin stillerini ayarlayın.

`CTabCtrl`Nesne oluşturulduktan sonra, aşağıdaki genişletilmiş stilleri ayarlayabilir veya temizleyebilirsiniz:

- **TCS_EX_FLATSEPARATORS** Sekme denetimi, sekme öğeleri arasında ayırıcılar çizecek. Bu genişletilmiş stil yalnızca **TCS_BUTTONS** ve **TCS_FLATBUTTONS** stilleri olan sekme denetimlerini etkiler. Varsayılan olarak, **TCS_FLATBUTTONS** stili ile sekme denetiminin oluşturulması bu genişletilmiş stili belirler.

- **TCS_EX_REGISTERDROP** Sekme denetimi, bir nesne denetimdeki sekme öğelerinin üzerine sürüklendiğinde bir bırakma hedefi nesnesi istemek için **TCN_GETOBJECT** bildirim iletileri oluşturur.

    > [!NOTE]
    >  **TCN_GETOBJECT** bildirimi almak IÇIN, OLE kitaplıklarını [AfxOleInit](reference/ole-initialization.md#afxoleinit)çağrısıyla başlatmalısınız.

Bu stiller, Denetim oluşturulduktan sonra, [Getil dedstyle](reference/ctabctrl-class.md#getextendedstyle) ve [Setil dedstyle](reference/ctabctrl-class.md#setextendedstyle) üye işlevlerine yapılan çağrılar ile alınabilir ve ayarlanabilir.

Örneğin, **TCS_EX_FLATSEPARATORS** stilini aşağıdaki kod satırlarıyla ayarlayın:

[!code-cpp[NVC_MFCControlLadenDialog#33](codesnippet/cpp/creating-the-tab-control_1.cpp)]

**TCS_EX_FLATSEPARATORS** `CTabCtrl` Aşağıdaki kod satırlarına sahip bir nesneden TCS_EX_FLATSEPARATORS stilini temizleyin:

[!code-cpp[NVC_MFCControlLadenDialog#34](codesnippet/cpp/creating-the-tab-control_2.cpp)]

Bu işlem, nesnenizin düğmeleri arasında görünen ayırıcıları kaldırır `CTabCtrl` .

## <a name="see-also"></a>Ayrıca bkz.

[CTabCtrl Kullanma](using-ctabctrl.md)<br/>
[Denetimler](controls-mfc.md)
