---
title: Derleyici hatası C3550
ms.date: 11/04/2016
f1_keywords:
- C3550
helpviewer_keywords:
- C3550
ms.assetid: 9f2d5ffc-e429-41a1-89e3-7acc4fd47e14
ms.openlocfilehash: 17c90aa68b29c9490deb8d49895162e8a6bdefec
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80200778"
---
# <a name="compiler-error-c3550"></a>Derleyici hatası C3550

Bu bağlamda yalnızca düz ' decltype (Auto) ' kullanılabilir

Bir işlevin dönüş türü için bir yer tutucu olarak `decltype(auto)` kullanılırsa, kendisi tarafından kullanılmalıdır. Bir işaretçi bildiriminin (`decltype(auto*)`) bir parçası olarak, bir başvuru bildirimi (`decltype(auto&)`) veya başka bir nitelik gibi kullanılamaz.

## <a name="see-also"></a>Ayrıca bkz.

[auto](../../cpp/auto-cpp.md)
