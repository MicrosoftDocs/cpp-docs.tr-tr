---
title: Derleyici Hatası C3550
ms.date: 11/04/2016
f1_keywords:
- C3550
helpviewer_keywords:
- C3550
ms.assetid: 9f2d5ffc-e429-41a1-89e3-7acc4fd47e14
ms.openlocfilehash: dbed14b9f2fa0f2163484edd8b5dfa330af9cbf1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50498893"
---
# <a name="compiler-error-c3550"></a>Derleyici Hatası C3550

Bu bağlamda yalnızca düz 'decltype(auto)' kullanılabilir

Varsa `decltype(auto)` kullanılan işlevin dönüş türü için bir yer tutucu olarak, kendisi tarafından kullanılmalıdır. Bir işaretçi bildirimi bir parçası olarak kullanılamaz (`decltype(auto*)`), bir başvuru bildirimi (`decltype(auto&)`), veya tüm diğer tür nitelemesini.

## <a name="see-also"></a>Ayrıca Bkz.

[auto](../../cpp/auto-cpp.md)