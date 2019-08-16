---
title: Ağaç Denetimi Etiketini Düzenleme
ms.date: 11/04/2016
helpviewer_keywords:
- editing tree control labels
- CTreeCtrl class [MFC], editing labels
- label editing in CTreeCtrl class [MFC]
- tree controls [MFC], label editing
ms.assetid: 6cde2ac3-43ee-468f-bac2-cf1a228ad32d
ms.openlocfilehash: 10148ef0dd8ccb2cf82c14c1c80ade6e8e5aa2b2
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69513318"
---
# <a name="tree-control-label-editing"></a>Ağaç Denetimi Etiketini Düzenleme

Kullanıcı, **TVS_EDITLABELS** stiline sahip bir ağaç denetimindeki ([ctreeci](../mfc/reference/ctreectrl-class.md)) öğelerin etiketlerini doğrudan düzenleyebilir. Kullanıcı, odağa sahip olan öğenin etiketine tıklayarak düzenlemeyle çalışmaya başlar. Bir uygulama [EditLabel](../mfc/reference/ctreectrl-class.md#editlabel) üye işlevini kullanarak düzenlemeyle çalışmaya başlar. Ağaç denetimi, düzenlenmek başladığında ve iptal edildiğinde veya tamamlandığında bildirim gönderir. Düzen tamamlandığında, uygunsa öğenin etiketini güncelleştirmekten siz sorumlusunuz.

Etiket düzenlemesi başladığında bir ağaç denetimi bir [TVN_BEGINLABELEDIT](/windows/win32/Controls/tvn-beginlabeledit) bildirim iletisi gönderir. Bu bildirimi işleyerek bazı etiketlerin düzenlenmesine ve diğerlerinin düzenlenmesine izin verebilirsiniz. 0 döndürülmesinin düzenlenmesine izin verir ve sıfır dışında döndürme bunu önler.

Etiket düzenlemesi iptal edildiğinde veya tamamlandığında, bir ağaç denetimi bir [TVN_ENDLABELEDIT](/windows/win32/Controls/tvn-endlabeledit) bildirim iletisi gönderir. *LParam* parametresi bir [Nmtvdispınfo](/windows/win32/api/commctrl/ns-commctrl-tvdispinfow) yapısının adresidir. **Öğe** üyesi, öğeyi tanımlayan ve düzenlenen metni Içeren bir [tvidıtem](/windows/win32/api/commctrl/ns-commctrl-tvitemw) yapısıdır. Öğe etiketini güncelleştirmeden, belki de düzenlenmiş dize doğrulandıktan sonra sorumlusunuz. Eğer düzenlenmediğinde, *pszText* üyesi `TV_ITEM` 0 ' dır.

Etiket düzenleme sırasında, genellikle [TVN_BEGINLABELEDIT](/windows/win32/Controls/tvn-beginlabeledit) bildirim iletisine yanıt olarak, [GetEditControl](../mfc/reference/ctreectrl-class.md#geteditcontrol) üye işlevini kullanarak etiket düzenleme için kullanılan düzenleme denetimine yönelik bir işaretçi alabilirsiniz. Bir kullanıcının düzenleme denetimine girebileceği veya onu geçersiz karakterlerle atlayabilmesi için düzenleme denetiminin [SetLimitText](../mfc/reference/cedit-class.md#setlimittext) üye işlevini çağırabilirsiniz. Ancak, düzenleme denetiminin yalnızca **TVN_BEGINLABELEDIT** gönderildikten *sonra* görüntülendiğini unutmayın.

## <a name="see-also"></a>Ayrıca bkz.

[CTreeCtrl Kullanma](../mfc/using-ctreectrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
