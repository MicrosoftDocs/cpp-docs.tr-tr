---
title: Genişletilebilir olmayan öznitelik
ms.date: 11/04/2016
helpviewer_keywords:
- nonextensible attribute
- dual interfaces, nonextensible attribute
ms.assetid: 02a4a18b-ffd3-4d53-8fd1-feb1c05ad5ac
ms.openlocfilehash: fda2a0d43144b6e9832e061e7198b3f3e65f8b86
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91500110"
---
# <a name="nonextensible-attribute"></a>Genişletilebilir olmayan öznitelik

Bir çift arabirim çalışma zamanında uzatılmazsa (yani, vtable aracılığıyla kullanılamayan yöntemleri veya özellikleri sağlamadıysanız `IDispatch::Invoke` ), arabirim tanımınıza **genişletilemez** özniteliği uygulamanız gerekir. Bu öznitelik, derleme zamanında tam kod doğrulamasını etkinleştirmek için kullanılabilen istemci dilleri (örneğin, Visual Basic) için bilgiler sağlar. Bu öznitelik sağlanmazsa, hatalar çalışma zamanına kadar istemci kodunda gizli kalabiliyor.

**Genişletilebilir olmayan** öznitelik ve bir örnek hakkında daha fazla bilgi için bkz. [Genişletilebilir olmayan](../windows/attributes/nonextensible.md).

## <a name="see-also"></a>Ayrıca bkz.

[Çift arabirimler ve ATL](../atl/dual-interfaces-and-atl.md)
