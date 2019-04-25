---
title: Üstbilgi denetimi ve liste denetimi
ms.date: 11/04/2016
helpviewer_keywords:
- CListCtrl class [MFC], with CHeaderCtrl
- CListCtrl class [MFC], header controls
- CHeaderCtrl class [MFC], with CListCtrl
- controls [MFC], header
- header controls [MFC]
- header controls [MFC], list controls used with
ms.assetid: b20194b1-1a6b-4e2f-b890-1b3cca6650bc
ms.openlocfilehash: 934b54de3266138225087d5519af2be51972cf9d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62240081"
---
# <a name="header-control-and-list-control"></a>Üstbilgi denetimi ve liste denetimi

Çoğu durumda, katıştırılmış üstbilgi denetimi kullanacağınız bir [CListCtrl](../mfc/reference/clistctrl-class.md) veya [CListView](../mfc/reference/clistview-class.md) nesne. Ancak, ayrı üstbilgi denetim nesnesi olduğu istenen sütun veya satır içinde düzenlenmiş bir veri düzenleme gibi durumlar vardır bir [CView](../mfc/reference/cview-class.md)-türetilmiş bir nesneye. Bu durumlarda, katıştırılmış üst denetimin varsayılan davranışını ve görünümünü üzerinde daha fazla denetime ihtiyacınız var.

Standart sağlamak için bir üst bilgi denetiminin istediğiniz ortak durumda da, varsayılan davranışı, kullanmak istediğiniz [CListCtrl](../mfc/reference/clistctrl-class.md) veya [CListView](../mfc/reference/clistview-class.md) yerine. Kullanım `CListCtrl` katıştırılmış bir liste görünümü ortak denetiminde varsayılan üstbilgi denetimi işlevlerini istediğinizde. Kullanım [CListView](../mfc/reference/clistview-class.md) bir görünüm nesnesini katıştırılmış bir varsayılan üstbilgi denetimi işlevlerini istediğinizde.

> [!NOTE]
>  Liste Görünümü denetimi kullanarak oluşturduysanız, bu denetimlerin yalnızca yerleşik üstbilgi denetimi dahil **LVS_REPORT** stili.

Çoğu durumda, katıştırılmış üst bilgi denetiminin görünümünü içeren liste görünümü denetimi stillerini değiştirme tarafından değiştirilebilir. Ayrıca, üst liste görünümü denetimi üye işlevleri aracılığıyla üstbilgi denetimi ile ilgili bilgi elde edilebilir. Ancak, tam denetim ve erişim, öznitelikleri ve katıştırılmış üstbilgi denetim stilleri, üst bilgi denetimi nesneye bir işaretçi alınması önerilir.

Katıştırılmış üstbilgi denetim nesnesi'nden ya da erişilebilir `CListCtrl` veya `CListView` çağrısıyla ilgili sınıfın `GetHeaderCtrl` üye işlevi. Aşağıdaki kod bunu göstermektedir:

[!code-cpp[NVC_MFCControlLadenDialog#14](../mfc/codesnippet/cpp/header-control-and-list-control_1.cpp)]

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz

- [Üstbilgi denetimleriyle görüntü listeleri kullanma](../mfc/using-image-lists-with-header-controls.md)

## <a name="see-also"></a>Ayrıca bkz.

[CHeaderCtrl Kullanma](../mfc/using-cheaderctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
