---
description: 'Daha fazla bilgi edinin: ATL bağlantı noktası örneği'
title: ATL bağlantı noktası örneği
ms.date: 11/04/2016
helpviewer_keywords:
- connection points [C++], examples
- examples [ATL]
ms.assetid: a49721b7-f308-43de-8868-f662a94bc81a
ms.openlocfilehash: 6416720b5366838f9687f31947cac9a6824da058
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97165816"
---
# <a name="atl-connection-point-example"></a>ATL bağlantı noktası örneği

Bu örnek, bir giden arabirim olarak [IPropertyNotifySink](/windows/win32/api/ocidl/nn-ocidl-ipropertynotifysink) destekleyen bir nesne gösterir:

[!code-cpp[NVC_ATL_Windowing#84](../atl/codesnippet/cpp/atl-connection-point-example_1.h)]

`IPropertyNotifySink`Giden arabirim olarak belirtirken, yerine [IPropertyNotifySinkCP](../atl/reference/ipropertynotifysinkcp-class.md) sınıfını kullanabilirsiniz `IConnectionPointImpl` . Örneğin:

[!code-cpp[NVC_ATL_Windowing#85](../atl/codesnippet/cpp/atl-connection-point-example_2.h)]

## <a name="see-also"></a>Ayrıca bkz.

[Bağlantı noktası](../atl/atl-connection-points.md)
