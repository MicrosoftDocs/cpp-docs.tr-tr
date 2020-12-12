---
description: 'Hakkında daha fazla bilgi edinin: bir arşiv aracılığıyla CObjects depolama ve yükleme'
title: Bir Arşiv Kullanarak CObject'leri Depolama ve Yükleme
ms.date: 11/04/2016
helpviewer_keywords:
- CObjects [MFC], loading through archives
- CArchive class [MFC], storing and loading objects
- Serialize method, vs. CArchive operators
- CObject class [MFC], CArchive objects
- CObjects [MFC]
ms.assetid: a829b6dd-bc31-47e0-8108-fbb946722db9
ms.openlocfilehash: c84c507fc556268eea526c1350211fd4b82f54fe
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216567"
---
# <a name="storing-and-loading-cobjects-via-an-archive"></a>Bir Arşiv Kullanarak CObject'leri Depolama ve Yükleme

`CObject`Bir arşiv aracılığıyla depolamak ve yüklemek ek bir değerlendirme gerektirir. Belirli durumlarda, nesnesinin `Serialize` `CArchive` işlecini kullanmanın aksine nesnenin, çağrının bir parametresi olduğu nesne işlevini çağırmanız gerekir `Serialize` **<\<** or **>>** `CArchive` . Göz önünde bulundurmanız gereken önemli olgu, `CArchive` **>>** işlecin `CObject` `CRuntimeClass` depolama arşivi tarafından daha önce dosyaya yazılmış bilgilere göre bellek içinde oluşturmasıdır.

Bu nedenle, işleçlerini ve çağrılmasını kullanarak, `CArchive` **<\<** and **>>** `Serialize` daha önce depolanan bilgilere göre nesneyi dinamik olarak yeniden oluşturmak için yükleme arşivine *ihtiyacınız* olup olmamasına bağlıdır `CRuntimeClass` . `Serialize`Aşağıdaki durumlarda işlevini kullanın:

- Nesne seri durumdan çıkarılırken, önceden nesnenin tam sınıfını bilirsiniz.

- Nesne seri durumdan çıkarılırken, zaten ayrılan belleğe sahip olursunuz.

> [!CAUTION]
> Nesnesini işlevini kullanarak yüklerseniz `Serialize` , işlevini kullanarak da nesneyi depolamanız gerekir `Serialize` . İşlecini kullanarak depolamayın `CArchive` **<<** ve sonra işlevini kullanarak yükleyin `Serialize` veya `Serialize` işlevini kullanarak ve sonra `CArchive >>` işlecini kullanarak yükleyin.

Aşağıdaki örnekte durumlar gösterilmektedir:

[!code-cpp[NVC_MFCSerialization#36](../mfc/codesnippet/cpp/storing-and-loading-cobjects-via-an-archive_1.h)]

[!code-cpp[NVC_MFCSerialization#37](../mfc/codesnippet/cpp/storing-and-loading-cobjects-via-an-archive_2.cpp)]

Özet olarak, seri hale getirilebilir sınıfınız bir üye olarak gömülü bir öğesi tanımlarsa, `CObject`  `CArchive` **<\<** and **>>** Bu nesne için İşleçleri kullanmamalısınız, ancak `Serialize` bunun yerine işlevi çağırmalıdır. Ayrıca, seri hale getirilebilir sınıfınız bir `CObject` üye olarak (veya öğesinden türetilmiş bir nesne) için bir işaretçi tanımlıyorsa `CObject` , ancak bu nesneyi kendi oluşturucusunda oluşturur, öğesini de çağırmalısınız `Serialize` .

## <a name="see-also"></a>Ayrıca bkz.

[Serileştirme: bir nesneyi seri hale getirme](../mfc/serialization-serializing-an-object.md)
