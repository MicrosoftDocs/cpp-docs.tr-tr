---
title: Üst bilgi öğesi&#39;görünümünü özelleştirme
ms.date: 11/04/2016
helpviewer_keywords:
- header controls [MFC], customization of items
- CHeaderCtrl class [MFC], customizing the items
- HDS_ styles
ms.assetid: b1e1e326-ec7d-4dbd-a46f-96a3e2055618
ms.openlocfilehash: 8bf1bdad6a0408746b50b6b0dcbecbce308f5ede
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84617084"
---
# <a name="customizing-the-header-item39s-appearance"></a>Üst bilgi öğesi&#39;görünümünü özelleştirme

İlk olarak bir üst bilgi denetimi oluştururken *dwStyle* parametresini ayarlayarak ([CHeaderCtrl:: Create](reference/cheaderctrl-class.md#create)), üst bilgi öğelerinin veya üst bilgi denetiminin görünümünü ve davranışını tanımlayabilirsiniz.

Ayarlayabileceğiniz stillerin bir örneklemesini ve amaçlarını aşağıda bulabilirsiniz:

- Bir üst bilgi öğesinin basma gibi görünmesini sağlamak için **HDS_BUTTONS** stilini kullanın.

   Verileri belirli bir sütuna göre sıralama, Microsoft Outlook 'ta yapıldığı gibi, bir üst bilgi öğesinde fare tıklamalarına yanıt olarak uygulamak istiyorsanız bu stili kullanın.

- Üst bilgi öğelerine fare imleci üzerinden geçtiğinde bir "sık izleme" görünümü vermek için **HDS_HOTTRACK** stilini kullanın.

   Etkin izleme, işaretçinin Aksi halde düz bir çubukta bir öğe üzerinden geçtiği bir 3B ana hat görüntüler.

- Üst bilgi denetiminin gizlenmesi gerektiğini göstermek için **HDS_HIDDEN** stilini kullanın.

   **HDS_HIDDEN** stili, üst bilgi denetiminin bir görsel denetim değil, veri kapsayıcısı olarak kullanılması amaçlandığını gösterir. Bu stil, denetimi otomatik olarak gizlemez, ancak bunun yerine davranışını etkiler `CHeaderCtrl::Layout` . Yapının *Cy* üyesinde döndürülen değer, `WINDOWPOS` denetimin kullanıcıya görünür olmaması gerektiğini belirten sıfır olacaktır.

Bu özellikler hakkında daha fazla bilgi için Windows SDK [öğeler](/windows/win32/Controls/header-controls) bölümüne bakın. Üst bilgi denetimine öğe ekleme hakkında daha fazla bilgi için bkz. [üst bilgi denetimine öğe ekleme](adding-items-to-the-header-control.md).

## <a name="see-also"></a>Ayrıca bkz.

[CHeaderCtrl Kullanma](using-cheaderctrl.md)<br/>
[Denetimler](controls-mfc.md)
