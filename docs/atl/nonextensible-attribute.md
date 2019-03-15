---
title: nonextensible özniteliği
ms.date: 11/04/2016
helpviewer_keywords:
- nonextensible attribute
- dual interfaces, nonextensible attribute
ms.assetid: 02a4a18b-ffd3-4d53-8fd1-feb1c05ad5ac
ms.openlocfilehash: cc57acb8bd7bc3e32c764606da651f57316ceabf
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57811855"
---
# <a name="nonextensible-attribute"></a>nonextensible özniteliği

Çift arabirim çalışma zamanında genişletilir değil, (diğer bir deyişle, yöntemler veya özellikleri aracılığıyla sağlamayacak `IDispatch::Invoke` vtable kullanılabilir değildir), uygulamanız gerekir **nonextensible** arabiriminize özniteliği tanımı. Bu öznitelik (örneğin, Visual Basic) derleme zamanında tam kod doğrulamayı etkinleştirmek için kullanılan istemci dillerini bilgileri sağlar. Bu öznitelik sağlanmazsa, hataların çalışma zamanına kadar gizli istemci kodu kalabilir.

Daha fazla bilgi için **nonextensible** özniteliğini ve bir örnek görmek, [nonextensible](../windows/nonextensible.md).

## <a name="see-also"></a>Ayrıca bkz.

[Çift Arabirimler ve ATL](../atl/dual-interfaces-and-atl.md)
