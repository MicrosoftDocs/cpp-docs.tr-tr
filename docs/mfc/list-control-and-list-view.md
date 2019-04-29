---
title: Liste Denetimi ve Liste Görünümü
ms.date: 11/04/2016
helpviewer_keywords:
- CListView class [MFC], and CListCtrl
- views [MFC], list and list control
- CListCtrl class [MFC], and CListView
- list views [MFC]
- list controls [MFC], List view
ms.assetid: 7aee1c48-b158-4399-be0b-be366993665e
ms.openlocfilehash: 5c9612a22eab27d568c0dbb86d29ba031fe5985e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62365339"
---
# <a name="list-control-and-list-view"></a>Liste Denetimi ve Liste Görünümü

Kolaylık olması için MFC, iki yolla liste denetimi kapsüller. Liste denetimleri kullanabilirsiniz:

- Katıştırarak, doğrudan bir [CListCtrl](../mfc/reference/clistctrl-class.md) iletişim kutusu sınıfı nesne.

- Sınıfı kullanarak dolaylı olarak [CListView](../mfc/reference/clistview-class.md).

`CListView` Liste denetimi denetim Kapsüllenen MFC belge/görünüm mimarisi ile tümleştirmek çok kolaylaştırır [CEditView](../mfc/reference/ceditview-class.md) kapsülleyen bir düzenleme denetimi: denetim MFC Görünümü tüm yüzey alanını doldurur. (Görünüm *olduğu* başvurusuna denetimi `CListView`.)

A `CListView` nesne devraldığı [CCtrlView](../mfc/reference/cctrlview-class.md) ve bunun temel sınıfları ve temel alınan bir liste denetimini almak için bir üye işlevi ekler. Görünüm olarak çalışmak için üyeleri Görüntüle'yi kullanın. Kullanım [GetListCtrl](../mfc/reference/clistview-class.md#getlistctrl) listesi denetiminin üye işlevleri erişmek için üye işlevi. Bu üyeleri kullanın:

- Ekleme, silme veya listesinde "Items" işleme.

- Ayarlayın ya da liste denetim öznitelikleri alın.

Bir başvuru almak `CListCtrl` temel bir `CListView`, çağrı `GetListCtrl` liste görünümü sınıfından:

[!code-cpp[NVC_MFCListView#4](../atl/reference/codesnippet/cpp/list-control-and-list-view_1.cpp)]

Bu konu, liste denetimi kullanmak için her iki yollarını açıklar.

## <a name="see-also"></a>Ayrıca bkz.

[CListCtrl Kullanma](../mfc/using-clistctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
