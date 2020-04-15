---
title: Liste Denetimlerinde Çalışma Alanlarını Uygulama
ms.date: 11/04/2016
helpviewer_keywords:
- list controls [MFC], working areas
- working areas in list control [MFC]
ms.assetid: fbbb356b-3359-4348-8603-f1cb114cadde
ms.openlocfilehash: 91577203163247bd230fecb083cf1c50e2875b98
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377219"
---
# <a name="implementing-working-areas-in-list-controls"></a>Liste Denetimlerinde Çalışma Alanlarını Uygulama

Varsayılan olarak, liste denetimi tüm öğeleri standart ızgara şeklinde düzenler. Ancak, liste öğelerini dikdörtgen gruplarhalinde düzenleyen çalışma alanları olan başka bir yöntem desteklenir. Çalışma alanlarını uygulayan bir liste denetimi nin görüntüsü için Windows SDK'da Liste Görünümü Denetimlerini Kullanma bölümüne bakın.

> [!NOTE]
> Çalışma alanları yalnızca liste denetimi simge veya küçük simge modunda olduğunda görünür. Ancak, görünüm rapor veya liste moduna geçerse, geçerli çalışma alanları korunur.

Çalışma alanları boş bir kenarlığı (öğelerin solunda, üstünde ve/veya sağında) görüntülemek veya normalde bir kenarlık olmadığında yatay kaydırma çubuğunun görüntülenmesine neden olmak için kullanılabilir. Başka bir yaygın kullanım, maddelerin taşınabileceği veya bırakılabildiği birden çok çalışma alanı oluşturmaktır. Bu yöntemle, farklı anlamlara sahip tek bir görünümde alanlar oluşturabilirsiniz. Kullanıcı daha sonra öğeleri farklı bir alana yerleştirerek kategorilere ayırabilir. Buna bir örnek, okuma/yazma dosyaları için bir alana ve salt okunur dosyalar için başka bir alana sahip bir dosya sisteminin görünümü olacaktır. Bir dosya öğesi salt okunur alanına taşınırsa, otomatik olarak salt okunur olur. Bir dosyayı salt okunur alanından okuma/yazma alanına taşımak, dosyanın okunması/yazılması dır.

`CListCtrl`liste denetiminizde çalışma alanları oluşturmak ve yönetmek için çeşitli üye işlevler sağlar. [Çalışma Alanları](../mfc/reference/clistctrl-class.md#getworkareas) ve [SetÇalışma Alanları,](../mfc/reference/clistctrl-class.md#setworkareas) liste `CRect` denetiminiz `RECT` için şu anda uygulanan çalışma alanlarını depolayan bir dizi nesne (veya yapı) alır ve ayarlar. Buna ek olarak, [GetNumberOfWorkAreas](../mfc/reference/clistctrl-class.md#getnumberofworkareas) liste denetiminiz için geçerli çalışma alanı sayısını alır (varsayılan olarak sıfır).

## <a name="items-and-working-areas"></a>Öğeler ve Çalışma Alanları

Bir çalışma alanı oluşturulduğunda, çalışma alanı içinde bulunan öğeler bu alanın üyesi olur. Benzer şekilde, bir öğe çalışma alanına taşınırsa, taşındığı çalışma alanının bir üyesi olur. Bir öğe herhangi bir çalışma alanı içinde yoksa, otomatik olarak ilk (dizin 0) çalışma alanının bir üyesi olur. Bir öğe oluşturmak ve belirli bir çalışma alanına yerleştirilmesini istiyorsanız, öğeyi oluşturmanız ve ardından [SetItemPosition'e](../mfc/reference/clistctrl-class.md#setitemposition)yapılan bir çağrıyla istediğiniz çalışma alanına taşımanız gerekir. Aşağıdaki ikinci örnekbu tekniği göstermektedir.

Aşağıdaki örnek, bir liste`rcWorkAreas`denetiminde, her çalışma alanının etrafında 10 piksel genişliğinde kenarlıklı`m_WorkAreaListCtrl`eşit boyutta dört çalışma alanı (), uygular.

[!code-cpp[NVC_MFCControlLadenDialog#20](../mfc/codesnippet/cpp/implementing-working-areas-in-list-controls_1.cpp)]

[ApproximateViewRect'e](../mfc/reference/clistctrl-class.md#approximateviewrect) yapılan arama, bir bölgedeki tüm öğeleri görüntülemek için gereken toplam alanın tahminini almak için yapıldı. Bu tahmin daha sonra dört bölgeye bölünür ve 5 piksel genişliğinde kenarlık ile yastıklanır.

Sonraki örnek, varolan liste öğelerini`rcWorkAreas`her gruba ( )`m_WorkAreaListCtrl`atar ve efekti tamamlamak için denetim görünümünü ( ) yeniler.

[!code-cpp[NVC_MFCControlLadenDialog#21](../mfc/codesnippet/cpp/implementing-working-areas-in-list-controls_2.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[CListCtrl Kullanma](../mfc/using-clistctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
