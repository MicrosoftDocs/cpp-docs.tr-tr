---
title: "OLE DB Şablonları, öznitelikler ve diğer uygulamalar | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB, implementations
- OLE DB templates, about OLE DB templates
- OLE DB templates
ms.assetid: 0c780c1b-9bba-4788-8c33-8552d9f120ac
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: abdf0565db00b13c932366985c315c88d8d29f9e
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="ole-db-templates-attributes-and-other-implementations"></a>OLE DB Şablonları, Öznitelikler ve Diğer Uygulamalar
## <a name="atl-ole-db-templates"></a>ATL OLE DB Şablonları  
 OLE DB ATL (Etkin Şablon Kütüphanesi) parçası olan şablonları, yüksek performanslı OLE DB veritabanı teknolojisi birçok yaygın olarak kullanılan OLE DB arabirimlerini uygulayan sınıflar sağlayarak kullanmak kolaylaştırır. Yanı sıra bu şablon OLE DB Başlatıcı uygulamaları oluşturmak için sihirbaz desteği kitaplığı gelir.  
  
 Bu şablon kitaplığı iki bölümden oluşur:  
  
-   **OLE DB Tüketici Şablonları** bir OLE DB istemci (tüketici) uygulamalarını gerçekleştirmek için kullanılır.  
  
-   **OLE DB sağlayıcı şablonları** bir OLE DB sunucu (sağlayıcı) uygulamalarını gerçekleştirmek için kullanılır.  
  
 OLE DB Şablonları kullanmak için C++ şablonları, COM ve OLE DB arabirimleri ile bilgi sahibi olmanız. OLE DB ile bilmiyorsanız bkz [OLE DB Programcının Başvurusu](https://msdn.microsoft.com/en-us/library/ms713643.aspx).  
  
 Daha fazla bilgi için şunları yapabilirsiniz:  
  
-   İlgili konuları okuyun [OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md) veya [OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md).  
  
-   Oluşturma bir [OLE DB Tüketici](../../data/oledb/creating-an-ole-db-consumer.md) veya [OLE DB sağlayıcısı](../../data/oledb/creating-an-ole-db-provider.md).  
  
-   Listesine bakın [OLE DB Tüketici sınıflar](../../data/oledb/ole-db-consumer-templates-reference.md) veya [OLE DB sağlayıcısı sınıfları](../../data/oledb/ole-db-provider-templates-reference.md).  
  
-   Listesine bakın [OLE DB Şablon örnekleri](http://msdn.microsoft.com/en-us/08958863-0b5f-41ad-ae99-fca7440c553c).  
  
-   Bkz: [OLE DB Programcının Başvurusu](https://msdn.microsoft.com/en-us/library/ms713643.aspx) (SDK Windows'da).  
  
## <a name="ole-db-attributes"></a>OLE DB öznitelikleri  
 [OLE DB tüketici öznitelikleri](../../windows/ole-db-consumer-attributes.md) OLE DB tüketicileri oluşturmak için kolay bir yol sağlamak. OLE DB öznitelikleri göre kod yerleştirir [OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-reference.md) çalışan OLE DB Tüketicileri ve sağlayıcıları oluşturmak için. Öznitelikler tarafından desteklenmeyen bir işlev belirtmeniz gerekiyorsa, OLE DB Şablonları öznitelikleri ile birlikte kodunuzda kullanabilirsiniz.  
  
## <a name="mfc-ole-db-classes"></a>MFC OLE DB sınıfları  
 MFC kitaplık bir sınıf, sahip [COleDBRecordView](../../mfc/reference/coledbrecordview-class.md), denetimlerinde veritabanı kayıtları görüntüler. Doğrudan bağlı bir form görünümü görünümdür bir `CRowset` nesne ve alanlarını görüntüler `CRowset` iletişim şablonun denetimlerinde nesnesi. Ayrıca taşıma için varsayılan uygulamasını sağlar, ilk sonraki, önceki ya da son kaydını ve kayıtta şu anda Görünümü güncelleştirmek için bir arabirim. Daha fazla bilgi için bkz. `COleDBRecordView`.  
  
## <a name="ole-db-sdk-interfaces"></a>OLE DB SDK arabirimleri  
 Burada OLE DB Şablonları OLE DB işlevselliği desteklemeyen durumlarda, OLE DB arabirimlerini kullanmanız gerekir. Daha fazla bilgi için bkz: [OLE DB Programcının Başvurusu](https://msdn.microsoft.com/en-us/library/ms713643.aspx) Windows SDK'sındaki.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB programlama](../../data/oledb/ole-db-programming.md)   
 [OLE DB Programlamaya Genel Bakış](../../data/oledb/ole-db-programming-overview.md)