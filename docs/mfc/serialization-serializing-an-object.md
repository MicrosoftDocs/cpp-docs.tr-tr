---
description: ': Serileştirme: bir nesneyi seri hale getirme hakkında daha fazla bilgi'
title: 'Seri hale getirme: Bir Nesneyi Seri Hale Getirme'
ms.date: 11/04/2016
helpviewer_keywords:
- serializing objects [MFC]
- serialization [MFC], objects
- objects [MFC], serializing
ms.assetid: 1db772b1-ad55-4fcf-b133-126cca082510
ms.openlocfilehash: ec0782f7faa0d6400f40013925f4a53495a76c7e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217483"
---
# <a name="serialization-serializing-an-object"></a>Seri hale getirme: Bir Nesneyi Seri Hale Getirme

Seri hale [getirme: seri hale getirilebilir bir sınıf](../mfc/serialization-making-a-serializable-class.md) oluşturma, bir sınıfın seri hale getirilebilir nasıl oluşturulacağını gösterir. Seri hale getirilebilir bir sınıfa sahip olduktan sonra, bu sınıfın nesnelerini bir [CArchive](../mfc/reference/carchive-class.md) nesnesi aracılığıyla bir dosyaya ve öğesinden seri hale getirebilirsiniz. Bu makalede şunları açıklanmaktadır:

- [CArchive nesnesi nedir?](../mfc/what-is-a-carchive-object.md)

- [CArchive oluşturmanın iki yolu](../mfc/two-ways-to-create-a-carchive-object.md).

- [CArchive <\< and >> işleçlerini kullanma](../mfc/using-the-carchive-output-and-input-operators.md).

- [CObjects bir arşiv aracılığıyla depolanıyor ve yükleniyor](../mfc/storing-and-loading-cobjects-via-an-archive.md).

Framework 'ün seri hale getirilebilir belgeniz için Arşiv oluşturmasına izin verebilir veya nesneyi doğrudan kendiniz oluşturabilirsiniz `CArchive` . Veya için <> işleçlerini kullanarak bir dosya ve seri hale getirilebilir nesneniz arasında verileri \< and > `CArchive` , bazı durumlarda, `Serialize` bir türetilmiş sınıfın işlevini çağırarak aktarabilirsiniz `CObject` .

## <a name="see-also"></a>Ayrıca bkz.

[Serileştirme](../mfc/serialization-in-mfc.md)
