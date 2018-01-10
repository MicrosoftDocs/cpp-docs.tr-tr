---
title: "Veri kaynakları ve oturumlar | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- data sources [C++], OLE DB
- connections [C++], data source
- OLE DB consumer templates [C++], data sources
ms.assetid: 6ee52216-e082-4869-a1d6-ce561cfb76e5
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2bb675897e29a26446b3070b2192b4f5c3e8fd2e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="data-sources-and-sessions"></a>Veri Kaynakları ve Oturumlar
Aşağıdaki şekilde bağlanmak ve veri kaynağına erişme destekleyen sınıfları gösterir. Her sınıf standart bir OLE DB bileşen uygulamasına dayalıdır.  
  
 ![Veri kaynağı ve oturum sınıfları](../../data/oledb/media/vcdatasourcesessionclasses.gif "vcdatasourcesessionclasses")  
Veri kaynağı ve oturum sınıfları  
  
 Sınıfları şunlardır:  
  
-   [CDataSource](../../data/oledb/cdatasource-class.md) Bu sınıf oluşturur ve bir veri kaynağına OLE DB sağlayıcısı aracılığıyla bağlantı yöneten veri kaynağı nesnesi başlatır. Veri kaynağı bir bağlantı dizesi biçiminde veri kaynağı adresi ve kimlik bilgileri gibi bilgileri alır.  
  
     Ayrıca, dikkate değerdir yardımcı sınıfı [CEnumerator](../../data/oledb/cenumerator-class.md) sisteme kayıtlı kullanılabilir sağlayıcılar listesi elde etmek için herhangi bir bağlantı kurulmadan önce çoğunlukla kullanılır. Bu veri kaynağı olarak bir sağlayıcı seçmenize olanak sağlar. Örneğin, **veri bağlantısı özelliklerini** iletişim kutusu üzerinde sağlayıcıları listesini doldurmak için bu sınıfı kullanır **sağlayıcıları** sekmesi. Eşdeğer olan **SQLBrowseConnect** veya **SQLDriverConnect** işlevi.  
  
-   [CSession](../../data/oledb/csession-class.md) Bu sınıf veri kaynağına tek erişimli oturumu gösteren oturum nesnesi başlatır. Ancak, bir veri kaynağında birden çok oturumu oluşturabilirsiniz. Her oturum için satır kümeleri, komutları ve diğer nesneleri veri kaynağından verilere erişmek için oluşturabilirsiniz. Oturum işlemleri işler.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)