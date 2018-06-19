---
title: Rebar denetimi oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- rebar controls [MFC], creating
- CReBarCtrl class [MFC], creating
ms.assetid: 0a012e08-772b-4f6a-af86-7cb651d11d3e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1deb33adc104775cf9b76daf75d4ee08b6475f0a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33342313"
---
# <a name="creating-a-rebar-control"></a>Rebar Denetimi Oluşturma
[CReBarCtrl](../mfc/reference/crebarctrl-class.md) nesneleri üst nesne görünür hale gelmeden önce oluşturulmalıdır. Bu olanaklar boyama sorunları en aza indirir.  
  
 Örneği için (çerçeve pencere nesneleri kullanılır) rebar denetimleri araç çubuğu denetimleri için yaygın olarak üst windows olarak kullanılır. Bu nedenle, rebar denetimiyle üst çerçeve penceresi nesnesidir. Çerçeve pencere nesnesi üst olduğundan `OnCreate` üyesi (üst) işlevidir rebar denetimi oluşturmak için mükemmel bir yerdir.  
  
 Kullanılacak bir `CReBarCtrl` nesnesi, genellikle şu adımları izleyin:  
  
### <a name="to-use-a-crebarctrl-object"></a>CReBarCtrl nesnesini kullanmak için  
  
1.  Oluşturmak [CReBarCtrl](../mfc/reference/crebarctrl-class.md) nesnesi.  
  
2.  Çağrı [oluşturma](../mfc/reference/crebarctrl-class.md#create) Windows rebar ortak denetimi oluşturmak ve ona eklemek için `CReBarCtrl` herhangi istenen stilleri belirten nesnesini.  
  
3.  Çağrısıyla bir bit eşlem yük [CBitmap::LoadBitmap](../mfc/reference/cbitmap-class.md#loadbitmap), rebar denetimi nesnesi arka planı olarak kullanılacak.  
  
4.  Oluşturma ve başlatma rebar denetimi nesnesiyle içerdiği tüm alt pencere nesneleri (araç çubukları, iletişim kutusu denetimleri ve benzeri).  
  
5.  Başlatma bir **REBARBANDINFO** yapısı hakkında eklenecek bant için gerekli bilgileri ile.  
  
6.  Çağrı [InsertBand](../mfc/reference/crebarctrl-class.md#insertband) varolan alt öğe pencerelerini eklemek için (gibi `m_wndReToolBar`) yeni rebar denetimine. Varolan bir rebar denetimi bantlar ekleme konusunda daha fazla bilgi için bkz: [Rebar denetimleri ve bantları](../mfc/rebar-controls-and-bands.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CReBarCtrl kullanma](../mfc/using-crebarctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

