---
title: Liste Denetimlerinde Çalışma Alanlarını Uygulama
ms.date: 11/04/2016
helpviewer_keywords:
- list controls [MFC], working areas
- working areas in list control [MFC]
ms.assetid: fbbb356b-3359-4348-8603-f1cb114cadde
ms.openlocfilehash: 01b166243c9032a113d46ff297b9f6e53429da21
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62297222"
---
# <a name="implementing-working-areas-in-list-controls"></a>Liste Denetimlerinde Çalışma Alanlarını Uygulama

Varsayılan olarak, bir liste denetimini standart kılavuz bir biçimde tüm öğeleri düzenler. Ancak, çalışma liste öğeleri dikdörtgen gruplar halinde düzenler alanlarını, başka bir yöntem desteklenir. Çalışma alanları uygulayan bir liste denetimi görüntüsü için Windows SDK'sını kullanarak liste görünümü denetimleri bakın.

> [!NOTE]
>  Çalışma alanları yalnızca liste denetimi simgesini veya küçük simge modunda olduğunda görünür. Ancak, görünümü rapor ya da liste moduna geçtiyseniz geçerli çalışma alanları korunur.

Çalışma alanları (sol, üst ve/veya öğeler sağındaki üzerinde) boş bir kenarlık görüntülemek veya normalde mıydı olması bir görüntülenecek bir yatay kaydırma çubuğu neden için kullanılabilir. Başka bir ortak kullanımı için öğeleri taşınmış bırakılan veya birden çok çalışma alanları oluşturmaktır. Bu yöntem ile farklı anlamlara sahip tek bir görünümde alanlar oluşturabilirsiniz. Kullanıcı farklı bir alanda koyarak öğeleri ardından kategorilere. Buna örnek olarak, bir okuma/yazma dosyaları için bir alan ve salt okunur dosyalar için başka bir alana sahip bir dosya sistemi görünümünü olacaktır. Dosya öğesi salt okunur alanına taşındıysa, salt okunur otomatik olarak olacak. Bir dosya salt okunur alanından oku/yaz alanına taşıma, okuma/yazma dosya hale getirir.

`CListCtrl` oluşturma ve yönetme, liste denetiminde çalışma alanları için birden fazla üye işlevleri sağlar. [GetWorkAreas](../mfc/reference/clistctrl-class.md#getworkareas) ve [SetWorkAreas](../mfc/reference/clistctrl-class.md#setworkareas) almak ve bir dizi ayarlamak `CRect` nesneleri (veya `RECT` yapıları), liste denetlemek için şu anda uygulanan çalışma alanlarına depolar. Ayrıca, [GetNumberOfWorkAreas](../mfc/reference/clistctrl-class.md#getnumberofworkareas) listesini denetlemek için çalışma alanları geçerli sayısını alır (varsayılan olarak, sıfır).

## <a name="items-and-working-areas"></a>Öğeleri ve çalışma alanları

Bir çalışma alanı oluşturulduğunda, çalışma alanının içinde bulunan öğeler bu üyeleri haline gelir. Benzer şekilde, öğeyi bir çalışma alanına taşınırsa, taşındıktan sonra çalışma alanının bir üyesi haline gelir. Otomatik olarak bir öğe herhangi bir çalışma alanı içinde yer almıyor, ilk (dizin 0) çalışma alanının bir üyesi haline gelir. Bir öğe oluşturun ve belirli bir çalışma alanı içinde yer sağlamak istiyorsanız, öğesi oluşturun ve ardından taşımak istediğiniz çalışma alanına çağrısıyla gerekir [SetItemPosition](../mfc/reference/clistctrl-class.md#setitemposition). Aşağıdaki ikinci örnekte, bu tekniği gösterir.

Aşağıdaki örnekte, dört çalışma alanları uygular (`rcWorkAreas`), her çalışma alanında bir liste denetimini 10-piksel genişliğinde kenarlık ile eşit boyutta (`m_WorkAreaListCtrl`).

[!code-cpp[NVC_MFCControlLadenDialog#20](../mfc/codesnippet/cpp/implementing-working-areas-in-list-controls_1.cpp)]

Çağrı [ApproximateViewRect](../mfc/reference/clistctrl-class.md#approximateviewrect) tek bir bölgede tüm öğeleri görüntülemek için gereken toplam alan kestirmek girişiminde bulunuldu. Bu tahmin sonra dört bölgeye bölünmüş ve 5 piksel genişliğinde kenarlıklı sıfır.

Sonraki örnek, varolan liste öğelerini her gruba atar (`rcWorkAreas`) ve denetimi Görünümü yeniler (`m_WorkAreaListCtrl`) etkisi tamamlanması.

[!code-cpp[NVC_MFCControlLadenDialog#21](../mfc/codesnippet/cpp/implementing-working-areas-in-list-controls_2.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[CListCtrl Kullanma](../mfc/using-clistctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
