---
title: Bileşik Denetime İşlevsellik Ekleme
ms.date: 11/04/2016
helpviewer_keywords:
- event handlers [C++], ActiveX controls
- composite controls, handling events
- ActiveX controls [C++], events
ms.assetid: 98f85681-9564-480d-af38-03f9733fe58b
ms.openlocfilehash: 5de18f863831973af384d2456adb5b2214f0dd68
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317420"
---
# <a name="adding-functionality-to-the-composite-control"></a>Bileşik Denetime İşlevsellik Ekleme

Bileşik denetime gerekli denetimleri ekledikten sonra, bir sonraki adım yeni işlevsellik eklemeyi içerir. Bu yeni işlev genellikle iki kategoriye ayrılır:

- Ek arabirimleri desteklemek ve bileşik denetiminizin davranışını ek, belirli özelliklerle özelleştirmek.

- İçerdiği ActiveX denetiminden (veya denetimlerinden) olayları işleme.

Bu makalenin amacı ve kapsamı için, bu bölümün geri kalanı yalnızca ActiveX denetimlerinden olayları işlemeye odaklanır.

> [!NOTE]
> Windows denetimlerinden gelen iletileri işlemeniz gerekiyorsa, ATL'de ileti işleme hakkında daha fazla bilgi için [Pencere Uygulama'ya](../atl/implementing-a-window.md) bakın.

İletişim kaynağına ActiveX denetimi ekledikten sonra denetimi sağ tıklatın ve **Olay İşleyicisi Ekle'yi**tıklatın. Işlemek istediğiniz olayı seçin ve **Ekle ve Düzenledik'i**tıklatın. Olay işleyicisi kodu denetimin .h dosyasına eklenir.

Kompozit kontroldeki ActiveX kontrollerinin bağlantı noktaları CComCompositeControl'e yapılan çağrılar la otomatik olarak bağlanır ve [kesilir::AdviseSinkMap](../atl/reference/ccomcompositecontrol-class.md#advisesinkmap).

## <a name="see-also"></a>Ayrıca bkz.

[Kompozit Kontrol Esasları](../atl/atl-composite-control-fundamentals.md)
