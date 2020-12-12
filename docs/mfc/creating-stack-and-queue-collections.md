---
description: 'Daha fazla bilgi edinin: yığın ve kuyruk koleksiyonları oluşturma'
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
ms.openlocfilehash: e6c3d4a2ade4262e01bd5d84529aa57d308a8623
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97309777"
---
# <a name="creating-stack-and-queue-collections"></a>Yığın ve Kuyruk Koleksiyonları Oluşturma

Bu makalede, MFC liste sınıflarından [yığınlar](#_core_stacks) ve [Kuyruklar](#_core_queues)gibi diğer veri yapılarının nasıl oluşturulduğu açıklanmaktadır. Örnekler, ' den türetilen sınıfları kullanır `CList` , ancak `CList` işlevsellik eklemeniz gerekmiyorsa doğrudan kullanabilirsiniz.

## <a name="stacks"></a><a name="_core_stacks"></a> Lara

Standart liste koleksiyonunda hem baş hem de kuyruk olduğundan, bir son ilk çıkar yığınının davranışını taklit eden bir türetilmiş liste koleksiyonu oluşturmak kolaydır. Bir yığın, Cafeteria 'daki tepsilerden oluşan bir yığın gibidir. Yığına tepsi eklendikçe, yığının en üstüne gitirler. Eklenen son tepsi, kaldırılacak ilkdir. Liste koleksiyonu üyesi işlevleri, `AddHead` `RemoveHead` özellikle listenin baş bir yanındaki öğeleri eklemek ve kaldırmak için kullanılabilir; Bu nedenle, en son eklenen öğe kaldırılacak ilk öğedir.

#### <a name="to-create-a-stack-collection"></a>Yığın koleksiyonu oluşturmak için

1. Mevcut MFC liste sınıflarından birinden yeni bir liste sınıfı türetirsiniz ve yığın işlemlerinin işlevlerini desteklemek için daha fazla üye işlevi ekleyin.

   Aşağıdaki örnek, yığın üzerinde öğelerine gönderme yapmak için üye işlevlerinin nasıl ekleneceğini, yığının en üst öğesine nasıl göz atmayı ve yığından en üstteki öğeyi eklemeyi gösterir:

   [!code-cpp[NVC_MFCCollections#20](codesnippet/cpp/creating-stack-and-queue-collections_1.h)]

Bu yaklaşımın temel sınıfı kullanıma sunduğunu unutmayın `CObList` . Kullanıcı herhangi `CObList` bir üye işlevi çağırabilir, bu, yığın için anlamlı hale getirir.

## <a name="queues"></a><a name="_core_queues"></a> Klarında

Standart liste koleksiyonunda hem baş hem de kuyruk olduğundan, ilk çıkar sırasının davranışını taklit eden bir türetilmiş liste koleksiyonu oluşturmak da kolaydır. Kuyruk, Cafeteria 'daki bir kişi satırı gibidir. Satırdaki ilk kişi, sunulacak ilk kişidir. Daha fazla kişi geldiklerinde, onların dönmesini beklemek için satırın sonuna gider. Liste koleksiyonu üyesi işlevleri, `AddTail` `RemoveHead` özellikle de listenin baş veya kuyruklu öğeleri eklemek ve kaldırmak için kullanılabilir; Bu nedenle, en son eklenen öğe her zaman kaldırılacak en son öğedir.

#### <a name="to-create-a-queue-collection"></a>Kuyruk koleksiyonu oluşturmak için

1. Microsoft Foundation Class Kitaplığı ile birlikte sunulan önceden tanımlanmış liste sınıflarından birinden yeni bir liste sınıfı türetebilir ve sıra işlemlerinin semantiğini desteklemek için daha fazla üye işlevi ekleyin.

   Aşağıdaki örnek, sıranın sonuna bir öğesi eklemek ve sıranın önüne öğe almak için üye işlevlerinin nasıl ekleneceğini gösterir.

   [!code-cpp[NVC_MFCCollections#21](codesnippet/cpp/creating-stack-and-queue-collections_2.h)]

## <a name="see-also"></a>Ayrıca bkz.

[Koleksiyonlar](collections.md)
