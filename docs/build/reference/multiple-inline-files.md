---
title: Birden Çok Satır İçi Dosya
ms.date: 11/04/2016
helpviewer_keywords:
- inline files, multiple NMAKE
- multiple inline files
- NMAKE program, inline files
ms.assetid: 6d381dcf-0ed8-45d1-8df3-b4598d860b99
ms.openlocfilehash: 71f17ff6717e717693facb21b4a4341a040b14c1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62320597"
---
# <a name="multiple-inline-files"></a>Birden Çok Satır İçi Dosya

Bir komutu birden fazla satır içi dosya oluşturabilirsiniz.

## <a name="syntax"></a>Sözdizimi

```
command << <<
inlinetext
<<[KEEP | NOKEEP]
inlinetext
<<[KEEP | NOKEEP]
```

## <a name="remarks"></a>Açıklamalar

Her dosya için satır içi metin sınırlayıcısı içeren bir kapanış satır tarafından izlenen bir veya daha fazla satır belirtin. İlk dosya sınırlandırma satırı aşağıdaki satırdaki ikinci dosyanın metin başlayın.

## <a name="see-also"></a>Ayrıca bkz.

[Derleme Görevleri Dosyasındaki Satır İçi Dosyalar](inline-files-in-a-makefile.md)
