---
title: Bileşik denetime işlevsellik ekleme
ms.date: 11/04/2016
helpviewer_keywords:
- event handlers [C++], ActiveX controls
- composite controls, handling events
- ActiveX controls [C++], events
ms.assetid: 98f85681-9564-480d-af38-03f9733fe58b
ms.openlocfilehash: 9ad7ef3d80579804ac614fbefac1a042a9cf2fba
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62252500"
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

## <a name="see-also"></a>Ayrıca bkz.

[Bileşik Denetim temelleri](../atl/atl-composite-control-fundamentals.md)
