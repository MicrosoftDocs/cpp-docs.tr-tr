---
title: Arama yolları için Bağımlılara | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, dependents
- dependents, NMAKE
ms.assetid: bf998e47-da74-48b5-891d-d3d8ce57264b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d1fd407f99abb98fb949b6d5bcc45b10c6ff9121
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45706322"
---
# <a name="search-paths-for-dependents"></a>Bağımlılıklar için Yollar Ara

Her bağlı gibi belirtilen bir isteğe bağlı arama yolu vardır:

## <a name="syntax"></a>Sözdizimi

```
{directory[;directory...]}dependent
```

## <a name="remarks"></a>Açıklamalar

NMAKE bağımlı bir geçerli dizin ilk olarak ve belirtilen sırada dizinde arar. Makro bölümünü veya tümünü bir arama yolu belirtebilirsiniz. Dizin adları ({}); küme ayraçları içine alın. birden çok dizin, noktalı virgül (;) ayırın. Boşluk veya sekme izin verilir.

## <a name="see-also"></a>Ayrıca Bkz.

[Bağımlılıklar](../build/dependents.md)