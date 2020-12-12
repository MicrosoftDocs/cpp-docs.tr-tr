---
description: 'Daha fazla bilgi edinin: dosyaları kapatma'
title: Dosyaları Kapatma
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, file operations
- files [MFC], closing
ms.assetid: 8415a3a8-3c75-45b0-ac2a-d5385f49bdb3
ms.openlocfilehash: e8d2f0792aeb889c40cb516af259fc2a40890a1a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338381"
---
# <a name="closing-files"></a>Dosyaları Kapatma

G/ç işlemlerinde her zamanki gibi, bir dosyayla bittikten sonra kapatmanız gerekir.

#### <a name="to-close-a-file"></a>Bir dosyayı kapatmak için

1. **Close** üye işlevini kullanın. Bu işlev, gerekirse dosya sistemi dosyasını ve Temizleme arabelleklerini kapatır.

[CFile](reference/cfile-class.md) nesnesini çerçevede ayırdıysanız ( [dosyaları açma](opening-files.md)bölümünde gösterilen örnekte olduğu gibi), nesne otomatik olarak kapatılıp, kapsam dışına geçtiğinde yok edilir. `CFile`Nesne silmenin dosya sistemindeki fiziksel dosyayı silmediğini unutmayın.

## <a name="see-also"></a>Ayrıca bkz.

[Dosyalar](files-in-mfc.md)
