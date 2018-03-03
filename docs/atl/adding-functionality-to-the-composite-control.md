---
title: "Bileşik Denetim işlevselliği ekleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- event handlers [C++], ActiveX controls
- composite controls, handling events
- ActiveX controls [C++], events
ms.assetid: 98f85681-9564-480d-af38-03f9733fe58b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6dcf3ffa0c3168c2f96a3ad9bed13ab1213f63da
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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

