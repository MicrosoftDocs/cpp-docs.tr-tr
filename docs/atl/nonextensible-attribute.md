---
title: nonextensible özniteliği | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- nonextensible
dev_langs:
- C++
helpviewer_keywords:
- nonextensible attribute
- dual interfaces, nonextensible attribute
ms.assetid: 02a4a18b-ffd3-4d53-8fd1-feb1c05ad5ac
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 73edae463051aca3ecafac53ae6200df103b8d90
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43762147"
---
# <a name="nonextensible-attribute"></a>nonextensible özniteliği

Çift arabirim çalışma zamanında genişletilir değil, (diğer bir deyişle, yöntemler veya özellikleri aracılığıyla sağlamayacak `IDispatch::Invoke` vtable kullanılabilir değildir), uygulamanız gerekir **nonextensible** arabiriminize özniteliği tanımı. Bu öznitelik (örneğin, Visual Basic) derleme zamanında tam kod doğrulamayı etkinleştirmek için kullanılan istemci dillerini bilgileri sağlar. Bu öznitelik sağlanmazsa, hataların çalışma zamanına kadar gizli istemci kodu kalabilir.

Daha fazla bilgi için **nonextensible** özniteliğini ve bir örnek görmek, [nonextensible](../windows/nonextensible.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Çift Arabirimler ve ATL](../atl/dual-interfaces-and-atl.md)

