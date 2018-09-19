---
title: Derleyici Uyarısı (Düzey 2 ve 3) C4008 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4008
dev_langs:
- C++
helpviewer_keywords:
- C4008
ms.assetid: fb45e535-cb68-4743-80e9-a6e34cfffeca
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bd052b8dd6a0b70dd90ca076d0085675b33dc621
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46091185"
---
# <a name="compiler-warning-levels-2-and-3-c4008"></a>Derleyici Uyarısı (Düzey 2 ve 3) C4008

'identifier': 'öznitelik' özniteliği yoksayıldı

Derleyicinin göz ardı `__fastcall`, **statik**, veya **satır içi** işlevi (uyarı Düzey 3) veya veri (uyarı Düzey 2) için özniteliği.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri kontrol ederek düzeltmek için

1. `__fastcall` verilerle özniteliği.

1. **statik** veya **satır içi** özniteliğini **ana** işlevi.