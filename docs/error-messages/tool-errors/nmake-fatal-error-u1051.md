---
title: NMAKE önemli hatası U1051 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1051
dev_langs:
- C++
helpviewer_keywords:
- U1051
ms.assetid: fede5cd5-dac3-47b7-b86d-e1acfb78699f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d3d3a14b75a30aa22bcc9faafb97a218051bb080
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46045022"
---
# <a name="nmake-fatal-error-u1051"></a>NMAKE Önemli Hatası U1051

Bellek yetersiz

NMAKE derleme görevleri dosyası çok büyük veya karmaşık olduğundan, sanal bellek dahil olmak üzere, bellek yetersiz kaldı.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>Aşağıdaki olası çözümleri kullanarak düzeltmek için

1. Disk üzerinde biraz alan boşaltın.

1. Windows NT disk belleği dosyası ya da Windows takas dosyası boyutunu artırın.

1. Yalnızca derleme görevleri dosyası parçası kullanılan derleme görevleri dosyası ayrı dosyalara bölün veya kullanın **! Eğer** ön işleme NMAKE işlemelisiniz tutarını sınırlamak için yönergeleri. **! Eğer** yönergelerinde **! Eğer**, `!IFDEF`, **! IFNDEF**, **! ELSE IF**, **! BAŞKA** `IFDEF`, ve **! BAŞKA** `IFNDEF`.