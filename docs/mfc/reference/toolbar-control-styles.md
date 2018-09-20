---
title: ToolBar denetim stilleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- ToolBar control styles [MFC]
ms.assetid: 0f717eb9-fa32-4263-b852-809238863feb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fe31acea49dddf6a1cf76c01de789ccfc8583e04
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46386541"
---
# <a name="toolbar-control-styles"></a>ToolBar Denetim Stilleri

[CMFCToolBarButton sınıfı](../../mfc/reference/cmfctoolbarbutton-class.md) düğmesinin davranışını ve görünümünü belirleyen bayrakları stil kümesi vardır. Bu bayrakların birleşimi çağırarak ayarlayabileceğiniz [CMFCToolBarButton::SetStyle](../../mfc/reference/cmfctoolbarbutton-class.md#setstyle). Bu konu, stil bayrak değerleri ve anlamlarını listeler.

## <a name="property-values"></a>Özellik değerleri

Aşağıdaki değerleri denetimini temsil eden bir düğme türünü belirleyin:

|||
|-|-|
|TBBS_BUTTON|Standart basma düğmesi (varsayılan).  |
|TBBS_CHECKBOX|Onay kutusunu seçin.  |
|TBBS_CHECKGROUP|Onay kutularından oluşan bir grubu başlangıcı.  |
|TBBS_GROUP|Bir grup düğmesi başlangıcı.  |
|TBBS_SEPARATOR|Ayırıcı.  |

Aşağıdaki değerleri denetimi geçerli durumunu temsil eder:

|||
|-|-|
|TBBS_CHECKED|Onay kutusu işaretli.  |
|TBBS_DISABLED|Denetim devre dışıdır.  |
|TBBS_INDETERMINATE|Onay kutusu belirsiz bir durumda.  |
|TBBS_PRESSED|Düğmeye basıldığında.  |

Aşağıdaki değeri, araç çubuğundaki düğmenin düzenini değiştirir:

|||
|-|-|
|TBBS_BREAK|Öğesi, sütun ayırıcı olmadan yeni bir satır veya yeni bir sütun yerleştirir.  |

## <a name="remarks"></a>Açıklamalar

Geçerli stili depolanan [CMFCToolBarButton::m_nStyle](../../mfc/reference/cmfctoolbarbutton-class.md#m_nstyle). Yeni bir değere ayarlamayın `m_nStyle` doğrudan bazı türetilmiş sınıflar çağırdığınızda, ek işleme gerçekleştirdiğinden `SetStyles`.

Görsel yöneticiyi düğmelerin her durumda görünümünü belirler. Bkz: [seri hale getirme Yöneticisi](../../mfc/visualization-manager.md) daha fazla bilgi için.

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxtoolbarbutton.h

## <a name="see-also"></a>Ayrıca Bkz.

[Makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md)<br/>
[CMFCToolBarButton Sınıfı](../../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[Seri Hale Getirme Yöneticisi](../../mfc/visualization-manager.md)


