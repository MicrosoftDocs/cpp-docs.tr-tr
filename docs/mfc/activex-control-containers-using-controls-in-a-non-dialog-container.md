---
title: 'ActiveX Denetim Kapsayıcıları: İletişim Kutusu Dışındaki Kapsayıcılarda Denetimleri Kullanma'
ms.date: 11/04/2016
helpviewer_keywords:
- Create method [MFC], ActiveX controls
- CreateControl method [MFC]
- ActiveX controls [MFC], creating
- ActiveX control containers [MFC], non-dialog containers
- ActiveX control containers [MFC], inserting controls
ms.assetid: 46f195b0-b8ca-4409-8cca-fbfaf2c9ab9f
ms.openlocfilehash: f3f0bc7c89ff2bea1c344f2c876e1624ba82fb87
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87214171"
---
# <a name="activex-control-containers-using-controls-in-a-non-dialog-container"></a>ActiveX Denetim Kapsayıcıları: İletişim Kutusu Dışındaki Kapsayıcılarda Denetimleri Kullanma

SDI veya MDI uygulaması gibi bazı uygulamalarda, uygulamanın bir penceresinde bir denetim eklemek isteyeceksiniz. Sarmalayıcı sınıfının üye **Oluştur** işlevi, Visual C++ tarafından, bir iletişim kutusu gerekmeden, denetimin bir örneğini dinamik bir şekilde oluşturabilir.

**Create** member işlevi aşağıdaki parametrelere sahiptir:

*lpszWindowName*<br/>
Denetimin metin veya başlık özelliğinde (varsa) görüntülenecek metin için bir işaretçi.

*dwStyle*<br/>
Windows stilleri. Tüm liste için bkz. [CWnd:: CreateControl](reference/cwnd-class.md#createcontrol).

*Rect*<br/>
Denetimin boyutunu ve konumunu belirtir.

*pParentWnd*<br/>
Denetimin üst penceresini (genellikle a) belirtir `CDialog` . **Null**olmaması gerekir.

*NID*<br/>
Denetim KIMLIĞINI belirtir ve kapsayıcı tarafından denetime başvurmak için kullanılabilir.

Bir ActiveX denetimi dinamik olarak oluşturmak için bu işlevi kullanmanın bir örneği, SDI uygulamasının form görünümünde olabilir. Daha sonra uygulamanın işleyicisinde denetimin bir örneğini oluşturabilirsiniz `WM_CREATE` .

Bu örnekte, `CMyView` ana görünüm sınıfı, `CCirc` sarmalayıcı sınıfı ve Circ olur. H üst bilgi (. H) sarmalayıcı sınıfının dosyası.

Bu özelliğin uygulanması dört adımlı bir işlemdir.

### <a name="to-dynamically-create-an-activex-control-in-a-non-dialog-window"></a>İletişim kutusu olmayan bir pencerede dinamik olarak ActiveX denetimi oluşturmak için

1. CIRC ekleyin. CMYVIEW içinde H. H, `CMyView` sınıf tanımından hemen önce:

   [!code-cpp[NVC_MFC_AxCont#12](codesnippet/cpp/activex-control-containers-using-controls-in-a-non-dialog-container_1.h)]

1. `CCirc` `CMyView` CMYVIEW içinde bulunan sınıf tanımının korumalı bölümüne üye değişken (türünden) ekleyin. Olsun

   [!code-cpp[NVC_MFC_AxCont#13](codesnippet/cpp/activex-control-containers-using-controls-in-a-non-dialog-container_2.h)]
    [!code-cpp[NVC_MFC_AxCont#14](codesnippet/cpp/activex-control-containers-using-controls-in-a-non-dialog-container_3.h)]

1. Sınıfa bir `WM_CREATE` ileti işleyicisi ekleyin `CMyView` .

1. İşleyici işlevinde, `CMyView::OnCreate` `Create` **`this`** işaretçiyi üst pencere olarak kullanarak denetimin işlevine bir çağrı yapın:

   [!code-cpp[NVC_MFC_AxCont#15](codesnippet/cpp/activex-control-containers-using-controls-in-a-non-dialog-container_4.cpp)]

1. Projeyi yeniden derleyin. Uygulamanın görünümü oluşturulduğunda bir Circ denetimi dinamik olarak oluşturulur.

## <a name="see-also"></a>Ayrıca bkz.

[ActiveX denetim kapsayıcıları](activex-control-containers.md)
