---
description: 'Daha fazla bilgi edinin: bellek yönetimi: çerçeve ayırma'
title: 'Bellek Yönetimi: Çerçeve Ayırma'
ms.date: 11/04/2016
helpviewer_keywords:
- memory leaks [MFC], frame allocation
- memory [MFC], detecting leaks
- memory [MFC], reclaiming
- memory allocation [MFC], frames
- frame variables [MFC], automatic deletion of
- scope [MFC], frame variables
- heap allocation [MFC], vs. frame allocation
- variables [MFC], frame variables
- memory leaks [MFC], detecting
- memory, releasing [MFC]
- stack frames [MFC]
- memory leaks [MFC], allocating objects on the frame
- detecting memory leaks [MFC]
- frame allocation [MFC]
- frame variables [MFC]
ms.assetid: 945a211a-6f4f-4679-bb6a-b0f2a0d4a6c1
ms.openlocfilehash: 1763d332275f17ee082b891830641ebc61cad054
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97193441"
---
# <a name="memory-management-frame-allocation"></a>Bellek Yönetimi: Çerçeve Ayırma

Çerçeve üzerinde ayırma, her bir işlev çağrıldığında ayarlanan "yığın çerçevesinden" adını alır. Yığın çerçevesi, işlevin bağımsız değişkenlerini geçici olarak tutan ve işlev için yerel olarak tanımlanan tüm değişkenler içeren bir bellek alanıdır. Yalnızca derleyici alanı otomatik olarak ayırdığı için çerçeve değişkenlerine genellikle "otomatik" değişkenler denir.

Çerçeve ayırmalarının iki temel özelliği vardır. İlk olarak, bir yerel değişken tanımladığınızda, büyük bir dizi veya veri yapısı olsa bile tüm değişkeni tutmak için yığın çerçevesinde yeterli alan ayrılır. İkinci olarak, çerçeve değişkenleri kapsam dışına gittiklerinde otomatik olarak silinir:

[!code-cpp[NVC_MFC_Utilities#10](codesnippet/cpp/memory-management-frame-allocation_1.cpp)]

Yerel işlev değişkenlerinde, bu kapsam geçişi işlev çıktığında gerçekleşir, ancak iç içe parantezler kullanılırsa bir çerçeve değişkeninin kapsamı bir işlevden daha küçük olabilir. Çerçeve değişkenlerinin bu otomatik olarak silinmesi çok önemlidir. Basit temel türler (örneğin **`int`** , **bayt**), diziler veya veri yapıları söz konusu olduğunda otomatik silme, değişken tarafından kullanılan belleği geri kazanır. Değişken kapsam dışına çıkış yaptığından, yine de erişilemez. Ancak, C++ nesneleri söz konusu olduğunda otomatik silme işlemi biraz daha karmaşıktır.

Bir nesne bir çerçeve değişkeni olarak tanımlandığında, Oluşturucusu otomatik olarak tanımın karşılaştığı noktada çağrılır. Nesne kapsam dışına geçtiğinde, nesne için bellek geri alınmadan önce yıkıcısı otomatik olarak çağrılır. Bu otomatik oluşturma ve yok etme çok kullanışlı olabilir, ancak özellikle yok edicinin otomatik çağrılardan haberdar olmanız gerekir.

Çerçeve üzerinde nesneleri ayırmanın önemli avantajı, otomatik olarak silinirler. Nesneleri çerçevede ayırdığınızda, unutulan nesneler hakkında endişelenmenize gerek kalmaz ve bellek sızıntılarına neden olabilirsiniz. (Bellek sızıntıları hakkında daha fazla bilgi için bkz. [MFC 'de bellek sızıntılarını algılama](/previous-versions/visualstudio/visual-studio-2010/c99kz476(v=vs.100))makalesi.) Çerçeve ayırmanın bir dezavantajı, çerçeve değişkenlerinin kapsam dışında kullanılamaz. Çerçeve ayırmayı ve yığın ayırmayı seçmek için bir faktör, büyük yapılar ve nesneler için, yığın alanı genellikle sınırlı olduğundan depolama yığını yerine yığının kullanılması genellikle daha iyidir.

## <a name="see-also"></a>Ayrıca bkz.

[Bellek yönetimi](memory-management.md)
