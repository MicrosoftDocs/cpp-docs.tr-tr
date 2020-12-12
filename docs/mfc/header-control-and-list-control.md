---
description: 'Daha fazla bilgi edinin: üst bilgi denetimi ve liste denetimi'
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
ms.openlocfilehash: d2301f82a76516a008de0a72e1c9288580b8f545
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325925"
---
# <a name="header-control-and-list-control"></a>Üstbilgi denetimi ve liste denetimi

Çoğu durumda, bir [CListCtrl](reference/clistctrl-class.md) veya [clienstview](reference/clistview-class.md) nesnesine gömülü olan üst bilgi denetimini kullanacaksınız. Ancak, bir [CView](reference/cview-class.md)tarafından türetilen nesne içindeki verileri düzenleme, sütunlarda veya satırlarda düzenleme gibi ayrı bir üst bilgi Denetim nesnesinin tercih edildiği durumlar vardır. Bu durumlarda, bir katıştırılmış üstbilgi denetiminin görünümü ve varsayılan davranışı üzerinde daha fazla denetime sahip olmanız gerekir.

Bir üst bilgi denetiminin standart, varsayılan davranışı sağlamasını istiyorsanız, bunun yerine [CListCtrl](reference/clistctrl-class.md) veya [CListView](reference/clistview-class.md) kullanmak isteyebilirsiniz. `CListCtrl`Bir liste görünümü ortak denetiminde gömülü olan varsayılan üst bilgi denetimi işlevlerini istediğiniz zaman kullanın. Bir görünüm nesnesine gömülü olan varsayılan üst bilgi denetiminin işlevselliğini istediğinizde [CListView](reference/clistview-class.md) kullanın.

> [!NOTE]
> Bu denetimler yalnızca **LVS_REPORT** stili kullanılarak liste görünümü denetimi oluşturulduysa yerleşik bir başlık denetimini içerir.

Çoğu durumda, katıştırılmış üst bilgi denetiminin görünümü, kapsayan liste görünümü denetiminin stilleri değiştirilerek değiştirilebilir. Ayrıca, üstbilgi denetimiyle ilgili bilgiler üst liste görünümü denetiminin üye işlevleri aracılığıyla elde edilebilir. Bununla birlikte, tüm denetim ve erişim için katıştırılmış üst bilgi denetiminin özniteliklerine ve stillerine kadar, üst bilgi denetim nesnesine bir işaretçi alınması önerilir.

Katıştırılmış üstbilgi denetim nesnesine `CListCtrl` veya `CListView` ilgili sınıfın üye işlevine yapılan çağrıdan erişilebilir `GetHeaderCtrl` . Aşağıdaki kod bunu gösterir:

[!code-cpp[NVC_MFCControlLadenDialog#14](codesnippet/cpp/header-control-and-list-control_1.cpp)]

## <a name="what-do-you-want-to-know-more-about"></a>Hakkında daha fazla bilgi edinmek istiyorsunuz

- [Üstbilgi denetimleriyle birlikte görüntü listeleri kullanma](using-image-lists-with-header-controls.md)

## <a name="see-also"></a>Ayrıca bkz.

[CHeaderCtrl Kullanma](using-cheaderctrl.md)<br/>
[Denetimler](controls-mfc.md)
