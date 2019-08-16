---
title: Denetime Öğe Ekleme
ms.date: 11/04/2016
helpviewer_keywords:
- CListCtrl class [MFC], adding items
ms.assetid: 715994bd-340d-4ad2-9882-411654137830
ms.openlocfilehash: 6c03be6f04746ec2e3146916d72cad637a204187
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69509332"
---
# <a name="adding-items-to-the-control"></a>Denetime Öğe Ekleme

Liste denetimine ([CListCtrl](../mfc/reference/clistctrl-class.md)) öğe eklemek için, sahip olduğunuz bilgilere bağlı olarak [InsertItem](../mfc/reference/clistctrl-class.md#insertitem) üye işlevinin çeşitli sürümlerinden birini çağırın. Bir sürüm, hazırladığınız bir [Lvidıtem](/windows/win32/api/commctrl/ns-commctrl-lvitemw) yapısını alır. `LVITEM` Yapı çok sayıda üye içerdiğinden, liste denetim öğesinin öznitelikleri üzerinde daha fazla denetiminiz vardır.

Yapının iki önemli üyesi (rapor görünümü ile ilgili olarak) `iSubItem` veüyeleridir.`iItem` `LVITEM` Üye, yapının başvurduğu öğenin sıfır tabanlı dizinidir `iSubItem` ve üye bir alt öğenin tek tabanlı dizinidir veya yapı bir öğe hakkında bilgi içeriyorsa sıfır olur. `iItem` Bu iki üye ile, liste denetimi rapor görünümünde olduğunda görüntülenen alt öğe bilgilerinin türü ve değeri her öğe için belirlenir. Daha fazla bilgi için bkz. [CListCtrl:: SetItem](../mfc/reference/clistctrl-class.md#setitem).

Ek Üyeler öğenin metin, simge, durum ve öğe verilerini belirtir. "Öğe verileri" liste görünümü öğesiyle ilişkili uygulama tanımlı bir değerdir. `LVITEM` Yapı hakkında daha fazla bilgi için, bkz. [CListCtrl:: GetItem](../mfc/reference/clistctrl-class.md#getitem).

Diğer sürümleri `InsertItem` , `LVITEM` yapıdaki üyelere karşılık gelen ve yalnızca desteklemek istediğiniz üyeleri başlatmanıza olanak tanıyan bir veya daha fazla ayrı değer alır. Genellikle liste denetimi, liste öğeleri için depolamayı yönetir, ancak "geri çağırma öğeleri" ni kullanarak uygulamanızdaki bazı bilgileri de saklayabilirsiniz. Daha fazla bilgi için, bu konudaki [geri arama öğeleri ve](../mfc/callback-items-and-the-callback-mask.md) geri çağırma maskesi ve [](/windows/win32/Controls/using-list-view-controls) Windows SDK geri çağırma maskesini inceleyin.

Daha fazla bilgi için bkz. [liste ve alt öğeleri ekleme](/windows/win32/Controls/using-list-view-controls).

## <a name="see-also"></a>Ayrıca bkz.

[CListCtrl Kullanma](../mfc/using-clistctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
