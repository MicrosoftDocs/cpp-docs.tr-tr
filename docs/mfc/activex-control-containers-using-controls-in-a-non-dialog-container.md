---
title: 'ActiveX denetim kapsayıcıları: Bir iletişim kutusu dışındaki kapsayıcılarda denetimleri kullanma'
ms.date: 11/04/2016
helpviewer_keywords:
- Create method [MFC], ActiveX controls
- CreateControl method [MFC]
- ActiveX controls [MFC], creating
- ActiveX control containers [MFC], non-dialog containers
- ActiveX control containers [MFC], inserting controls
ms.assetid: 46f195b0-b8ca-4409-8cca-fbfaf2c9ab9f
ms.openlocfilehash: 70a67a6952d5361177b89e3ba514d7036b5799b6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62394877"
---
# <a name="activex-control-containers-using-controls-in-a-non-dialog-container"></a>ActiveX denetim kapsayıcıları: Bir iletişim kutusu dışındaki kapsayıcılarda denetimleri kullanma

Bazı gibi bir SDI uygulamaları veya MDI uygulaması, bir uygulama penceresinde bir denetim eklemek isteyeceksiniz. **Oluştur** Visual C++ tarafından eklenen sarmalayıcı sınıfının üye işlevinde bir örneğini oluşturabilirsiniz denetimi dinamik olarak bir iletişim kutusu gerek kalmadan.

**Oluştur** üye işlevi aşağıdaki parametrelere sahiptir:

*lpszWindowName*<br/>
Bir işaretçi (varsa) denetimin metin veya resim yazısı özelliğini görüntülenecek metin.

*dwStyle*<br/>
Windows stilleri. Tam bir listesi için bkz. [CWnd::CreateControl](../mfc/reference/cwnd-class.md#createcontrol).

*Rect*<br/>
Denetimin boyutunu ve konumunu belirtir.

*pParentWnd*<br/>
Denetiminin üst penceresine, genellikle belirtir bir `CDialog`. Değil olmalıdır **NULL**.

*nID*<br/>
Denetim Kimliği belirtir ve kapsayıcı tarafından denetime başvurmak için kullanılabilir.

ActiveX denetimi dinamik olarak oluşturmak için bu işlevi kullanarak bir örnek, bir SDI uygulaması form görünümünde olacaktır. Daha sonra denetimi örneği oluşturabilirsiniz `WM_CREATE` uygulamasının işleyicisi.

Bu örnekte, `CMyView` ana görünüm sınıfı `CCirc` CIRC. ve sarmalayıcı sınıfı H ise üst bilgisi (. H) dosyası sarmalayıcı sınıf.

Bu özelliği uygulamak dört adımlık bir işlemdir.

### <a name="to-dynamically-create-an-activex-control-in-a-non-dialog-window"></a>Dinamik olarak bir iletişim kutusu dışındaki penceresinde bir ActiveX denetimi oluşturmak için

1. CIRC. Ekle CMYVIEW H. H, hemen önce `CMyView` sınıf tanımını:

   [!code-cpp[NVC_MFC_AxCont#12](../mfc/codesnippet/cpp/activex-control-containers-using-controls-in-a-non-dialog-container_1.h)]

1. Üye değişkeni ekleme (tür `CCirc`) korumalı bölümüne `CMyView` sınıf tanımını CMYVIEW içinde bulunur. Y:

   [!code-cpp[NVC_MFC_AxCont#13](../mfc/codesnippet/cpp/activex-control-containers-using-controls-in-a-non-dialog-container_2.h)]
    [!code-cpp[NVC_MFC_AxCont#14](../mfc/codesnippet/cpp/activex-control-containers-using-controls-in-a-non-dialog-container_3.h)]

1. Ekleme bir `WM_CREATE` sınıfı için ileti işleyicisi `CMyView`.

1. İşleyici işlevindeki `CMyView::OnCreate`, denetimin çağrı yapmak `Create` kullanarak bu işlevi **bu** işaretçi üst pencere olarak:

   [!code-cpp[NVC_MFC_AxCont#15](../mfc/codesnippet/cpp/activex-control-containers-using-controls-in-a-non-dialog-container_4.cpp)]

1. Projeyi yeniden derleyin. Uygulamanın görünümü oluşturulduğunda Dai denetimi dinamik olarak oluşturulur.

## <a name="see-also"></a>Ayrıca bkz.

[ActiveX Denetim Kapsayıcıları](../mfc/activex-control-containers.md)
