---
title: 'Bellek Yönetimi: Çerçeve ayırma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ca2d98898c232cdb65d3ac5d1288b06aca403772
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46398124"
---
# <a name="memory-management-frame-allocation"></a>Bellek Yönetimi: Çerçeve Ayırma

Çerçeve ayırma "olarak ayarlanmış yığın çerçevesini" adını alan her bir işlev çağrılır. Yığın çerçevesinin tutan geçici olarak bağımsız değişkenler tanımlanan tüm değişkenler yanı sıra işlev işleve yerel bellek alanıdır. Derleyicinin otomatik olarak alan için ayırdığından çerçeve değişkenleri genellikle "Otomatik" değişkenler çağrılır.

Çerçeve ayırma iki anahtar özellikleri vardır. İlk olarak, yerel bir değişken tanımlayın, uzun dizi ya da veri yapısı olsa bile yeterli alan tüm değişkeni tutmak için yığın çerçevesinin ayrılır. İkinci olarak, bunlar kapsam dışına çıkmadan, çerçeve değişkenleri otomatik olarak silinir:

[!code-cpp[NVC_MFC_Utilities#10](../mfc/codesnippet/cpp/memory-management-frame-allocation_1.cpp)]

Yerel işlev değişkenleri için iç içe ayraçları kullanılıyorsa bir çerçeve değişkenin kapsamını ancak işlev çıkar bir işlevi küçük olabilir bu kapsam geçiş olur. Bu çerçeve değişkenleri otomatik olarak silinmesini çok önemlidir. Basit ilkel türleri söz konusu olduğunda (gibi **int** veya **bayt**), dizi ya da veri yapılarını otomatik silme yalnızca değişkeni tarafından kullanılan belleği geri kazanır. Değişken kapsam dışına geçti olduğundan, yine de erişilemez. C++ nesnelerinin söz konusu olduğunda, ancak otomatik silme işlemi biraz daha karmaşık bir işlemdir.

Bir nesne bir çerçeve değişken olarak tanımlandığında, yapıcısına tanımını burada karşılaşılanaa noktada otomatik olarak çağrılır. Nesne kapsam dışına çıktığında, nesne için bellek alınmadan önce otomatik olarak, yok Edicisi çağrılır. Bu otomatik oluşturma ve yok etme çok kullanışlı olabilir, ancak yok edici için özellikle otomatik çağrıları farkında olmanız gerekir.

Çerçevede nesneleri ayırma önemli bir avantajı, otomatik olarak silinir. Çerçeve, nesneleri ayırdığınızda, bellek sızıntılarının neden Unutulan nesneleri hakkında endişelenmeniz gerekmez. (Bellek sızıntılarını hakkında daha fazla bilgi için bkz [MFC'de bellek sızıntılarını algılama](/previous-versions/visualstudio/visual-studio-2010/c99kz476\(v=vs.100\)).) Çerçeve ayırma bir dezavantajı, çerçeve değişkenleri kendi kapsamı dışında kullanılamaz olmasıdır. Yığın ayırma ve çerçeve ayırma seçme içinde başka bir faktör büyük yapılar ve nesneler için genellikle yığın alanı çoğunlukla sınırlı olduğundan öbek için Depolama yığını yerine kullanılması daha iyidir olmasıdır.

## <a name="see-also"></a>Ayrıca Bkz.

[Bellek Yönetimi](../mfc/memory-management.md)

