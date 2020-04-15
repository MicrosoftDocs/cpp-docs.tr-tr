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
ms.openlocfilehash: 5b3427f7bb2e46435ddf2768bcbb816f9d7e5c1a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371601"
---
# <a name="creating-stack-and-queue-collections"></a>Yığın ve Kuyruk Koleksiyonları Oluşturma

Bu makalede, MFC liste sınıflarından [yığınlar](#_core_stacks) ve [kuyruklar](#_core_queues)gibi diğer veri yapıları nasıl oluşturulacak açıklanmaktadır. `CList`Örnekler, türetilen sınıfları kullanır, `CList` ancak işlevsellik eklemeniz gerekmedikçe doğrudan kullanabilirsiniz.

## <a name="stacks"></a><a name="_core_stacks"></a>Yığın

Standart liste koleksiyonunun hem kafası hem de kuyruğu olduğundan, son gelen ilk çıkış yığınının davranışını taklit eden türetilmiş bir liste koleksiyonu oluşturmak kolaydır. Yığın, kafeteryadaki tepsi yığını gibidir. Tepsiler yığına eklendikçe, yığının üstüne giderler. Eklenen son tepsi ilk çıkarılacak. Liste toplama üye `AddHead` `RemoveHead` işlevleri ve eklemek ve özellikle listenin başından öğeleri kaldırmak için kullanılabilir; böylece, en son eklenen öğe ilk kaldırılan öğedir.

#### <a name="to-create-a-stack-collection"></a>Yığın koleksiyonu oluşturmak için

1. Varolan MFC liste sınıflarından birinden yeni bir liste sınıfı türetin ve yığın işlemlerinin işlevselliğini desteklemek için daha fazla üye işlev ekleyin.

   Aşağıdaki örnek, öğeleri yığına itmek, yığının üst öğesini gözetlemek ve üst öğeyi yığından çıkarmak için üye işlevlerin nasıl ekleyeceğini gösterir:

   [!code-cpp[NVC_MFCCollections#20](../mfc/codesnippet/cpp/creating-stack-and-queue-collections_1.h)]

Bu yaklaşımın temel `CObList` sınıfı ortaya çıkardığını unutmayın. Kullanıcı, bir `CObList` yığın için mantıklı olsun veya olmasın, herhangi bir üye işlevi arayabilir.

## <a name="queues"></a><a name="_core_queues"></a>Sıra

Standart liste koleksiyonunun hem kafası hem de kuyruğu olduğundan, ilk çıkan ilk sıranın davranışını taklit eden türetilmiş bir liste koleksiyonu oluşturmak da kolaydır. Sıra, kafeteryadaki bir sıra gibi. Sırada ilk kişi servis edilen ilk kişidir. Daha fazla insan geldikçe sıralarını beklemek için sıranın sonuna giderler. Liste toplama üye `AddTail` `RemoveHead` işlevleri ve eklemek ve özellikle listenin baş veya kuyruk öğeleri kaldırmak için kullanılabilir; böylece, en son eklenen öğe her zaman kaldırılacak son öğedir.

#### <a name="to-create-a-queue-collection"></a>Sıra koleksiyonu oluşturmak için

1. Microsoft Hazırlık Sınıfı Kitaplığı ile sağlanan önceden tanımlanmış liste sınıflarından birinden yeni bir liste sınıfı türetin ve sıra işlemlerinin anlambilimini desteklemek için daha fazla üye işlev ekleyin.

   Aşağıdaki örnek, sıranın sonuna bir öğe eklemek ve öğeyi sıranın önünden almak için üye işlevleri nasıl ekleyebileceğinizi gösterir.

   [!code-cpp[NVC_MFCCollections#21](../mfc/codesnippet/cpp/creating-stack-and-queue-collections_2.h)]

## <a name="see-also"></a>Ayrıca bkz.

[Koleksiyonlar](../mfc/collections.md)
