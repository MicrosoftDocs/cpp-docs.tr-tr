---
title: Birden Çok Satır İçi Dosya
ms.date: 11/04/2016
helpviewer_keywords:
- inline files, multiple NMAKE
- multiple inline files
- NMAKE program, inline files
ms.assetid: 6d381dcf-0ed8-45d1-8df3-b4598d860b99
ms.openlocfilehash: ec531e5716098725782010927201ef57e2a8aa24
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50558164"
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

## <a name="see-also"></a>Ayrıca Bkz.

[Derleme Görevleri Dosyasındaki Satır İçi Dosyalar](../build/inline-files-in-a-makefile.md)