---
title: Dosyaları kapatma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC, file operations
- files [MFC], closing
ms.assetid: 8415a3a8-3c75-45b0-ac2a-d5385f49bdb3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9c392ef728e1d796a02cfa32edc2c3e8c74d083b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46426243"
---
# <a name="closing-files"></a>Dosyaları Kapatma

Bir dosya ile işiniz bittiğinde her zaman olduğu gibi g/ç işlemlerinde kapatmalısınız.

#### <a name="to-close-a-file"></a>Bir dosyayı kapatmak için

1. Kullanım **Kapat** üye işlevi. Bu işlev, dosya sistemi dosyayı kapatır ve gerekirse arabelleklerini boşaltır.

Ayırdığınızda, [CFile](../mfc/reference/cfile-class.md) çerçevesinde nesne (gösterilen örnekte olduğu gibi [dosyaları açma](../mfc/opening-files.md)), otomatik olarak nesne olacak kapatılmasını ve ardından kapsam dışına çıktığında yok. Bu silme Not `CFile` nesnesi dosya sistemindeki fiziksel dosya silinmez.

## <a name="see-also"></a>Ayrıca Bkz.

[Dosyalar](../mfc/files-in-mfc.md)

