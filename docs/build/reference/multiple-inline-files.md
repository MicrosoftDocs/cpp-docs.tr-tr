---
description: 'Daha fazla bilgi: birden çok satır Içi dosya'
title: Birden Çok Satır İçi Dosya
ms.date: 11/04/2016
helpviewer_keywords:
- inline files, multiple NMAKE
- multiple inline files
- NMAKE program, inline files
ms.assetid: 6d381dcf-0ed8-45d1-8df3-b4598d860b99
ms.openlocfilehash: d739591910007f69eca5d4834f6943ae0a0082ed
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97190607"
---
# <a name="multiple-inline-files"></a>Birden Çok Satır İçi Dosya

Bir komut, birden fazla satır içi dosya oluşturabilir.

## <a name="syntax"></a>Syntax

```
command << <<
inlinetext
<<[KEEP | NOKEEP]
inlinetext
<<[KEEP | NOKEEP]
```

## <a name="remarks"></a>Açıklamalar

Her dosya için satır içi metnin bir veya daha fazla satırını ve ardından sınırlayıcıyı içeren bir kapanış satırını belirtin. İkinci dosyanın metnini ilk dosya için sınırlandırma satırını izleyen satırda başlatın.

## <a name="see-also"></a>Ayrıca bkz.

[Derleme görevleri dosyasındaki satır içi dosyalar](inline-files-in-a-makefile.md)
