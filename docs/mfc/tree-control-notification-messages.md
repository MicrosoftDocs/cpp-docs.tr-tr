---
description: 'Daha fazla bilgi edinin: ağaç denetimi bildirim Iletileri'
title: Ağaç Denetimi Bildirim İletileri
ms.date: 11/04/2016
helpviewer_keywords:
- notifications [MFC], tree controls
- messages [MFC], notification
- CTreeCtrl class [MFC], notifications
- notifications [MFC], CTreeCtrl
- tree controls [MFC], notification messages
ms.assetid: ac7013b4-91dd-4668-bd75-439ca0680ef9
ms.openlocfilehash: 899b6469a2de9a076dd33e62c5023f502448d45f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97263991"
---
# <a name="tree-control-notification-messages"></a>Ağaç Denetimi Bildirim İletileri

Ağaç denetimi ([Ctreeci](../mfc/reference/ctreectrl-class.md)) aşağıdaki bildirim iletilerini WM_NOTIFY iletileri olarak gönderir:

|Bildirim iletisi|Açıklama|
|--------------------------|-----------------|
|TVN_BEGINDRAG|Sürükle ve bırak işleminin başlangıcına bildirir|
|TVN_BEGINLABELEDIT|Yerinde etiket düzenlemesinin başlangıcına bildirir|
|TVN_BEGINRDRAG|Bir sürükle ve bırak işleminin başlangıcını, sağ fare düğmesini kullanarak bildirir|
|TVN_DELETEITEM|Belirli bir öğenin silinmesini bildirir|
|TVN_ENDLABELEDIT|Etiket düzenlemenin sonuna işaret eder|
|TVN_GETDISPINFO|Ağaç denetiminin bir öğeyi görüntülemesi için gereken bilgileri ister|
|TVN_ITEMEXPANDED|Üst öğenin alt öğe listesinin genişletildiğini veya daraltılacağını bildirir|
|TVN_ITEMEXPANDING|Üst öğenin alt öğe listesinin genişletilmekte veya daraltılmak üzere olduğunu bildirir|
|TVN_KEYDOWN|Klavye olayına işaret eder|
|TVN_SELCHANGED|Seçimin bir öğeden diğerine değiştiğini bildirir|
|TVN_SELCHANGING|Seçimin bir öğeden diğerine değiştirilme olduğunu bildirir|
|TVN_SETDISPINFO|Bir öğe için tutulan bilgileri güncelleştirme bildirimi|

## <a name="see-also"></a>Ayrıca bkz.

[CTreeCtrl Kullanma](../mfc/using-ctreectrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
