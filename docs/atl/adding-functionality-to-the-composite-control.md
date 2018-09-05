---
title: Bileşik denetime işlevsellik ekleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- event handlers [C++], ActiveX controls
- composite controls, handling events
- ActiveX controls [C++], events
ms.assetid: 98f85681-9564-480d-af38-03f9733fe58b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 59ee8047e17efdebbae6ee58ec243057a477caff
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43751139"
---
# <a name="adding-functionality-to-the-composite-control"></a>Bileşik denetime işlevsellik ekleme

Bileşik denetime gerekli herhangi bir denetim ekledikten sonra sonraki adım, yeni işlevsellik ekleme içerir. Bu yeni işlevselliği, genellikle iki kategoriye döner:

- Ek arabirimleri destekleyen ve ek, belirli özellikleri ile Bileşik Denetim davranışını özelleştirme.

- Kapsanan ActiveX denetimi (veya denetimleri) etkinlikleri işleme.

Amacı ve bu makalenin kapsamı için bu bölümün geri kalanında yalnızca ActiveX denetimleri etkinlikleri işleme üzerinde odaklanır.

> [!NOTE]
>  Windows denetimleri gelen iletileri işlemek ihtiyacınız varsa bkz [pencere uygulama](../atl/implementing-a-window.md) ileti ATL içinde işleme hakkında daha fazla bilgi

ActiveX denetimi iletişim kaynak ekleme sonra denetime sağ tıklayın ve **olay işleyici Ekle**. ' A tıklayın ve işlemek için istediğiniz olayı seçin **ekleme ve düzenleme**. Olay işleyici kodunu denetim .h dosyasına eklenir.

Bileşik denetim ActiveX denetimleri için bağlantı noktaları otomatik olarak bağlı ve çağrılar aracılığıyla bağlı [CComCompositeControl::AdviseSinkMap](../atl/reference/ccomcompositecontrol-class.md#advisesinkmap).

## <a name="see-also"></a>Ayrıca Bkz.

[Bileşik Denetim temelleri](../atl/atl-composite-control-fundamentals.md)

