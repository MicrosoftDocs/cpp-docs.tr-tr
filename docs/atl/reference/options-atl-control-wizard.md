---
title: ATL denetimi Sihirbazı, seçenekleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.codewiz.class.atl.control.options
dev_langs:
- C++
helpviewer_keywords:
- ATL Control Wizard, options
ms.assetid: 4607c51a-992d-433e-9281-919c6f519a3d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9c1acf9602dedf0eef1b8d96344914c367ce5926
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50073558"
---
# <a name="options-atl-control-wizard"></a>ATL denetimi Sihirbazı, Seçenekler

"Arama sonuçları" Özet buraya ekleyin.

Sihirbazın bu sayfası, oluşturmakta olduğunuz denetim türünü ve içerdiği arabirimi destek düzeyini tanımlamak için kullanın.

## <a name="uielement-list"></a>UIElement Listesi

### <a name="control-type"></a>Denetim türü

Oluşturmak istediğiniz denetim türü.

- **Standart denetim**: bir ActiveX denetimi.

- **Bileşik Denetim**: (iletişim kutusuna benzer) içeren bir ActiveX denetimi diğer ActiveX denetimleri veya Windows denetimleri. Bileşik Denetim şunları içerir:

   - Bileşik Denetim uygulayan iletişim kutusu için bir şablon.

   - Özel kaynak, kayıt defteri bileşik denetim çağrıldığında otomatik olarak kaydeder.

   - Bileşik Denetim uygulayan bir C++ sınıf.

   - Bileşik denetim tarafından kullanıma sunulan bir COM arabirimi.

   - Bileşik Denetim içeren bir HTML test sayfası.

   Varsayılan olarak, bu denetim ayarlar [CComControlBase::m_bWindowOnly](../../atl/reference/ccomcontrolbase-class.md#m_bwindowonly) kadar pencereli denetimin olduğunu belirtmek için true. Bir havuz eşleme uygular. Daha fazla bilgi için [DHTML denetimi desteği](../../atl/atl-support-for-dhtml-controls.md).

- **DHTML denetimi**: HTML kullanarak kullanıcı arabirimi, bir ATL DHTML denetimini belirtir. DHTML kullanıcı Arabirimi sınıfı bir COM eşlemesi içerir. Varsayılan olarak, bu denetim ayarlar [CComControlBase::m_bWindowOnly](../../atl/reference/ccomcontrolbase-class.md#m_bwindowonly) kadar pencereli denetimin olduğunu belirtmek için true.

   Daha fazla bilgi için [DHTML denetim projesinin öğelerini tanımlama](../../atl/identifying-the-elements-of-the-dhtml-control-project.md).

### <a name="minimal-control"></a>En az denetim

Çoğu kapsayıcı tarafından kesinlikle gerekli arabirimleri destekler. Ayarlayabileceğiniz **en az bir denetim** herhangi bir denetim türü için: en az standart bir denetimde, en az bir bileşik denetim veya en az bir DHTML denetimi oluşturabilirsiniz.

### <a name="aggregation"></a>Toplama

Oluşturmakta olduğunuz Denetim toplama desteği ekler. Daha fazla bilgi için [toplama](../../atl/aggregation.md).

- **Evet**: toplanabilir bir denetim oluşturursunuz.

- **Hayır**: toplanamaz bir denetim oluşturursunuz.

- **Yalnızca**: yalnızca toplama oluşturulan bir denetim oluşturursunuz.

### <a name="threading-model"></a>İş parçacığı modeli

İş parçacığı modeli denetim tarafından kullanılan belirtir.

- **Tek**: denetim, yalnızca birincil COM iş parçacığında çalışır.

- **Apartman**: denetimin herhangi tek iş parçacığı grubu oluşturulabilir. Varsayılan.

### <a name="interface"></a>Arabirim

Arabirim türü bu denetim için kapsayıcı gösterir.

- **Çift**: özellikler ve yöntemler aracılığıyla kullanıma sunduğu bir arabirim oluşturur `IDispatch` ve doğrudan VTBL.

- **Özel**: doğrudan bir VTBL aracılığıyla yöntemlerini gösteren bir arabirim oluşturur.

   Seçerseniz **özel**, denetimin olduğunu belirtin ve **otomasyon uyumlu**. Seçerseniz **otomasyon uyumlu**, sihirbaz ekler sonra [oleautomation](../../windows/oleautomation.md) IDL arabiriminde özniteliği ve arabirimi oleaut32.dll, Evrensel sıralayıcı tarafından sıralanabilir. Bkz: [hazırlama ayrıntıları](/windows/desktop/com/marshaling-details) daha fazla bilgi için Windows SDK.

   Ayrıca, seçerseniz **otomasyon uyumlu**, denetimdeki tüm yöntemler için tüm parametreleri VARYANT olmalıdır uyumlu.

### <a name="support"></a>Destek

Ek çeşitli destek denetimi için ayarlar.

- **Bağlantı noktaları**: nesneniz için bağlantı noktaları sağlar, nesnenin sınıfı türetilen yaparak [Iconnectionpointcontainerımpl](../../atl/reference/iconnectionpointcontainerimpl-class.md) ve bir kaynak arabirimi kullanıma izin veren.

- **Lisanslı**: denetim için destek ekler [lisanslama](/windows/desktop/com/licensing). Lisanslı Denetimler, yalnızca istemci makinede doğru lisansa varsa barındırılabilir.

## <a name="see-also"></a>Ayrıca Bkz.

[ATL Denetimi Sihirbazı](../../atl/reference/atl-control-wizard.md)

