---
title: ATL denetimi Sihirbazı, Seçenekler
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.class.atl.control.options
helpviewer_keywords:
- ATL Control Wizard, options
ms.assetid: 4607c51a-992d-433e-9281-919c6f519a3d
ms.openlocfilehash: 1dd136739162c72d8064deb9b1498794f1985e1b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62197360"
---
# <a name="options-atl-control-wizard"></a>ATL denetimi Sihirbazı, Seçenekler

Sihirbazın bu sayfası, oluşturmakta olduğunuz denetim türünü ve içerdiği arabirimi destek düzeyini tanımlamak için kullanın.

## <a name="uielement-list"></a>UIElement Listesi

### <a name="control-type"></a>Denetim türü

Oluşturmak istediğiniz denetim türü.

- **Standart denetim**: ActiveX denetimi.

- **Bileşik Denetim**: (İletişim kutusuna benzer) içerebilir bir ActiveX denetimini diğer ActiveX denetimleri veya Windows denetimleri. Bileşik Denetim şunları içerir:

  - Bileşik Denetim uygulayan iletişim kutusu için bir şablon.

  - Özel kaynak, kayıt defteri bileşik denetim çağrıldığında otomatik olarak kaydeder.

  - Bileşik Denetim uygulayan bir C++ sınıf.

  - Bileşik denetim tarafından kullanıma sunulan bir COM arabirimi.

  - Bileşik Denetim içeren bir HTML test sayfası.

    Varsayılan olarak, bu denetim ayarlar [CComControlBase::m_bWindowOnly](../../atl/reference/ccomcontrolbase-class.md#m_bwindowonly) kadar pencereli denetimin olduğunu belirtmek için true. Bir havuz eşleme uygular. Daha fazla bilgi için [DHTML denetimi desteği](../../atl/atl-support-for-dhtml-controls.md).

- **DHTML denetimi**: ATL DHTML denetimini kullanarak HTML kullanıcı arabirimi belirtir. DHTML kullanıcı Arabirimi sınıfı bir COM eşlemesi içerir. Varsayılan olarak, bu denetim ayarlar [CComControlBase::m_bWindowOnly](../../atl/reference/ccomcontrolbase-class.md#m_bwindowonly) kadar pencereli denetimin olduğunu belirtmek için true.

   Daha fazla bilgi için [DHTML denetim projesinin öğelerini tanımlama](../../atl/identifying-the-elements-of-the-dhtml-control-project.md).

### <a name="minimal-control"></a>En az denetim

Çoğu kapsayıcı tarafından kesinlikle gerekli arabirimleri destekler. Ayarlayabileceğiniz **en az bir denetim** herhangi bir denetim türü için: en az standart bir denetimde, en az bir bileşik denetim veya en az bir DHTML denetimi oluşturabilirsiniz.

### <a name="aggregation"></a>Toplama

Oluşturmakta olduğunuz Denetim toplama desteği ekler. Daha fazla bilgi için [toplama](../../atl/aggregation.md).

- **Evet**: Toplanabilir bir denetim oluşturursunuz.

- **Hayır**: Toplanamaz bir denetim oluşturursunuz.

- **Yalnızca**: Yalnızca toplama oluşturulan bir denetim oluşturursunuz.

### <a name="threading-model"></a>İş parçacığı modeli

İş parçacığı modeli denetim tarafından kullanılan belirtir.

- **Tek**: Denetim, yalnızca birincil COM iş parçacığında çalışır.

- **Apartman**: Denetimin tüm tek iş parçacığı grubu oluşturulabilir. Varsayılan.

### <a name="interface"></a>Arabirim

Arabirim türü bu denetim için kapsayıcı gösterir.

- **Çift**: Özellikler ve yöntemler aracılığıyla kullanıma sunduğu bir arabirim oluşturur `IDispatch` ve doğrudan VTBL.

- **Özel**: Doğrudan bir VTBL aracılığıyla yöntemlerini gösteren bir arabirim oluşturur.

   Seçerseniz **özel**, denetimin olduğunu belirtin ve **otomasyon uyumlu**. Seçerseniz **otomasyon uyumlu**, sihirbaz ekler sonra [oleautomation](../../windows/oleautomation.md) IDL arabiriminde özniteliği ve arabirimi oleaut32.dll, Evrensel sıralayıcı tarafından sıralanabilir. Bkz: [hazırlama ayrıntıları](/windows/desktop/com/marshaling-details) daha fazla bilgi için Windows SDK.

   Ayrıca, seçerseniz **otomasyon uyumlu**, denetimdeki tüm yöntemler için tüm parametreleri VARYANT olmalıdır uyumlu.

### <a name="support"></a>Destek

Ek çeşitli destek denetimi için ayarlar.

- **Bağlantı noktaları**: Nesneniz için bağlantı noktaları, nesnenin sınıfı türetilen yaparak sağlar [Iconnectionpointcontainerımpl](../../atl/reference/iconnectionpointcontainerimpl-class.md) ve bir kaynak arabirimi kullanıma olanak tanır.

- **Lisanslı**: Denetim için destek ekler [lisanslama](/windows/desktop/com/licensing). Lisanslı Denetimler, yalnızca istemci makinede doğru lisansa varsa barındırılabilir.

## <a name="see-also"></a>Ayrıca bkz.

[ATL Denetimi Sihirbazı](../../atl/reference/atl-control-wizard.md)
