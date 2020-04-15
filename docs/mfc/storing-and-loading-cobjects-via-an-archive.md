---
title: Bir Arşiv Kullanarak CObject'leri Depolama ve Yükleme
ms.date: 11/04/2016
helpviewer_keywords:
- CObjects [MFC], loading through archives
- CArchive class [MFC], storing and loading objects
- Serialize method, vs. CArchive operators
- CObject class [MFC], CArchive objects
- CObjects [MFC]
ms.assetid: a829b6dd-bc31-47e0-8108-fbb946722db9
ms.openlocfilehash: f1b59516d5bba13b6f5e006f91d8ebd560543b05
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372153"
---
# <a name="storing-and-loading-cobjects-via-an-archive"></a>Bir Arşiv Kullanarak CObject'leri Depolama ve Yükleme

Bir arşiv `CObject`üzerinden depolama ve yükleme ekstra dikkate gerektirir. Bazı `Serialize` durumlarda, `CArchive` nesnenin çağrının `Serialize` ** < ** bir parametresi olduğu nesnenin işlevini, `CArchive`'nin işlevini **>>** veya işlecinin yerine Akılda tutulması gereken önemli bir `CArchive` **>>** gerçek, `CObject` işleç daha `CRuntimeClass` önce depolama arşivi tarafından dosyaya yazılmış bilgilere dayalı bellek inşa olmasıdır.

Bu nedenle, aramayı `CArchive` ** < ** **>>** karşıklayarak `Serialize`ve kullanıp kullanmadığınız, nesneyi daha önce depolanan `CRuntimeClass` bilgilere göre dinamik olarak yeniden yapılandırmak için yükleme arşivine *ihtiyaç duyup* duymadığınıza bağlıdır. Aşağıdaki `Serialize` durumlarda işlevi kullanın:

- Nesneyi deserializing zaman, nesnenin tam sınıfını önceden biliyorum.

- Nesneyi deserializing, zaten bunun için ayrılmış bellek var.

> [!CAUTION]
> Nesneyi `Serialize` işlevi kullanarak yüklerseniz, `Serialize` nesneyi işlevi kullanarak da depolamanız gerekir. İşleç kullanarak `CArchive` **<<** depoyapmayın ve `Serialize` ardından işlevi kullanarak `Serialize` yükleyin veya `CArchive >>` işlevi kullanarak depolayın ve ardından operatörü kullanarak yükleyin.

Aşağıdaki örnek, servis taleplerini göstermektedir:

[!code-cpp[NVC_MFCSerialization#36](../mfc/codesnippet/cpp/storing-and-loading-cobjects-via-an-archive_1.h)]

[!code-cpp[NVC_MFCSerialization#37](../mfc/codesnippet/cpp/storing-and-loading-cobjects-via-an-archive_2.cpp)]

Özetle, `CObject` serileştirilebilir sınıfınız katıştirilen bir nesneyi tanımlıyorsa, o nesne için `CArchive` ** < ** **>>** ve `Serialize` işleçleri *kullanmamalısınız,* bunun yerine işlevi aramalısınız. Ayrıca, serializable sınıf bir işaretçi `CObject` (veya türetilen `CObject`bir nesne) bir üye olarak tanımlar, ancak kendi oluşturucu `Serialize`bu diğer nesne inşa ederse, ayrıca çağırmalısınız.

## <a name="see-also"></a>Ayrıca bkz.

[Seri hale getirme: Bir Nesneyi Seri Hale Getirme](../mfc/serialization-serializing-an-object.md)
