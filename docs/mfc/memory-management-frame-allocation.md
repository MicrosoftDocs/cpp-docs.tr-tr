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
ms.openlocfilehash: 1f67149e5835ee6f2b8922b29ee92872b24d0ec4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33349317"
---
# <a name="memory-management-frame-allocation"></a>Bellek Yönetimi: Çerçeve Ayırma
Çerçevesinde ayırma "olarak ayarlanmış yığın çerçevesi" adı geçen her bir işlev çağrılır. Yığın çerçevesi tutan geçici olarak bağımsız değişkenler tanımlanan değişkenler yanı sıra işlevi işlevi için yerel bellek alanıdır. Derleyici otomatik olarak alanı kendileri için ayırdığından çerçeve değişkenleri genellikle "Otomatik" değişkenleri denir.  
  
 Çerçeve ayırma iki anahtar özellikleri vardır. İlk olarak, yerel bir değişken tanımladığınızda, uzun dizi veya veri yapısı olsa bile, yeterli alan tüm değişkeni tutmak için yığın çerçevesi ayrılır. İkinci olarak, kapsam dışı olduğunuzda çerçeve değişkenleri otomatik olarak silinir:  
  
 [!code-cpp[NVC_MFC_Utilities#10](../mfc/codesnippet/cpp/memory-management-frame-allocation_1.cpp)]  
  
 İç içe ayraçlar kullanılıyorsa bir çerçeve değişkenin kapsamını ancak işlevi çıkar işlevi küçük olabilir yerel işlevi değişkenleri için bu kapsamı geçiş olur. Bu çerçeve değişkenleri otomatik olarak silinmesini çok önemlidir. Basit ilkel türler söz konusu olduğunda (gibi `int` veya **bayt**), dizi ya da veri yapılarını otomatik silme yalnızca değişkeni tarafından kullanılan bellek geri kazanır. Değişkeni fazlası kapsam dışında olduğundan, yine de erişilemiyor. C++ nesneleri söz konusu olduğunda, ancak otomatik silme işlemi biraz daha karmaşıktır.  
  
 Bir nesne bir çerçeve değişken olarak tanımlandığında, kurucusu tanımı burada karşılaştı noktada otomatik olarak çağrılır. Nesne kapsam dışına çıktığında nesnesi için bellek alınmadan önce kendi yıkıcı otomatik olarak çağrılır. Bu otomatik oluşturma ve yok etme çok kullanışlı olabilir, ancak otomatik çağrıları, özellikle yıkıcı farkında olmanız gerekir.  
  
 Çerçevede nesneleri ayırma önemli bir avantajı, bunlar otomatik olarak silinmesini ' dir. Çerçeve nesneleriniz ayırdığınızda, bellek sızıntıları neden Unutulan nesneler hakkında endişelenmenize gerek yoktur. (Bellek sızıntıları hakkında daha fazla bilgi için bkz: [MFC'de bellek sızıntılarını algılama](http://msdn.microsoft.com/en-us/29ee8909-96e9-4246-9332-d3a8aa8d4658).) Çerçeve ayırma dezavantajı, çerçeve değişkenleri kendi kapsamı dışında kullanılamaz olmasıdır. Yığın ayırma karşı çerçeve ayırma seçme başka bir etken büyük yapıları ve nesneler için genellikle yığın alanı genellikle sınırlı olduğu öbek yerine yığın depolama alanını kullanın. daha iyi olmasıdır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bellek Yönetimi](../mfc/memory-management.md)

