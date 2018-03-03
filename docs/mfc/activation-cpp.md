---
title: "Etkinleştirme (C++) | Microsoft Docs"
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
- OLE server applications [MFC], activation
- OLE items [MFC], visual editing
- activation [MFC]
- OLE [MFC], in-place activation
- OLE [MFC], activation
- in-place activation, embedded and linked items
- activating objects
- visual editing, activation
- visual editing
- documents [MFC], OLE
- embedded objects [MFC]
- OLE [MFC], editing
- in-place activation
- activation [MFC], embedded OLE items
- OLE activation [MFC]
ms.assetid: ed8357d9-e487-4aaa-aa6b-2edc4de25dfa
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 70017721fb59fa0c6d18d568546d9618257328b5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="activation-c"></a>Etkinleştirme (C++)
Bu makalede visual OLE öğelerini düzenleme etkinleştirme rol açıklanmaktadır. Bir kullanıcı bir OLE öğesi bir kapsayıcı belgede katıştırılmış içeren sonra kullanılacak gerekebilir. Bunu yapmak için bu öğeyi etkinleştirir öğesi kullanıcı çift tıklamalar. Etkinleştirme için en sık rastlanan etkinlik düzenliyor. Düzenleme için etkinleştirildiğinde birçok geçerli OLE öğeleri, menüleri ve araç çubuklarını öğesini oluşturan sunucu uygulamaya ait olanlar yansıtacak şekilde değiştirmek için geçerli çerçeve penceresi neden. Olarak yerinde etkinleştirme, bilinen bu davranış, kapsayıcı belgenin penceresi ayrılmadan bir bileşik belge katıştırılmış herhangi bir öğeye düzenlemesine olanak tanır.  
  
 Katıştırılmış OLE öğeleri ayrı bir pencerede düzenlemek mümkündür. Kapsayıcı ya da sunucu uygulamasının yerinde etkinleştirme desteklemiyorsa, bu durum gerçekleşir. Bu durumda, kullanıcı katıştırılmış öğeyi tıklattığında sunucu uygulaması ayrı bir pencerede başlatılır ve katıştırılmış öğesi kendi belgesi olarak görünür. Kullanıcı Bu pencere öğesinde düzenler. Düzenleme tamamlandığında, kullanıcı sunucu uygulaması kapatır ve kapsayıcı uygulamaya döndürür.  
  
 Alternatif olarak, kullanıcı "açmak düzenleme" ile seçebilir  **\<nesnesi > açmak** komutunu **Düzenle** menüsü. Bu nesne ayrı bir pencerede açar.  
  
> [!NOTE]
>  OLE 1 sürümünde standart davranışı olan ayrı bir pencerede katıştırılmış öğelerini düzenleme ve bazı OLE uygulamaları düzenleme yalnızca bu stili destekleyebilir.  
  
 Yerinde etkinleştirme belge oluşturma için belge merkezli bir yaklaşım yükseltir. Kullanıcı bir bileşik belge üzerinde uygulamalar arasında geçiş yapma olmadan çalışan tek bir varlık olarak davranabilirsiniz. Ancak, yalnızca bağlantılı öğeler için katıştırılmış öğeleri için yerinde etkinleştirme kullanılır: ayrı bir pencerede düzenlenmesi gerekir. Bağlantılı bir öğe başka bir yerde depolandığından budur. Bağlantılı bir öğenin düzenlenmesine verilerin depolandığı veri, diğer bir deyişle, gerçek bağlamında gerçekleşir. Bağlantılı bir öğe ayrı bir pencerede düzenleme verileri başka bir belgeye ait kullanıcı anımsatır.  
  
 MFC iç içe geçmiş yerinde etkinleştirme desteklemez. Bir kapsayıcı/sunucu uygulaması derleme varsa ve kapsayıcı/sunucu başka bir kapsayıcı ve yerinde etkinleştirilmiş katıştırılmış, onu yerinde olamaz katıştırılmış nesneler etkinleştirin.  
  
 Kullanıcı tıklattığında katıştırılmış bir öğesiyle olanlar öğesi için tanımlanmış fiiller bağlıdır. Bilgi için bkz: [etkinleştirme: fiiller](../mfc/activation-verbs.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE](../mfc/ole-in-mfc.md)   
 [Kapsayıcıları](../mfc/containers.md)   
 [Sunucular](../mfc/servers.md)

