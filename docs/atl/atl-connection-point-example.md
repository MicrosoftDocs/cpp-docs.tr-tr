---
title: ATL bağlantı noktası örneği
ms.date: 11/04/2016
helpviewer_keywords:
- connection points [C++], examples
- examples [ATL]
ms.assetid: a49721b7-f308-43de-8868-f662a94bc81a
ms.openlocfilehash: 3113637a3f777a56bc0b0994203ce709fbc189d5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62223348"
---
# <a name="atl-connection-point-example"></a>ATL bağlantı noktası örneği

Bu örnek, destekleyen bir nesne gösterir [Ipropertynotifysink](/windows/desktop/api/ocidl/nn-ocidl-ipropertynotifysink) giden bir arabirim olarak:

[!code-cpp[NVC_ATL_Windowing#84](../atl/codesnippet/cpp/atl-connection-point-example_1.h)]

Belirtirken `IPropertyNotifySink` giden bir arabirim sınıfını kullanabilirsiniz [Ipropertynotifysinkcp](../atl/reference/ipropertynotifysinkcp-class.md) yerine `IConnectionPointImpl`. Örneğin:

[!code-cpp[NVC_ATL_Windowing#85](../atl/codesnippet/cpp/atl-connection-point-example_2.h)]

## <a name="see-also"></a>Ayrıca bkz.

[Bağlantı noktası](../atl/atl-connection-points.md)
