---
title: 'Seri hale getirme: Bir nesneyi seri hale getirme'
ms.date: 11/04/2016
helpviewer_keywords:
- serializing objects [MFC]
- serialization [MFC], objects
- objects [MFC], serializing
ms.assetid: 1db772b1-ad55-4fcf-b133-126cca082510
ms.openlocfilehash: 5c1106f180c587894283575a82a88e9e18b5c01a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62308049"
---
# <a name="serialization-serializing-an-object"></a>Seri hale getirme: Bir nesneyi seri hale getirme

Makaleyi [seri hale getirme: Seri hale getirilebilir bir sınıf yapma](../mfc/serialization-making-a-serializable-class.md) bir sınıf serileştirilebilir yapmak nasıl gösterir. Seri hale getirilebilir bir sınıf aldıktan sonra bir dosya gelen ve bu sınıfın nesneleri serileştirebilen bir [CArchive](../mfc/reference/carchive-class.md) nesne. Bu makalede açıklanmıştır:

- [CArchive nesnesi hangi](../mfc/what-is-a-carchive-object.md).

- [CArchive oluşturmanın iki yolu](../mfc/two-ways-to-create-a-carchive-object.md).

- [CArchive kullanmayı <\< ve >> işleçleri](../mfc/using-the-carchive-output-and-input-operators.md).

- [Depolama ve Arşiv CObjects yükleme](../mfc/storing-and-loading-cobjects-via-an-archive.md).

Seri hale getirilebilir belgeniz için arşiv veya açıkça oluşturmak framework sağlayabilirsiniz `CArchive` kendiniz nesne. Kullanarak bir dosya ile seri hale getirilebilir nesnenizin arasında veri aktarabilir <\< ve >> işleçleri `CArchive` veya çağırarak bağlı olarak, bazı durumlarda `Serialize` işlevi bir `CObject`-türetilmiş sınıf.

## <a name="see-also"></a>Ayrıca bkz.

[Serileştirme](../mfc/serialization-in-mfc.md)
