---
description: 'Hakkında daha fazla bilgi edinin: seçenekler, ATL Denetim Sihirbazı'
title: Seçenekler, ATL Denetim Sihirbazı
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.class.atl.control.options
helpviewer_keywords:
- ATL Control Wizard, options
ms.assetid: 4607c51a-992d-433e-9281-919c6f519a3d
ms.openlocfilehash: 428f6ba1a4bee9cec60ca05b57d66d176c3f0deb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97157899"
---
# <a name="options-atl-control-wizard"></a>Seçenekler, ATL Denetim Sihirbazı

Oluşturmakta olduğunuz denetim türünü ve içerdiği arabirim desteği düzeyini tanımlamak için sihirbazın bu sayfasını kullanın.

## <a name="uielement-list"></a>UIElement Listesi

### <a name="control-type"></a>Denetim türü

Oluşturmak istediğiniz denetim türü.

- **Standart denetim**: ActiveX denetimi.

- **Bileşik denetim**: (iletişim kutusuyla benzer), diğer ActiveX denetimleri veya Windows denetimleri Içerebilen bir ActiveX denetimidir. Bileşik denetim şunları içerir:

  - Bileşik denetimi uygulayan iletişim kutusu için bir şablon.

  - Çağrıldığında bileşik denetimi otomatik olarak kaydeden özel bir kaynak, kayıt DEFTERI.

  - Bileşik denetimi uygulayan bir C++ sınıfı.

  - Bileşik denetim tarafından sunulan bir COM arabirimi.

  - Bileşik denetimi içeren bir HTML test sayfası.

    Varsayılan olarak bu denetim, bu bir pencereli denetim olduğunu göstermek için [CComControlBase:: m_bWindowOnly](../../atl/reference/ccomcontrolbase-class.md#m_bwindowonly) true olarak belirler. Havuz eşlemesini uygular. Daha fazla bilgi için bkz. [DHTML denetimi Için destek](../../atl/atl-support-for-dhtml-controls.md).

- **DHTML denetimi**: atl dhtml denetimi, Kullanıcı arabirimini HTML kullanarak belirtir. DHTML Kullanıcı arabirimi sınıfı bir COM eşlemesi içerir. Varsayılan olarak bu denetim, bu bir pencereli denetim olduğunu göstermek için [CComControlBase:: m_bWindowOnly](../../atl/reference/ccomcontrolbase-class.md#m_bwindowonly) true olarak belirler.

   Daha fazla bilgi için bkz. [DHTML denetim projesinin öğelerini tanımlama](../../atl/identifying-the-elements-of-the-dhtml-control-project.md).

### <a name="minimal-control"></a>En az denetim

Yalnızca çoğu kapsayıcı tarafından kesinlikle gerekli olan arabirimleri destekler. Denetim türlerinden herhangi biri için **en az denetim** ayarlayabilirsiniz: en az bir standart denetim, en az bir bileşik denetim veya en az bir dhtml denetimi oluşturabilirsiniz.

### <a name="aggregation"></a>Toplama

Oluşturmakta olduğunuz denetim için toplama desteği ekler. Daha fazla bilgi için bkz. [toplama](../../atl/aggregation.md).

- **Evet**: toplanabilecek bir denetim oluşturun.

- **Hayır**: toplanmayan bir denetim oluşturun.

- **Yalnızca**: toplama yoluyla örneklenebilir bir denetim oluşturun.

### <a name="threading-model"></a>İş parçacığı modeli

Denetim tarafından kullanılan iş parçacığı modelinin belirtir.

- **Tek**: denetim yalnızca birincil com iş parçacığında çalışır.

- **Apartment**: denetim herhangi bir tek iş parçacığı grubu içinde oluşturulabilir. Varsayılan.

### <a name="interface"></a>Arabirim

Bu denetimin kapsayıcı için sunduğu arabirimin türü.

- **Çift**: doğrudan VTBL aracılığıyla ve aracılığıyla özellikleri ve yöntemleri sunan bir arabirim oluşturur `IDispatch` .

- **Özel**: yöntemleri doğrudan bir VTBL aracılığıyla kullanıma sunan bir arabirim oluşturur.

   **Özel**' i seçerseniz, denetimin **Otomasyon uyumlu** olduğunu belirtebilirsiniz. **Otomasyon uyumluluğu**' nu seçerseniz, SIHIRBAZ, IDL 'deki arabirime [oleautomation](../../windows/attributes/oleautomation.md) özniteliğini ekler ve arabirim oleaut32.dll evrensel sıralayıcı tarafından sıralanabilir. Daha fazla bilgi için Windows SDK [sıralama ayrıntılarına](/windows/win32/com/marshaling-details) bakın.

   Ayrıca, **Otomasyon uyumluluğu**' nu seçerseniz, denetimdeki tüm yöntemler için tüm parametrelerin değişken uyumlu olması gerekir.

### <a name="support"></a>Destek

Denetim için ek çeşitli destek ayarlar.

- **Bağlantı noktaları**: nesnenizin sınıfının [IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md) 'den türemesini ve bir kaynak arabirimini açığa çıkarmasını sağlayarak nesneniz için bağlantı noktaları sağlar.

- **Lisanslı**: [lisanslama](/windows/win32/com/licensing)için denetime destek ekler. Lisanslı denetimler yalnızca istemci makinesinde doğru lisans varsa barındırılabilir.

## <a name="see-also"></a>Ayrıca bkz.

[ATL Denetim Sihirbazı](../../atl/reference/atl-control-wizard.md)
