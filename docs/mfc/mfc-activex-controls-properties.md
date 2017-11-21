---
title: "MFC ActiveX denetimleri: Özellikler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- properties [MFC], ActiveX controls
- MFC ActiveX controls [MFC], properties
- properties [MFC]
ms.assetid: b678a53c-0d9e-476f-8aa0-23b80baaba46
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 26947b0c2c779f65fb01dd78d56ffe19afaf27ce
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="mfc-activex-controls-properties"></a>MFC ActiveX Denetimleri: Özellikler
ActiveX denetimi denetim kapsayıcısı ile iletişim kurmak için olay tetikler. Kapsayıcı, buna karşılık, yöntemleri ve özellikleri denetimi ile iletişim kurmak için kullanır. Yöntemleri ve özellikleri sırasıyla üye işlevleri ve C++ sınıfının üye değişkenleri için kullanım ve amacı, benzerdir. Herhangi bir kapsayıcıya sunulan veri üyeleri ActiveX denetiminin özelliklerdir. Özellikler, Otomasyon istemcileri ve ActiveX denetimi kapsayıcıları gibi ActiveX denetimlerini içeren uygulamalar için arabirim sağlar.  
  
 Özellikler öznitelikler de denir.  
  
 ActiveX denetimi yöntemleri hakkında daha fazla bilgi için bkz: [MFC ActiveX denetimleri: yöntemler](../mfc/mfc-activex-controls-methods.md).  
  
 ActiveX denetimleri, stock ve özel yöntemler ve Özellikler uygulayabilirsiniz. Sınıf `COleControl` stok özellikleri için bir uygulama sağlar. (Stok özellikleri tam bir listesi için bkz: [MFC ActiveX denetimleri: stok Özellikler ekleme](../mfc/mfc-activex-controls-adding-stock-properties.md).) Özel özellikler, geliştirici tarafından tanımlanan bir ActiveX denetimine özel özellikleri ekleyin. Daha fazla bilgi için bkz: [MFC ActiveX denetimleri: özel özellikler ekleme](../mfc/mfc-activex-controls-adding-custom-properties.md).  
  
 Yöntemleri gibi hem özel hem de stok özellikleri, özellikleri ve yöntemleri ve varolan üye işlevlerini işleyen gönderme haritasını oluşan bir mekanizma tarafından desteklenir `COleControl` sınıfı. Ayrıca, bu özellikleri Geliştirici denetime ek bilgi aktarmak için kullandığı parametreler olabilir.  
  
 Aşağıdaki makaleler ActiveX denetimi özellikleri daha ayrıntılı ele alınmıştır:  
  
-   [MFC ActiveX denetimleri: Stok Özellikler ekleme](../mfc/mfc-activex-controls-adding-stock-properties.md)  
  
-   [MFC ActiveX denetimleri: Özel özellikler ekleme](../mfc/mfc-activex-controls-adding-custom-properties.md)  
  
-   [MFC ActiveX denetimleri: Gelişmiş özellik uygulama](../mfc/mfc-activex-controls-advanced-property-implementation.md)  
  
-   [MFC ActiveX denetimleri: Ortam özelliklerine erişme](../mfc/mfc-activex-controls-accessing-ambient-properties.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC ActiveX denetimleri](../mfc/mfc-activex-controls.md)

