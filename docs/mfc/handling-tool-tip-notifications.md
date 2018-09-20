---
title: Araç İpucu bildirimlerini işleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- TOOLTIPTEXT structure [MFC]
- CToolBarCtrl class [MFC], handling notifications
- notifications [MFC], tool tips
- tool tips [MFC], notifications
ms.assetid: ddb93b5f-2e4f-4537-8053-3453c86e2bbb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0449877f9894685ea724e3ad00c028e3e57f50d9
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46409765"
---
# <a name="handling-tool-tip-notifications"></a>Araç İpucu Bildirimlerini İşleme

Belirttiğinizde **TBSTYLE_TOOLTIPS** stil, araç oluşturur ve bir araç ipucunu denetimini yönetir. Bir araç ipucu araç çubuğu düğmesi açıklayan metin satırı içeren küçük bir açılır penceredir. Yalnızca kullanıcı bir araç çubuğu düğmesini imleci getirir ve bunu var. ikinci yarısı için yaklaşık bırakır görünen araç ipucu gizlenir. Araç İpucu imlecin yanında görüntülenir.

Araç İpucu görüntülenmeden önce **TTN_NEEDTEXT** düğme için açıklayıcı metni almak için araç çubuğunun sahibi penceresine bildirim iletisi gönderilir. Araç çubuğunun sahibi penceresi olup olmadığını bir `CFrameWnd` penceresinde araç ipuçları, herhangi bir fazladan çaba görüntülenir, çünkü `CFrameWnd` için bir varsayılan işleyici sahip **TTN_NEEDTEXT** bildirim. Araç çubuğunun sahip penceresine türünden türetilmediğinden varsa `CFrameWnd`, bir iletişim kutusu veya form görünümü gibi sahibi pencerenin ileti eşlemesi için bir giriş ekleyin ve gerekir ileti eşlemesi bildirim işleyicisinde sağlayın. Girişe sahip pencerenin ileti eşlemesi aşağıdaki gibidir:

[!code-cpp[NVC_MFCControlLadenDialog#40](../mfc/codesnippet/cpp/handling-tool-tip-notifications_1.cpp)]

## <a name="remarks"></a>Açıklamalar

*memberFxn*<br/>
Bu düğme için metin gerektiğinde çağrılacak üye işlevi.

Bir araç ipucu kimliği her zaman olduğuna dikkat edin 0.

Ek olarak **TTN_NEEDTEXT** bildirim, bir araç ipucunu denetimini gönderebilir aşağıdaki bildirimleri bir toolbar denetimine:

|Bildirim|Açıklama|
|------------------|-------------|
|**TTN_NEEDTEXTA**|Araç ipucunu denetimini ASCII metni (yalnızca Windows 95) gerektirir.|
|**TTN_NEEDTEXTW**|Araç ipucunu denetimini UNICODE metni (yalnızca Windows NT) gerektirir.|
|**TBN_HOTITEMCHANGE**|Sık erişimli vurgulanmış öğe değişmiş olduğunu belirtir.|
|**NM_RCLICK**|Kullanıcı bir düğme sağ gösterir.|
|**TBN_DRAGOUT**|Kullanıcı düğmeye tıkladı ve imleci düğmeden sürüklediğiniz gösterir. Sürükleme uygulamak ve araç çubuğu düğmesinden bırakma bir uygulama sağlar. Bu bildirim alındığında, uygulama başlamadan sürükleme ve bırakma işlemi.|
|**TBN_DROPDOWN**|Kullanıcının kullandığı bir düğmeye tıkladığını belirtir **TBSTYLE_DROPDOWN** stili.|
|**TBN_GETOBJECT**|Kullanıcı kullanan bir düğmenin üzerine işaretçiyi taşınmış gösterir **TBSTYLE_DROPPABLE** stili.|

Bir örnek işleyici işlevi ve araç ipuçlarını etkinleştirme hakkında daha fazla bilgi için bkz: [araç ipuçları](../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md).

## <a name="see-also"></a>Ayrıca Bkz.

[CToolBarCtrl Kullanma](../mfc/using-ctoolbarctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

