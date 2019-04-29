---
title: Dosyaları Kapatma
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, file operations
- files [MFC], closing
ms.assetid: 8415a3a8-3c75-45b0-ac2a-d5385f49bdb3
ms.openlocfilehash: 69a0960c1edabab00cb71702acda526ee9ebd798
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62326930"
---
# <a name="closing-files"></a>Dosyaları Kapatma

Bir dosya ile işiniz bittiğinde her zaman olduğu gibi g/ç işlemlerinde kapatmalısınız.

#### <a name="to-close-a-file"></a>Bir dosyayı kapatmak için

1. Kullanım **Kapat** üye işlevi. Bu işlev, dosya sistemi dosyayı kapatır ve gerekirse arabelleklerini boşaltır.

Ayırdığınızda, [CFile](../mfc/reference/cfile-class.md) çerçevesinde nesne (gösterilen örnekte olduğu gibi [dosyaları açma](../mfc/opening-files.md)), otomatik olarak nesne olacak kapatılmasını ve ardından kapsam dışına çıktığında yok. Bu silme Not `CFile` nesnesi dosya sistemindeki fiziksel dosya silinmez.

## <a name="see-also"></a>Ayrıca bkz.

[Dosyalar](../mfc/files-in-mfc.md)
