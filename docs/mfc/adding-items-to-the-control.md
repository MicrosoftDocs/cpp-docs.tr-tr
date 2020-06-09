---
title: Denetime Öğe Ekleme
ms.date: 11/04/2016
helpviewer_keywords:
- CListCtrl class [MFC], adding items
ms.assetid: 715994bd-340d-4ad2-9882-411654137830
ms.openlocfilehash: 5cc1c7a921cf6d6ba2c0f968012b48bfcaef0658
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84623372"
---
# <a name="adding-items-to-the-control"></a>Denetime Öğe Ekleme

Liste denetimine ([CListCtrl](reference/clistctrl-class.md)) öğe eklemek için, sahip olduğunuz bilgilere bağlı olarak [InsertItem](reference/clistctrl-class.md#insertitem) üye işlevinin çeşitli sürümlerinden birini çağırın. Bir sürüm, hazırladığınız bir [Lvidıtem](/windows/win32/api/commctrl/ns-commctrl-lvitemw) yapısını alır. `LVITEM`Yapı çok sayıda üye içerdiğinden, liste denetim öğesinin öznitelikleri üzerinde daha fazla denetiminiz vardır.

Yapının iki önemli üyesi (rapor görünümü ile ilgili olarak) `LVITEM` `iItem` ve `iSubItem` üyeleridir. `iItem`Üye, yapının başvurduğu öğenin sıfır tabanlı dizinidir ve `iSubItem` üye bir alt öğenin tek tabanlı dizinidir veya yapı bir öğe hakkında bilgi içeriyorsa sıfır olur. Bu iki üye ile, liste denetimi rapor görünümünde olduğunda görüntülenen alt öğe bilgilerinin türü ve değeri her öğe için belirlenir. Daha fazla bilgi için bkz. [CListCtrl:: SetItem](reference/clistctrl-class.md#setitem).

Ek Üyeler öğenin metin, simge, durum ve öğe verilerini belirtir. "Öğe verileri" liste görünümü öğesiyle ilişkili uygulama tanımlı bir değerdir. Yapı hakkında daha fazla bilgi için `LVITEM` , bkz. [CListCtrl:: GetItem](reference/clistctrl-class.md#getitem).

Diğer sürümleri, `InsertItem` yapıdaki üyelere karşılık gelen ve `LVITEM` yalnızca desteklemek istediğiniz üyeleri başlatmanıza olanak tanıyan bir veya daha fazla ayrı değer alır. Genellikle liste denetimi, liste öğeleri için depolamayı yönetir, ancak "geri çağırma öğeleri" ni kullanarak uygulamanızdaki bazı bilgileri de saklayabilirsiniz. Daha fazla bilgi için, bu konudaki [geri arama öğeleri ve](callback-items-and-the-callback-mask.md) geri çağırma maskesi ve Windows SDK geri [çağırma maskesini inceleyin](/windows/win32/Controls/using-list-view-controls) .

Daha fazla bilgi için bkz. [liste ve alt öğeleri ekleme](/windows/win32/Controls/using-list-view-controls).

## <a name="see-also"></a>Ayrıca bkz.

[CListCtrl Kullanma](using-clistctrl.md)<br/>
[Denetimler](controls-mfc.md)
