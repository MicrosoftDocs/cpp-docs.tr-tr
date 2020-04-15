---
title: Üstbilgi Kontrolü ve Liste Kontrolü
ms.date: 11/04/2016
helpviewer_keywords:
- CListCtrl class [MFC], with CHeaderCtrl
- CListCtrl class [MFC], header controls
- CHeaderCtrl class [MFC], with CListCtrl
- controls [MFC], header
- header controls [MFC]
- header controls [MFC], list controls used with
ms.assetid: b20194b1-1a6b-4e2f-b890-1b3cca6650bc
ms.openlocfilehash: 53dd6f1a7878d82a7f7ac48dd7082d791323941b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370466"
---
# <a name="header-control-and-list-control"></a>Üstbilgi Kontrolü ve Liste Kontrolü

Çoğu durumda, [clistctrl](../mfc/reference/clistctrl-class.md) veya [CListView](../mfc/reference/clistview-class.md) nesnesine katıştırılmış üstbilgi denetimini kullanırsınız. Ancak, [CView](../mfc/reference/cview-class.md)türetilmiş bir nesnede, sütunlarda veya satırlarda düzenlenmiş verileri işlemek gibi ayrı bir üstbilgi denetim nesnesi gibi arzu edilen durumlar vardır. Bu gibi durumlarda, katıştırılmış üstbilgi denetiminin görünümü ve varsayılan davranışı üzerinde daha fazla denetime ihtiyacınız var.

Standart, varsayılan davranış sağlamak için bir üstbilgi denetimi istediğiniz yaygın durumda, bunun yerine [CListCtrl](../mfc/reference/clistctrl-class.md) veya [CListView](../mfc/reference/clistview-class.md) kullanmak isteyebilirsiniz. Bir `CListCtrl` liste görünümü ortak denetimine katıştırılmış varsayılan üstbilgi denetiminin işlevselliğini istediğinizde kullanın. Bir görünüm nesnesine katıştırılmış varsayılan üstbilgi denetiminin işlevselliğini istediğinizde [CListView'i](../mfc/reference/clistview-class.md) kullanın.

> [!NOTE]
> Bu denetimler yalnızca liste görünümü denetimi **LVS_REPORT** stili kullanılarak oluşturulursa yerleşik üstbilgi denetimini içerir.

Çoğu durumda, katıştırılmış üstbilgi denetiminin görünümü, içeren liste görünümü denetiminin stilleri değiştirilerek değiştirilebilir. Buna ek olarak, üstbilgi denetimi hakkında bilgi üst liste görünümü denetiminin üye işlevleri aracılığıyla elde edilebilir. Ancak, katıştırılmış üstbilgi denetiminin özniteliklerine ve stillerine tam denetim ve erişim için üstbilgi denetim nesnesine bir işaretçi alınması önerilir.

Katıştırılmış üstbilgi denetim nesnesine, `CListView` ilgili sınıfın `GetHeaderCtrl` üye işlevine yapılan bir çağrıyla `CListCtrl` veya bu nesneden erişilebilir. Aşağıdaki kod bunu göstermektedir:

[!code-cpp[NVC_MFCControlLadenDialog#14](../mfc/codesnippet/cpp/header-control-and-list-control_1.cpp)]

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilmek istiyorum

- [Resim listelerini üstbilgi denetimleriyle kullanma](../mfc/using-image-lists-with-header-controls.md)

## <a name="see-also"></a>Ayrıca bkz.

[CHeaderCtrl Kullanma](../mfc/using-cheaderctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
