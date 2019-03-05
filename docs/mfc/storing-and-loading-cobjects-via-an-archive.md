---
title: Bir Arşiv Kullanarak CObject'leri Depolama ve Yükleme
ms.date: 11/04/2016
f1_keywords:
- CObject
helpviewer_keywords:
- CObjects [MFC], loading through archives
- CArchive class [MFC], storing and loading objects
- Serialize method, vs. CArchive operators
- CObject class [MFC], CArchive objects
- CObjects [MFC]
ms.assetid: a829b6dd-bc31-47e0-8108-fbb946722db9
ms.openlocfilehash: 591ce7032aa3d70b1e5a020cd9173ed4c9d0fa9b
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57299952"
---
# <a name="storing-and-loading-cobjects-via-an-archive"></a>Bir Arşiv Kullanarak CObject'leri Depolama ve Yükleme

Depolama ve yükleme `CObject`s bir arşiv aracılığıyla ek göz önünde bulundurarak gerektirir. Bazı durumlarda, çağırması gerekir `Serialize` nesnenin işlevi burada `CArchive` nesnedir parametre `Serialize` sınıfını kullanarak çağrısı **< \<** veya **>>** işleci `CArchive`. Akılda tutulması gereken önemli olgu olan `CArchive` **>>** işleci yapıları `CObject` göre bellekte `CRuntimeClass` bilgi dosyasına depolanmasını arşiv tarafından önceden yazılmış.

Kullanıp bu nedenle, `CArchive` **< \<** ve **>>** çağırmak yerine, işleçler `Serialize`, bağlıdır, *gereksinim* Arşiv yüklenirken nesneye dinamik olarak yeniden oluşturmak için temel alarak daha önce depolanan `CRuntimeClass` bilgileri. Kullanım `Serialize` işlevi aşağıdaki durumlarda:

- Nesneyi seri durumdan çıkarmak olduğunda, tam nesnenin sınıfını önceden bilmeniz.

- Nesneyi seri durumdan çıkarmak olduğunda, kendisi için ayrılan bellek zaten sahip.

> [!CAUTION]
>  Nesnesini kullanarak yüklerseniz `Serialize` işlevi nesnesini kullanarak depolamalısınız `Serialize` işlevi. Kullanarak depolama `CArchive` **<<** işleci ve sonra Yük kullanarak `Serialize` işlev veya deposunda `Serialize` işlevi ve ardından kullanarak yük `CArchive >>` işleci.

Aşağıdaki örnek durumları gösterir:

[!code-cpp[NVC_MFCSerialization#36](../mfc/codesnippet/cpp/storing-and-loading-cobjects-via-an-archive_1.h)]

[!code-cpp[NVC_MFCSerialization#37](../mfc/codesnippet/cpp/storing-and-loading-cobjects-via-an-archive_2.cpp)]

Özet olarak, seri hale getirilebilir bir sınıf katıştırılmış tanımlıyorsa, `CObject` bir üyesi olarak gerektiğini *değil* kullanın `CArchive` **< \<** ve **>>** işleçleri söz konusu nesnenin ancak çağırmalıdır `Serialize` işlevini. Ayrıca, seri hale getirilebilir bir sınıf için bir işaretçi tanımlıyorsa bir `CObject` (veya bir nesne öğesinden türetilen `CObject`) üyesi, ancak yapıları kendi Oluşturucusu bu diğer nesne de çağırmanız gerekir `Serialize`.

## <a name="see-also"></a>Ayrıca bkz.

[Seri hale getirme: Bir nesneyi seri hale getirme](../mfc/serialization-serializing-an-object.md)
