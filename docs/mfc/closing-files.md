---
title: Dosyaları Kapatma
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, file operations
- files [MFC], closing
ms.assetid: 8415a3a8-3c75-45b0-ac2a-d5385f49bdb3
ms.openlocfilehash: 51e51c88260a51ec44f11ecb5c2a88e645194f4e
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84617229"
---
# <a name="closing-files"></a>Dosyaları Kapatma

G/ç işlemlerinde her zamanki gibi, bir dosyayla bittikten sonra kapatmanız gerekir.

#### <a name="to-close-a-file"></a>Bir dosyayı kapatmak için

1. **Close** üye işlevini kullanın. Bu işlev, gerekirse dosya sistemi dosyasını ve Temizleme arabelleklerini kapatır.

[CFile](reference/cfile-class.md) nesnesini çerçevede ayırdıysanız ( [dosyaları açma](opening-files.md)bölümünde gösterilen örnekte olduğu gibi), nesne otomatik olarak kapatılıp, kapsam dışına geçtiğinde yok edilir. `CFile`Nesne silmenin dosya sistemindeki fiziksel dosyayı silmediğini unutmayın.

## <a name="see-also"></a>Ayrıca bkz.

[Dosyalar](files-in-mfc.md)
