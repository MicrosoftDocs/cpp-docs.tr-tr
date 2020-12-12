---
description: 'Hakkında daha fazla bilgi edinin: bileşik denetime Işlevsellik ekleme'
title: Bileşik denetime Işlevsellik ekleme
ms.date: 11/04/2016
helpviewer_keywords:
- event handlers [C++], ActiveX controls
- composite controls, handling events
- ActiveX controls [C++], events
ms.assetid: 98f85681-9564-480d-af38-03f9733fe58b
ms.openlocfilehash: 90e1f6b0adfc33817f9fa5a6de6fbdcd276241e1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97166128"
---
# <a name="adding-functionality-to-the-composite-control"></a>Bileşik denetime Işlevsellik ekleme

Bileşik denetime gerekli denetimleri ekledikten sonra, bir sonraki adım yeni işlevsellik eklemeyi içerir. Bu yeni işlevsellik genellikle iki kategoriye denk gelir:

- Ek arabirimleri destekleme ve bileşik denetiminizin davranışını ek, özel özelliklerle özelleştirme.

- İçerilen ActiveX denetiminden (veya denetimlerinde) olayları işleme.

Bu makalenin amacı ve kapsamı için, bu bölümün geri kalanı yalnızca ActiveX denetimlerinden olayları işlemeye odaklanır.

> [!NOTE]
> Windows denetimlerinden iletileri işlemeniz gerekiyorsa, ATL 'de ileti işleme hakkında daha fazla bilgi için bkz. [bir pencere uygulama](../atl/implementing-a-window.md) .

İletişim kutusuna bir ActiveX denetimi ekledikten sonra, denetime sağ tıklayın ve **olay Işleyicisi Ekle**' ye tıklayın. İşlemek istediğiniz olayı seçin ve **Ekle ve Düzenle**' ye tıklayın. Olay işleyicisi kodu, denetimin. h dosyasına eklenecektir.

Bileşik denetimdeki ActiveX denetimleri için bağlantı noktaları, [CComCompositeControl:: Advisesınkmap](../atl/reference/ccomcompositecontrol-class.md#advisesinkmap)çağrıları aracılığıyla otomatik olarak bağlanır ve kesilir.

## <a name="see-also"></a>Ayrıca bkz.

[Bileşik denetim temelleri](../atl/atl-composite-control-fundamentals.md)
