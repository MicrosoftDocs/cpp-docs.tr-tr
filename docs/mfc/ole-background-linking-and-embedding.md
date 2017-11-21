---
title: "OLE arka planı: Bağlama ve katıştırma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- OLE embedded items [MFC]
- item types [MFC], defined
- item types [MFC]
- OLE [MFC], linked items
- linked items (OLE) [MFC]
- embedded objects [MFC]
- OLE items [MFC], types
ms.assetid: 11107711-eb96-4099-8f5c-7910bb3ecb75
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9ecbc8bb39d9cba3a5d13567811221fe0a703ab5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ole-background-linking-and-embedding"></a>OLE Arka Planı: Bağlama ve Katıştırma
Bir kapsayıcı uygulamasında Yapıştır komutunu kullanarak bir katıştırılmış bileşeni veya katıştırılmış öğesi oluşturabilirsiniz. Katıştırılmış bir öğe için kaynak verilerini içerdiği OLE belge bir parçası olarak depolanır. Bu şekilde bir belge dosyasını bir sözcük işlemci belge için metin içerebilir ve bit eşlemler, grafikler, formüller veya herhangi bir veri türünü de içerebilir.  
  
 OLE verileri başka bir uygulamadan birleştirmek için başka bir yöntem sunar: bağlı bir bileşen veya bağlantılı öğesi veya bir bağlantı oluşturuluyor. Bağlantı Yapıştır komut Yapıştır komutu yerine dışında kullanmasını bağlantılı bir öğe oluşturma adımlarını katıştırılmış bir öğe oluşturmak için benzerdir. Katıştırılmış bir bileşen farklı olarak ayrı bir dosyaya görülür özgün veri yoluna bağlı bir bileşen depolar.  
  
 Örneğin, bir sözcük işlemci belge çalışma ve bazı elektronik tablo hücreleri bağlantılı bir öğesiyle oluşturursanız, veriler bağlantılı öğesi için özgün elektronik belgede depolanır. Sözcük işlemci belge yalnızca öğe, başka bir deyişle, özgün elektronik belge için bir bağlantı içeren bulunabileceği belirtme bilgilerini içerir. Hücreleri çift tıkladığınızda, elektronik tablo uygulaması başlatılır ve özgün elektronik belge depolandığı gelen yüklenir.  
  
 Her OLE öğesi katıştırılmış ya da bağlantılı, oluşturulduğu uygulamaya göre ilişkili bir türe sahip. Örneğin, bir türde öğe bir Microsoft Paintbrush öğesidir ve Microsoft Excel öğesi başka bir türdür. Bazı uygulamalar, ancak, birden fazla öğesi türü oluşturabilirsiniz. Örneğin, Microsoft Excel çalışma öğeleri, grafik öğeleri ve makro sayfası öğeleri oluşturabilirsiniz. Bu öğelerin her biri bir sınıf tanımlayıcısını kullanarak sistem tarafından benzersiz olarak tanımlanabilir veya **CLSID**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE arka planı](../mfc/ole-background.md)   
 [OLE arka planı: Kapsayıcılar ve sunucular](../mfc/ole-background-containers-and-servers.md)   
 [Kapsayıcılar: İstemci öğeleri](../mfc/containers-client-items.md)   
 [Sunucular: Sunucu öğeleri](../mfc/servers-server-items.md)

