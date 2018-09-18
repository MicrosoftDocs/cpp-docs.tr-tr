---
title: Derleyici Hatası C3550 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3550
dev_langs:
- C++
helpviewer_keywords:
- C3550
ms.assetid: 9f2d5ffc-e429-41a1-89e3-7acc4fd47e14
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 08c22d7e371fda7a229b541f78d4385f2943ee54
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46047791"
---
# <a name="compiler-error-c3550"></a>Derleyici Hatası C3550

Bu bağlamda yalnızca düz 'decltype(auto)' kullanılabilir

Varsa `decltype(auto)` kullanılan işlevin dönüş türü için bir yer tutucu olarak, kendisi tarafından kullanılmalıdır. Bir işaretçi bildirimi bir parçası olarak kullanılamaz (`decltype(auto*)`), bir başvuru bildirimi (`decltype(auto&)`), veya tüm diğer tür nitelemesini.

## <a name="see-also"></a>Ayrıca Bkz.

[auto](../../cpp/auto-cpp.md)