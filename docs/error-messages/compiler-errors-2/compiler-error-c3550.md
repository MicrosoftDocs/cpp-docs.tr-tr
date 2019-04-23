---
title: Derleyici Hatası C3550
ms.date: 11/04/2016
f1_keywords:
- C3550
helpviewer_keywords:
- C3550
ms.assetid: 9f2d5ffc-e429-41a1-89e3-7acc4fd47e14
ms.openlocfilehash: 106ac93496eebb25ee603251d84680053e1310b7
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59032343"
---
# <a name="compiler-error-c3550"></a>Derleyici Hatası C3550

Bu bağlamda yalnızca düz 'decltype(auto)' kullanılabilir

Varsa `decltype(auto)` kullanılan işlevin dönüş türü için bir yer tutucu olarak, kendisi tarafından kullanılmalıdır. Bir işaretçi bildirimi bir parçası olarak kullanılamaz (`decltype(auto*)`), bir başvuru bildirimi (`decltype(auto&)`), veya tüm diğer tür nitelemesini.

## <a name="see-also"></a>Ayrıca bkz.

[auto](../../cpp/auto-cpp.md)