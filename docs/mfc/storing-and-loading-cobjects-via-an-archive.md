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
ms.openlocfilehash: 368421a86d6ff6fc70455edd0ea9a32e05645007
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79446369"
---
# <a name="storing-and-loading-cobjects-via-an-archive"></a>Bir Arşiv Kullanarak CObject'leri Depolama ve Yükleme

`CObject`s 'yi bir arşiv aracılığıyla depolamak ve yüklemek ek bir değerlendirme gerektirir. Belirli durumlarda, \< **<>>** veya **`CArchive`** işlecini kullanmanın aksine, `CArchive` nesnesinin `Serialize` çağrısının bir parametresi olduğu nesnenin `Serialize` işlevini çağırmanız gerekir. Göz önünde bulundurmanız gereken önemli olgu, `CArchive` **>>** işlecinin, daha önce depolayan Arşiv tarafından dosyaya yazılmış `CRuntimeClass` bilgilere göre bellekte `CObject` oluşturmasıdır.

Bu nedenle, `CArchive` **<\<** ve **>>** işleçlerini (`Serialize`çağırarak) kullandığınızda, daha önce depolanan `CRuntimeClass` bilgilerine göre nesneyi dinamik olarak yeniden oluşturmak için yükleme arşivine *ihtiyacınız* olup olmamasına bağlıdır. Aşağıdaki durumlarda `Serialize` işlevini kullanın:

- Nesne seri durumdan çıkarılırken, önceden nesnenin tam sınıfını bilirsiniz.

- Nesne seri durumdan çıkarılırken, zaten ayrılan belleğe sahip olursunuz.

> [!CAUTION]
>  Nesneyi `Serialize` işlevini kullanarak yüklerseniz, nesneyi `Serialize` işlevini kullanarak da depolamanız gerekir. `CArchive` **<<** işlecini kullanarak depolamayın, sonra `Serialize` işlevini kullanarak yükleyin veya `Serialize` işlevini kullanarak ve sonra `CArchive >>` işlecini kullanarak yükleyin.

Aşağıdaki örnekte durumlar gösterilmektedir:

[!code-cpp[NVC_MFCSerialization#36](../mfc/codesnippet/cpp/storing-and-loading-cobjects-via-an-archive_1.h)]

[!code-cpp[NVC_MFCSerialization#37](../mfc/codesnippet/cpp/storing-and-loading-cobjects-via-an-archive_2.cpp)]

Özet olarak, seri hale getirilebilir sınıfınız bir üye olarak gömülü bir `CObject` tanımlıyorsa, bu nesne için `CArchive` **<\<** ve **>>** *işleçlerini kullanmamalısınız,* ancak bunun yerine `Serialize` işlevini çağırmalıdır. Ayrıca, seri hale getirilebilir sınıfınız üye olarak bir `CObject` (veya `CObject`öğesinden türetilmiş bir nesne) için bir işaretçi tanımlıyorsa, ancak bu nesneyi kendi oluşturucusunda oluşturur, ayrıca `Serialize`' yı da çağırmanız gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[Seri hale getirme: Bir Nesneyi Seri Hale Getirme](../mfc/serialization-serializing-an-object.md)
