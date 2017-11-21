---
title: "Yığın ve kuyruk koleksiyonları oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
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
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9d2f21d64aaafb133aa756c4ada472bf6cde9c23
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="creating-stack-and-queue-collections"></a>Yığın ve Kuyruk Koleksiyonları Oluşturma
Bu makalede gibi diğer veri yapıları oluşturma açıklanmaktadır [yığınları](#_core_stacks) ve [sıraları](#_core_queues), MFC'den sınıfları listele. Türetilmiş sınıfları örneklerde `CList`, ancak kullanabilirsiniz `CList` doğrudan sürece işlevsellik eklemeniz gerekir.  
  
##  <a name="_core_stacks"></a>Yığınları  
 Standart liste koleksiyonu head ve bir kuyruk olduğundan, son-giren ilk çıkar yığını davranışını taklit eden bir türetilmiş liste koleksiyonu oluşturmak kolaydır. Bir yığın, bir kafeterya Tepsisi yığınını gibidir. Tepsisi yığına eklendikçe, bunlar üzerinde yığını gidin. Eklenen son Tepsisi kaldırılacak ilk ' dir. Liste koleksiyonu üye işlevleri `AddHead` ve `RemoveHead` eklemek için kullanılabilir ve özellikle listenin başından öğeleri kaldırın; bu nedenle, en son öğe kaldırılacak ilk eklenir.  
  
#### <a name="to-create-a-stack-collection"></a>Bir yığın koleksiyonu oluşturmak için  
  
1.  Varolan MFC liste sınıfları birinden bir yeni liste sınıf türetin ve yığın işlemlerinin işlevleri desteklemek için daha fazla üye işlevleri ekleyin.  
  
     Aşağıdaki örnek, öğeleri yığının üst öğede gözlem yığını açın ve gönderebilir yığının üst öğeden pop için üye işlevleri eklemek gösterilmektedir:  
  
     [!code-cpp[NVC_MFCCollections#20](../mfc/codesnippet/cpp/creating-stack-and-queue-collections_1.h)]  
  
 Bu yaklaşımın temel sunan Not `CObList` sınıfı. Kullanıcı herhangi çağırabilirsiniz `CObList` bir yığınının veya mantıklıdır olup olmadığını üye işlev.  
  
##  <a name="_core_queues"></a>Kuyruklar  
 Standart liste koleksiyonu head ve bir kuyruk olduğundan, ayrıca bir ilk olarak ilk çıkış sırası davranışını taklit eden bir türetilmiş liste koleksiyonu oluşturmak kolaydır. Bir kuyruk, bir kafeterya kişilerin bir satır gibidir. İlk satırdaki sunulacak ilk kişidir. Daha fazla kişinin gelen gibi bunlar ve dolayısıyla beklenecek satırın sonuna gidin. Liste koleksiyonu üye işlevleri `AddTail` ve `RemoveHead` eklemek için kullanılabilir ve özellikle head veya listesinin kuyruk öğeleri kaldırın; bu nedenle, en son öğe her zaman en son kaldırılacak eklenir.  
  
#### <a name="to-create-a-queue-collection"></a>Bir kuyruk koleksiyonu oluşturmak için  
  
1.  Microsoft Foundation Class Kitaplığı ile sağlanan önceden tanımlanmış liste sınıfları birini yeni bir liste sınıf türetin ve kuyruk işlemlerini semantiği desteklemek için daha fazla üye işlevleri ekleyin.  
  
     Aşağıdaki örnek, sıranın sonuna bir öğe ekleyin ve sıra Önden öğesini almak için üye işlevleri nasıl ekleyebilirsiniz gösterir.  
  
     [!code-cpp[NVC_MFCCollections#21](../mfc/codesnippet/cpp/creating-stack-and-queue-collections_2.h)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Koleksiyonları](../mfc/collections.md)

