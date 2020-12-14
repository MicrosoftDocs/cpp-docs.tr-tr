---
description: 'Daha fazla bilgi edinin: Ağaç Denetim resmi listeleri'
title: Ağaç Denetim Görüntü Listeleri
ms.date: 11/04/2016
helpviewer_keywords:
- images [MFC], lists in tree controls
- tree controls [MFC], image lists
- CTreeCtrl class [MFC], image lists
ms.assetid: f560c4f2-20d2-4d28-ac33-4017e65fb0a6
ms.openlocfilehash: ce76cca5642208d4158b36c45c150202270258e4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97264160"
---
# <a name="tree-control-image-lists"></a>Ağaç Denetim Görüntü Listeleri

Ağaç denetimindeki her öğe ([Ctreeci](../mfc/reference/ctreectrl-class.md)) onunla ilişkili bir çift bit eşlenmiş görüntü olabilir. Görüntüler, bir öğenin etiketinin sol tarafında görünür. Öğe seçildiğinde bir görüntü görüntülenir ve öğe seçilmediğinde diğeri görüntülenir. Örneğin, bir öğe seçildiğinde açık bir klasör ve seçili olmadığında kapalı bir klasör görüntülenebilir.

Öğe görüntülerini kullanmak için bir [CImageList](../mfc/reference/cimagelist-class.md) nesnesi oluşturup, ilişkili görüntü listesini oluşturmak Için [CImageList:: Create](../mfc/reference/cimagelist-class.md#create) işlevini kullanarak bir görüntü listesi oluşturmanız gerekir. Ardından istenen bit eşlemleri listeye ekleyin ve [SetImageList](../mfc/reference/ctreectrl-class.md#setimagelist) üye işlevini kullanarak listeyi ağaç denetimiyle ilişkilendirin. Varsayılan olarak, tüm öğeler hem seçili hem de seçili olmayan durumlar için görüntü listesindeki ilk görüntüyü görüntüler. [InsertItem](../mfc/reference/ctreectrl-class.md#insertitem) üye işlevini kullanarak öğe ağaç denetimine eklenirken seçili ve seçili olmayan görüntülerin dizinlerini belirterek, belirli bir öğe için varsayılan davranışı değiştirebilirsiniz. [Setitemımage](../mfc/reference/ctreectrl-class.md#setitemimage) üye işlevini kullanarak bir öğeyi ekledikten sonra dizinleri değiştirebilirsiniz.

Ağaç denetiminin görüntü listeleri, öğe görüntülerinde kullanılmak üzere tasarlanan kaplama görüntülerini da içerebilir. Bit 8 ' de bir ağaç denetim öğesi durumunun sıfır dışında bir değeri, bir kaplama görüntüsünün tek tabanlı dizinini belirtir (0, bir kaplama görüntüsü olmadığını gösterir). 4 bit, tek tabanlı bir dizin kullanıldığından, kaplama görüntülerinin görüntü listelerindeki ilk 15 görüntü arasında olması gerekir. Ağaç Denetim öğesi durumları hakkında daha fazla bilgi için bu konunun önceki kısımlarında yer alarak [Ağaç denetimi öğe durumlarına genel bakış](../mfc/tree-control-item-states-overview.md) bölümüne bakın.

Bir durum görüntüsü listesi belirtilmişse, ağaç denetimi bir durum görüntüsü için her öğenin simgesinin solunda yer alan alanı ayırır. Uygulama, uygulama tanımlı öğe durumlarını göstermek için, denetlenen ve temizlenmiş onay kutuları gibi durum görüntülerini kullanabilir. Bit olarak 12 ile 15 arasında sıfır olmayan bir değer, bir durum görüntüsünün tek tabanlı dizinini belirtir (0 durum görüntüsü olmadığını gösterir).

Bir görüntünün dizini yerine **I_IMAGECALLBACK** değerini belirterek, öğe yeniden çizilene kadar seçili veya seçili olmayan görüntünün belirtilmesini erteleyebilirsiniz. **I_IMAGECALLBACK** , ağaç denetimini, dizin için [TVN_GETDISPINFO](/windows/win32/Controls/tvn-getdispinfo) bildirim iletisini göndererek uygulamayı sorgulamak üzere yönlendirir.

[GetImageList](../mfc/reference/ctreectrl-class.md#getimagelist) üye işlevi bir ağaç denetiminin görüntü listesinin tanıtıcısını alır. Bu işlev, listeye daha fazla görüntü eklemeniz gerekiyorsa yararlıdır. Görüntü listeleri hakkında daha fazla bilgi için bkz. [CImageList](../mfc/using-cimagelist.md), *MFC başvurusu* içindeki [CImageList](../mfc/reference/cimagelist-class.md) ve Windows SDK [görüntü listeleri](/windows/win32/controls/image-lists) kullanma.

## <a name="see-also"></a>Ayrıca bkz.

[CTreeCtrl Kullanma](../mfc/using-ctreectrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
