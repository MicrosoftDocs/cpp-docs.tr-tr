---
title: 'Etkinleştirme: Fiiller | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- verbs [MFC]
- OLE [MFC], activation
- edit verb [MFC]
- activation [MFC], verbs
- OLE [MFC], editing
- Primary verb [MFC]
- OLE activation {MFC]
ms.assetid: eb56ff23-1de8-43ad-abeb-dc7346ba7b70
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2c484231eb87144a6546ff2b8b7061a5339820ee
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33331080"
---
# <a name="activation-verbs"></a>Etkinleştirme: Fiiller
Bu makalede OLE rol birincil ve ikincil fiiller oyunda açıklanmaktadır [etkinleştirme](../mfc/activation-cpp.md).  
  
 Genellikle, katıştırılmış bir öğeyi çift düzenlemek kullanıcının sağlar. Ancak, belirli öğeleri bu şekilde davranır değil. Örneğin, Ses Kaydedicisi uygulama ile oluşturulan bir öğeyi çift sunucu ayrı bir pencerede açılmaz; Bunun yerine, ses yürütür.  
  
 Bu davranış fark Ses Kaydedicisi öğeleri farklı "birincil fiil." sahip nedeni Birincil fiil kullanıcı OLE öğeyi tıklattığında gerçekleştirilen bir eylemdir. OLE öğeleri çoğu türleri için birincil fiil öğesini oluşturan sunucusu başlatan Düzenle ' dir. Ses Kaydedicisi öğeleri gibi öğeleri bazı türleri birincil fiil Play içindir.  
  
 OLE öğeleri türlerde yalnızca bir fiil destekler ve düzenleme en yaygın adrestir. Ancak, bazı türlerde öğeleri birden çok fiilleri destekler. Örneğin, Ses Kaydedicisi öğeleri destekler, ikincil bir fiil olarak düzenleyin.  
  
 Sık kullanılan başka bir fiil Aç ' dir. Sunucu uygulaması ayrı bir pencerede başlatılır dışında açık fiili Düzenle için aynıdır. Kapsayıcı uygulama veya sunucu uygulaması yerinde etkinleştirme desteklemediğinde bu fiil kullanılmalıdır.  
  
 Öğe seçildiğinde birincil fiil dışındaki tüm fiiller alt komutu aracılığıyla çağrılması gerekir. Bu alt öğe tarafından desteklenen tüm fiiller içerir ve genellikle tarafından sınırına *typename* **nesne** komutunu **Düzenle** menüsü. Hakkında bilgi için *typename* **nesne** komutu, makaleye bakın [menüler ve kaynaklar: kapsayıcı ekleme](../mfc/menus-and-resources-container-additions.md).  
  
 Sunucu uygulamasının desteklediği fiiller Windows kayıt veritabanı'nda listelenir. Sunucu uygulamanızı Microsoft Foundation Class Kitaplığı ile yazılmışsa sunucusu başlatıldığında otomatik olarak tüm fiiller kaydeder. Aksi durumda, sunucu uygulamasının başlangıç aşamasında kaydetmeniz. Daha fazla bilgi için bkz: [kayıt](../mfc/registration.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Etkinleştirme](../mfc/activation-cpp.md)   
 [Kapsayıcıları](../mfc/containers.md)   
 [Sunucular](../mfc/servers.md)

