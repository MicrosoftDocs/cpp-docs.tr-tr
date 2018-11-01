---
title: Yığın ve Kuyruk Koleksiyonları Oluşturma
ms.date: 11/04/2016
helpviewer_keywords:
- MFC collection classes [MFC], stack collections
- collections, stack
- stack
- collection classes [MFC], creating
- queue collections
- MFC collection classes [MFC], queue collections
- stack collections
- collections, queue
ms.assetid: 3c7bc198-35f0-4fc3-aaed-6005a0f22638
ms.openlocfilehash: 082308acaeddcb173a0d873c0f50e2e40fd8fe12
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50569244"
---
# <a name="creating-stack-and-queue-collections"></a>Yığın ve Kuyruk Koleksiyonları Oluşturma

Bu makalede gibi diğer veri yapılarını oluşturma açıklanır [yığınları](#_core_stacks) ve [kuyrukları](#_core_queues), MFC'den sınıfların listesi. Türetilen sınıflar örneklerde `CList`, ancak kullanabilirsiniz `CList` doğrudan işlevselliği eklemek gerekli olmadıkça.

##  <a name="_core_stacks"></a> Yığınları

Standart liste koleksiyon head hem bir kuyruk olduğundan, bir son giren ilk-çıkar yığını davranışını taklit eden bir türetilmiş listesi koleksiyonunu oluşturmak kolaydır. Bir yığın içinde bir kafeterya Tepsi yığınını gibidir. Tepsi yığına eklendikçe yığının en üstünde gitmeleri. Eklenen son kaldırılacak ilk alanıdır. Liste koleksiyon üye işlevleri `AddHead` ve `RemoveHead` eklemek için kullanılabilir ve özellikle listesinin başından öğeleri kaldırın; bu nedenle, en son öğesi kaldırılacak ilk eklenir.

#### <a name="to-create-a-stack-collection"></a>Bir yığın koleksiyonu oluşturmak için

1. Varolan MFC listesi sınıflarının birinden bir yeni liste sınıf türetin ve yığın işlemleri işlevlerini desteklemek için daha fazla üye işlevleri ekleyin.

   Aşağıdaki örnek, yığın, yığın üst öğesinin göz at açın öğeleri gönderme ve üst öğe yığından pop üye işlevleri eklemek gösterilmektedir:

   [!code-cpp[NVC_MFCCollections#20](../mfc/codesnippet/cpp/creating-stack-and-queue-collections_1.h)]

Bu yaklaşım temel alınan göstermesini Not `CObList` sınıfı. Herhangi bir kullanıcı çağırabilirsiniz `CObList` üye işlevi bir yığın için veya mantıklıdır olup olmadığını.

##  <a name="_core_queues"></a> Kuyruklar

Standart liste koleksiyon head hem bir kuyruk olduğundan, ayrıca ilk-giren ilk çıkar kuyruk davranışını taklit eden bir türetilmiş liste koleksiyonu oluşturmak kolaydır. Bir kuyruk, bir kafeterya insanların bir satır gibidir. İlk satırdaki ilk hizmet kişidir. Daha fazla insana gelir gibi bunlar ve dolayısıyla beklenecek satırın sonuna gidin. Liste koleksiyon üye işlevleri `AddTail` ve `RemoveHead` eklemek için kullanılabilir ve özellikle head veya listenin Kuyruk öğeleri kaldırın; bu nedenle, en son öğe her zaman en son kaldırılacak eklenir.

#### <a name="to-create-a-queue-collection"></a>Kuyruk koleksiyon oluşturma

1. Microsoft Foundation Class Kitaplığı ile sağlanan önceden tanımlı listeye sınıflardan birini yeni bir liste sınıf türetin ve kuyruk işlemleri semantiği desteklemek için daha fazla üye işlevleri ekleyin.

   Aşağıdaki örnek, üye işlevleri sırasının sonuna bir öğe ekleyin ve öğenin sıra önünden almak için nasıl ekleyebilir gösterir.

   [!code-cpp[NVC_MFCCollections#21](../mfc/codesnippet/cpp/creating-stack-and-queue-collections_2.h)]

## <a name="see-also"></a>Ayrıca Bkz.

[Koleksiyonlar](../mfc/collections.md)

