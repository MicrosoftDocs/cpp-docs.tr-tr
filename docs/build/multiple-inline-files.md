---
title: Birden çok satır içi dosyalar | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- inline files, multiple NMAKE
- multiple inline files
- NMAKE program, inline files
ms.assetid: 6d381dcf-0ed8-45d1-8df3-b4598d860b99
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 87d68034c4f0018d65020915d24d0b5c2ec5d61a
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45725601"
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