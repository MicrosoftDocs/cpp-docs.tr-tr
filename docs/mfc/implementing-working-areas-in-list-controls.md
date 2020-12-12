---
description: 'Daha fazla bilgi edinin: liste denetimlerinde çalışma alanı uygulama'
title: Liste Denetimlerinde Çalışma Alanlarını Uygulama
ms.date: 11/04/2016
helpviewer_keywords:
- list controls [MFC], working areas
- working areas in list control [MFC]
ms.assetid: fbbb356b-3359-4348-8603-f1cb114cadde
ms.openlocfilehash: 04eb935531dff0ac1ee240dec8690bd7ce1378a2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97290082"
---
# <a name="implementing-working-areas-in-list-controls"></a>Liste Denetimlerinde Çalışma Alanlarını Uygulama

Varsayılan olarak, liste denetimi tüm öğeleri standart bir kılavuzda düzenler. Ancak, bir diğer yöntem, liste öğelerini dikdörtgen gruplar halinde düzenler, çalışma alanlarında desteklenir. Çalışma alanını uygulayan bir liste denetiminin görüntüsü için, bkz. Windows SDK List-View denetimlerini kullanma.

> [!NOTE]
> Çalışma alanlarında yalnızca liste denetimi simge veya küçük simge modunda olduğunda görünür. Ancak, görünüm rapor veya liste moduna geçiş yaparken geçerli çalışma alanlarının tutulması gerekir.

Çalışma alanlarında boş bir sınır (sol tarafta, üst ve/veya sağ tarafta) veya normalde bir tane olmadığında bir yatay kaydırma çubuğunun görüntülenmesine neden olacak şekilde kullanılabilir. Diğer bir yaygın kullanım, öğelerin taşınabileceği veya bırakılabileceği birden fazla çalışma alanı oluşturmaktır. Bu yöntemde, farklı anlamlara sahip tek bir görünümde alan oluşturabilirsiniz. Kullanıcı daha sonra öğeleri farklı bir alana yerleştirerek kategorilere ayırabilirsiniz. Buna bir örnek, okuma/yazma dosyaları alanı olan bir dosya sisteminin görünümü ve salt okuma dosyaları için başka bir alandır. Bir dosya öğesi salt okuma alanına taşınmışsa, otomatik olarak salt okunabilir hale gelir. Bir dosyayı salt oku/yaz alanına taşımak dosyayı okuma/yazma olarak yapar.

`CListCtrl` liste denetiinizdeki çalışma alanlarının oluşturulması ve yönetilmesi için çeşitli üye işlevleri sağlar. [GetWorkAreas](reference/clistctrl-class.md#getworkareas) ve [SetWorkAreas](reference/clistctrl-class.md#setworkareas) `CRect` `RECT` , liste denetiminiz için geçerli olarak uygulanan çalışma alanını depolayan nesneler (veya yapılar) dizisini alın ve ayarlayın. Ayrıca, [GetNumberOfWorkAreas](reference/clistctrl-class.md#getnumberofworkareas) , liste denetiminiz için geçerli çalışma alanı sayısını (varsayılan olarak sıfır) alır.

## <a name="items-and-working-areas"></a>Öğeler ve çalışma alanı

Çalışma alanı oluşturulduğunda, çalışma alanında yer alan öğeler onun üyesi olur. Benzer şekilde, bir öğe çalışma alanına taşınırsa, taşındığı çalışma alanının bir üyesi olur. Bir öğe herhangi bir çalışma alanında yer içermiyorsa, otomatik olarak ilk (Dizin 0) çalışma alanının bir üyesi olur. Bir öğe oluşturmak ve belirli bir çalışma alanına yerleştirilmesini istiyorsanız, öğeyi oluşturmanız ve ardından [SetItemPosition](reference/clistctrl-class.md#setitemposition)çağrısıyla istenen çalışma alanına taşımanız gerekir. Aşağıdaki ikinci örnekte bu teknik gösterilmektedir.

Aşağıdaki örnek dört çalışma `rcWorkAreas` alanını (), her çalışma alanı etrafında 10 piksellik bir kenarlık olan eşit büyüklükte bir liste denetiminde ( `m_WorkAreaListCtrl` ) uygular.

[!code-cpp[NVC_MFCControlLadenDialog#20](codesnippet/cpp/implementing-working-areas-in-list-controls_1.cpp)]

[Yaklaşık Teviewrect](reference/clistctrl-class.md#approximateviewrect) çağrısı, tüm öğeleri tek bir bölgede göstermek için gereken toplam alanın tahminini almak üzere yapılmıştır. Bu tahmin daha sonra dört bölgeye bölünür ve 5 piksel geniş bir kenarlıkla doldurulur.

Sonraki örnek, var olan liste öğelerini her gruba () atar `rcWorkAreas` ve efekti tamamlamaya yönelik denetim görünümünü ( `m_WorkAreaListCtrl` ) yeniler.

[!code-cpp[NVC_MFCControlLadenDialog#21](codesnippet/cpp/implementing-working-areas-in-list-controls_2.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[CListCtrl Kullanma](using-clistctrl.md)<br/>
[Denetimler](controls-mfc.md)
