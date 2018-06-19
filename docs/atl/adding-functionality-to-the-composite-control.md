---
title: Bileşik Denetim işlevselliği ekleme | Microsoft Docs
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
ms.openlocfilehash: 67602e16fc5a30c82e82772b6b9f6c553ba79d9b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32354188"
---
# <a name="adding-functionality-to-the-composite-control"></a>Bileşik Denetim işlevsellik ekleme
Tüm gerekli denetimleri bileşik denetime ekledikten sonra sonraki adım, yeni işlevsellik ekleme içerir. Bu yeni işlevsellik genellikle iki kategoride toplanabilir:  
  
-   Ek arabirimleri destekleyen ve ek, belirli özelliklerle bileşik denetiminizi davranışını özelleştirme.  
  
-   Kapsanan ActiveX denetimi (veya denetimleri) olayları işleme.  
  
 Amacı ve bu makalenin kapsamı için bu bölümde geri kalanı yalnızca ActiveX denetimlerini etkinlikleri işleme üzerine odaklanır.  
  
> [!NOTE]
>  Windows denetimleri gelen iletileri işlemek ihtiyacınız varsa bkz [bir pencere uygulama](../atl/implementing-a-window.md) ileti içinde ATL işleme hakkında daha fazla bilgi için  
  
 ActiveX denetimi iletişim kaynak ekleme sonra denetimi sağ tıklatın ve **olay işleyicisi ekleme**. Önce işlemek istediğiniz olayı seçin **ekleme ve düzenleme**. Olay işleyici kodu denetimin .h dosyasına eklenir.  
  
 Bileşik denetim ActiveX denetimleri için bağlantı noktaları otomatik olarak bağlı ve çağrıları aracılığıyla bağlantısı kesilmiş [CComCompositeControl::AdviseSinkMap](../atl/reference/ccomcompositecontrol-class.md#advisesinkmap).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bileşik Denetim temelleri](../atl/atl-composite-control-fundamentals.md)

