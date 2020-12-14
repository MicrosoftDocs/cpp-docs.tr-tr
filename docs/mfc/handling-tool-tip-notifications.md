---
description: 'Daha fazla bilgi edinin: Işleme aracı Ipucu bildirimleri'
title: Araç İpucu Bildirimlerini İşleme
ms.date: 11/04/2016
helpviewer_keywords:
- TOOLTIPTEXT structure [MFC]
- CToolBarCtrl class [MFC], handling notifications
- notifications [MFC], tool tips
- tool tips [MFC], notifications
ms.assetid: ddb93b5f-2e4f-4537-8053-3453c86e2bbb
ms.openlocfilehash: 02bb1fb0760cf91c76e3c3be75fe097d5d57b71e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97254865"
---
# <a name="handling-tool-tip-notifications"></a>Araç İpucu Bildirimlerini İşleme

**TBSTYLE_TOOLTIPS** stilini belirttiğinizde araç çubuğu bir araç ipucu denetimi oluşturur ve yönetir. Araç ipucu, bir araç çubuğu düğmesini açıklayan bir metin satırı içeren küçük bir açılır pencere penceresidir. Araç ipucu gizlenir ve yalnızca Kullanıcı imleci bir araç çubuğu düğmesine yerleştirdiği ve yaklaşık bir yarı yarım saniye boyunca bırakdığında görünür. Araç ipucu imlecin yakınında görüntülenir.

Araç ipucu görüntülenmeden önce, düğme için açıklayıcı metni almak üzere araç çubuğunun sahip penceresine **TTN_NEEDTEXT** bildirim iletisi gönderilir. Araç çubuğunun sahip penceresi bir `CFrameWnd` pencere ise, araç ipuçları ek bir çaba olmadan görüntülenir, çünkü `CFrameWnd` **TTN_NEEDTEXT** bildirimi için varsayılan bir işleyici vardır. Araç çubuğunun sahip olduğu pencere `CFrameWnd` , bir iletişim kutusu veya form görünümü gibi öğesinden türetilmişse, sahip pencerenizin ileti eşlemesine bir giriş eklemeniz ve ileti haritasında bir bildirim işleyicisi sağlamanız gerekir. Sahip pencerenizin ileti eşlemesine giriş aşağıdaki gibidir:

[!code-cpp[NVC_MFCControlLadenDialog#40](codesnippet/cpp/handling-tool-tip-notifications_1.cpp)]

## <a name="remarks"></a>Açıklamalar

*memberFxn*<br/>
Bu düğme için metin gerektiğinde çağrılacak üye işlev.

Araç ipucu kimliğinin her zaman 0 olduğunu unutmayın.

**TTN_NEEDTEXT** bildirimine ek olarak, bir araç ipucu denetimi bir araç çubuğu denetimine aşağıdaki bildirimleri gönderebilir:

|Bildirim|Anlamı|
|------------------|-------------|
|**TTN_NEEDTEXTA**|Araç ipucu denetimi ASCII metni gerektiriyor (yalnızca Windows 95)|
|**TTN_NEEDTEXTW**|Araç ipucu denetimi UNICODE metin gerektiriyor (yalnızca Windows NT)|
|**TBN_HOTITEMCHANGE**|Sık kullanılan (vurgulanmış) öğenin değiştiğini gösterir.|
|**NM_RCLICK**|Kullanıcının bir düğmeye sağ tıkladığını gösterir.|
|**TBN_DRAGOUT**|Kullanıcının düğmeye tıkladığını ve işaretçiyi düğmenin dışına sürüklemiş olduğunu gösterir. Bir uygulamanın bir araç çubuğu düğmesinden sürükle ve bırak uygulamasına uygulanmasını sağlar. Bu bildirim alındığında uygulama sürükle ve bırak işlemini başlatır.|
|**TBN_DROPDOWN**|Kullanıcının **TBSTYLE_DROPDOWN** stilini kullanan bir düğmeye tıkladığını gösterir.|
|**TBN_GETOBJECT**|Kullanıcının işaretçiyi **TBSTYLE_DROPPABLE** stilini kullanan bir düğmenin üzerine taşındığını gösterir.|

Örnek işleyici işlevi ve araç ipuçlarını etkinleştirme hakkında daha fazla bilgi için bkz. [araç ipuçları](tool-tips-in-windows-not-derived-from-cframewnd.md).

## <a name="see-also"></a>Ayrıca bkz.

[CToolBarCtrl Kullanma](using-ctoolbarctrl.md)<br/>
[Denetimler](controls-mfc.md)
