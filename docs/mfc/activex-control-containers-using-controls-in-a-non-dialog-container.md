---
title: 'ActiveX denetim kapsayıcıları: İletişim kutusu dışındaki kapsayıcılarda denetimleri kullanma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Create method [MFC], ActiveX controls
- CreateControl method [MFC]
- ActiveX controls [MFC], creating
- ActiveX control containers [MFC], non-dialog containers
- ActiveX control containers [MFC], inserting controls
ms.assetid: 46f195b0-b8ca-4409-8cca-fbfaf2c9ab9f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a20d069024fd424beeec41d3483f8e2c28432e00
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46410734"
---
# <a name="activex-control-containers-using-controls-in-a-non-dialog-container"></a>ActiveX Denetim Kapsayıcıları: İletişim Kutusu Dışındaki Kapsayıcılarda Denetimleri Kullanma

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

## <a name="see-also"></a>Ayrıca Bkz.

[ActiveX Denetim Kapsayıcıları](../mfc/activex-control-containers.md)

