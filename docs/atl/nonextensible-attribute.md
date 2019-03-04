---
title: nonextensible özniteliği
ms.date: 11/04/2016
f1_keywords:
- nonextensible
helpviewer_keywords:
- nonextensible attribute
- dual interfaces, nonextensible attribute
ms.assetid: 02a4a18b-ffd3-4d53-8fd1-feb1c05ad5ac
ms.openlocfilehash: 5aa5b8514435e9876500daa4d92504d75eb6dc23
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57257637"
---
# <a name="nonextensible-attribute"></a>nonextensible özniteliği

Çift arabirim çalışma zamanında genişletilir değil, (diğer bir deyişle, yöntemler veya özellikleri aracılığıyla sağlamayacak `IDispatch::Invoke` vtable kullanılabilir değildir), uygulamanız gerekir **nonextensible** arabiriminize özniteliği tanımı. Bu öznitelik (örneğin, Visual Basic) derleme zamanında tam kod doğrulamayı etkinleştirmek için kullanılan istemci dillerini bilgileri sağlar. Bu öznitelik sağlanmazsa, hataların çalışma zamanına kadar gizli istemci kodu kalabilir.

Daha fazla bilgi için **nonextensible** özniteliğini ve bir örnek görmek, [nonextensible](../windows/nonextensible.md).

## <a name="see-also"></a>Ayrıca bkz.

[Çift Arabirimler ve ATL](../atl/dual-interfaces-and-atl.md)
