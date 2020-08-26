---
title: ToolBar Denetim Stilleri
ms.date: 11/04/2016
helpviewer_keywords:
- ToolBar control styles [MFC]
ms.assetid: 0f717eb9-fa32-4263-b852-809238863feb
ms.openlocfilehash: eab4dbde68fcebdb0afd0d058b4678c464874c81
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88837131"
---
# <a name="toolbar-control-styles"></a>ToolBar Denetim Stilleri

[CMFCToolBarButton sınıfı](../../mfc/reference/cmfctoolbarbutton-class.md) , düğmenin görünümünü ve davranışını tespit eden bir stil bayrakları kümesine sahiptir. Bu bayrakların bir bileşimini [CMFCToolBarButton:: SetStyle](../../mfc/reference/cmfctoolbarbutton-class.md#setstyle)çağırarak ayarlayabilirsiniz. Bu konu stili bayrak değerlerini ve bunların anlamlarını listeler.

## <a name="property-values"></a>Özellik Değerleri

Aşağıdaki değerler, denetimin gösterdiği düğme türünü belirtir:

|Ad|Açıklama|
|-|-|
|TBBS_BUTTON|Standart basma düğmesi (varsayılan).  |
|TBBS_CHECKBOX|Onay kutusu.  |
|TBBS_CHECKGROUP|Bir onay kutusu grubunun başlangıcı.  |
|TBBS_GROUP|Düğme grubunun başlangıcı.  |
|TBBS_SEPARATOR|Ayırıcı.  |

Aşağıdaki değerler denetimin geçerli durumunu temsil eder:

|Ad|Açıklama|
|-|-|
|TBBS_CHECKED|Onay kutusu işaretli.  |
|TBBS_DISABLED|Denetim devre dışı bırakıldı.  |
|TBBS_INDETERMINATE|Onay kutusu belirsiz bir durumda.  |
|TBBS_PRESSED|Düğmesine basıldığında.  |

Aşağıdaki değer, araç çubuğundaki düğmenin yerleşimini değiştirir:

|Ad|Açıklama|
|-|-|
|TBBS_BREAK|Öğeyi yeni bir satıra veya sütunları ayırmadan yeni bir sütuna koyar.  |

## <a name="remarks"></a>Açıklamalar

Geçerli stil [CMFCToolBarButton:: m_nStyle](../../mfc/reference/cmfctoolbarbutton-class.md#m_nstyle)içinde depolanır. `m_nStyle`Bazı türetilmiş sınıflar, ' i çağırdığınızda ek işleme yaptığından, doğrudan ' de yeni bir değer ayarlamayın `SetStyles` .

Görsel yönetici her durumdaki düğmelerin görünümünü belirler. Daha fazla bilgi için bkz. [görselleştirme Yöneticisi](../../mfc/visualization-manager.md) .

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxtoolbarbutton. h

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve genel öğeler](../../mfc/reference/mfc-macros-and-globals.md)<br/>
[CMFCToolBarButton sınıfı](../../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[Görselleştirme Yöneticisi](../../mfc/visualization-manager.md)
