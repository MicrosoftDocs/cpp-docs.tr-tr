---
description: 'Daha fazla bilgi edinin: Genişletilebilir olmayan öznitelik'
title: Genişletilebilir olmayan öznitelik
ms.date: 11/04/2016
helpviewer_keywords:
- nonextensible attribute
- dual interfaces, nonextensible attribute
ms.assetid: 02a4a18b-ffd3-4d53-8fd1-feb1c05ad5ac
ms.openlocfilehash: 5bad214d6688570bc4a69aca952f6bed98c2b0dc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97159407"
---
# <a name="nonextensible-attribute"></a>Genişletilebilir olmayan öznitelik

Bir çift arabirim çalışma zamanında uzatılmazsa (yani, vtable aracılığıyla kullanılamayan yöntemleri veya özellikleri sağlamadıysanız `IDispatch::Invoke` ), arabirim tanımınıza **genişletilemez** özniteliği uygulamanız gerekir. Bu öznitelik, derleme zamanında tam kod doğrulamasını etkinleştirmek için kullanılabilen istemci dilleri (örneğin, Visual Basic) için bilgiler sağlar. Bu öznitelik sağlanmazsa, hatalar çalışma zamanına kadar istemci kodunda gizli kalabiliyor.

**Genişletilebilir olmayan** öznitelik ve bir örnek hakkında daha fazla bilgi için bkz. [Genişletilebilir olmayan](../windows/attributes/nonextensible.md).

## <a name="see-also"></a>Ayrıca bkz.

[Çift arabirimler ve ATL](../atl/dual-interfaces-and-atl.md)
