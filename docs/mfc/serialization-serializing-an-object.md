---
title: 'Seri hale getirme: Bir Nesneyi Seri Hale Getirme'
ms.date: 11/04/2016
helpviewer_keywords:
- serializing objects [MFC]
- serialization [MFC], objects
- objects [MFC], serializing
ms.assetid: 1db772b1-ad55-4fcf-b133-126cca082510
ms.openlocfilehash: 10a7c52e6187f4db8345e1eadb88faeefa50b419
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50588532"
---
# <a name="serialization-serializing-an-object"></a>Seri hale getirme: Bir Nesneyi Seri Hale Getirme

Makaleyi [seri hale getirme: seri hale getirilebilir bir sınıf yapma](../mfc/serialization-making-a-serializable-class.md) bir sınıf serileştirilebilir yapmak nasıl gösterir. Seri hale getirilebilir bir sınıf aldıktan sonra bir dosya gelen ve bu sınıfın nesneleri serileştirebilen bir [CArchive](../mfc/reference/carchive-class.md) nesne. Bu makalede açıklanmıştır:

- [CArchive nesnesi hangi](../mfc/what-is-a-carchive-object.md).

- [CArchive oluşturmanın iki yolu](../mfc/two-ways-to-create-a-carchive-object.md).

- [CArchive kullanmayı <\< ve >> işleçleri](../mfc/using-the-carchive-output-and-input-operators.md).

- [Depolama ve Arşiv CObjects yükleme](../mfc/storing-and-loading-cobjects-via-an-archive.md).

Seri hale getirilebilir belgeniz için arşiv veya açıkça oluşturmak framework sağlayabilirsiniz `CArchive` kendiniz nesne. Kullanarak bir dosya ile seri hale getirilebilir nesnenizin arasında veri aktarabilir <\< ve >> işleçleri `CArchive` veya çağırarak bağlı olarak, bazı durumlarda `Serialize` işlevi bir `CObject`-türetilmiş sınıf.

## <a name="see-also"></a>Ayrıca Bkz.

[Serileştirme](../mfc/serialization-in-mfc.md)

