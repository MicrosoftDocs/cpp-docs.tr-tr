---
description: 'Daha fazla bilgi için: liste denetimi ve liste görünümü'
title: Liste Denetimi ve Liste Görünümü
ms.date: 11/04/2016
helpviewer_keywords:
- CListView class [MFC], and CListCtrl
- views [MFC], list and list control
- CListCtrl class [MFC], and CListView
- list views [MFC]
- list controls [MFC], List view
ms.assetid: 7aee1c48-b158-4399-be0b-be366993665e
ms.openlocfilehash: 582957cb59bc28797849d45f56fc2be95b8cc2b3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336806"
---
# <a name="list-control-and-list-view"></a>Liste Denetimi ve Liste Görünümü

MFC daha kolay bir şekilde liste denetimini iki şekilde kapsüller. Liste denetimlerini kullanabilirsiniz:

- İletişim kutusu sınıfına bir [Clienstctrl](reference/clistctrl-class.md) nesnesi katıştırarak doğrudan.

- Dolaylı olarak, sınıf [Clienstview](reference/clistview-class.md)kullanılarak.

`CListView` bir liste denetimini MFC belge/görünüm mimarisi ile tümleştirmeyi kolaylaştırır. [CEditView](reference/ceditview-class.md) bir düzenleme denetimi kapsüller. denetim, bir MFC görünümünün tüm yüzey alanını doldurur. ( *Görünüm denetim, öğesine* atama `CListView` )

Bir `CListView` nesne [CCtrlView](reference/cctrlview-class.md) ve temel sınıflarından devralır ve temel alınan liste denetimini almak için bir üye işlevi ekler. Görünümle görünüm olarak çalışmak için görünüm üyelerini kullanın. Liste denetiminin üye işlevlerine erişim kazanmak için [GetListCtrl](reference/clistview-class.md#getlistctrl) üye işlevini kullanın. Bu üyeleri şu şekilde kullanın:

- Listeye "öğe" ekleyin, silin veya değiştirin.

- Liste denetim özniteliklerini ayarlayın veya alın.

Temel alınan a başvurusunu almak için `CListCtrl` `CListView` , `GetListCtrl` liste görünümü sınıfınızı çağırın:

[!code-cpp[NVC_MFCListView#4](../atl/reference/codesnippet/cpp/list-control-and-list-view_1.cpp)]

Bu konuda, liste denetimini kullanmanın her iki yolu da açıklanmaktadır.

## <a name="see-also"></a>Ayrıca bkz.

[CListCtrl Kullanma](using-clistctrl.md)<br/>
[Denetimler](controls-mfc.md)
