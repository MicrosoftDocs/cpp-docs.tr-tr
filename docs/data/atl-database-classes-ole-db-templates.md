---
title: ATL Veritabanı sınıfları (OLE DB Şablonları) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- OLE DB templates [C++], ATL database classes
- database classes [C++], OLE DB
- database classes [C++], ATL
ms.assetid: 219766aa-e18a-405f-9e36-d7a0fdb31b2b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: fabced79232d17807d252da9dac5b066ddf69f25
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="atl-database-classes-ole-db-templates"></a>ATL Veritabanı Sınıfları (OLE DB Şablonları)
Microsoft OLE DB, çeşitli bilgi kaynakları ve biçimlerinde verilere Tekdüzen erişim sağlayan COM arabirimleri kümesi çeşitli uygulamalarını sağlar.  OLE DB resmi olarak kullanım dışı; eski kod bakımı geliştiriciler için belgesidir. Yeni uygulamalar, SQL veri kaynaklarına bağlanmak için ODBC kullanmalıdır.
  
 OLE DB Şablonları OLE DB veritabanı teknolojisi birçok yaygın olarak kullanılan OLE DB arabirimlerini uygulayan sınıflar sağlayarak kullanmayı daha kolay hale C++ ATL içinde şablonlarıdır.  
  
 Bu şablon kitaplığı iki bölümden oluşur:  
  
-   [OLE DB Tüketici Şablonları](../data/oledb/ole-db-consumer-templates-cpp.md) bir OLE DB istemci (tüketici) uygulamalarını gerçekleştirmek için kullanılır.  
  
-   [OLE DB sağlayıcı şablonları](../data/oledb/ole-db-provider-templates-cpp.md) bir OLE DB sunucu (sağlayıcı) uygulamalarını gerçekleştirmek için kullanılır.  
  
 Ayrıca, [OLE DB tüketici öznitelikleri](../windows/ole-db-consumer-attributes.md) OLE DB tüketicileri oluşturmak için kolay bir yol sağlamak. OLE DB öznitelikleri çalışan OLE DB tüketicileri oluşturmak için OLE DB Tüketici Şablonları göre kod yerleştirir.  
  
 MFC kitaplığını bir sınıf içerdiğini unutmayın [COleDBRecordView](../mfc/reference/coledbrecordview-class.md), denetimlerinde veritabanı kayıtları görüntüler. Doğrudan bağlı bir form görünümü görünümdür bir `CRowset` nesne ve alanlarını görüntüler `CRowset` iletişim şablonun denetimlerinde nesnesi.  
  
 Daha fazla bilgi için bkz: [OLE DB programlama](../data/oledb/ole-db-programming.md) ve [OLE DB Programcı Kılavuzu](http://go.microsoft.com/fwlink/p/?linkid=121548).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Tüketicisi Oluşturma](../data/oledb/creating-an-ole-db-consumer.md)   
 [OLE DB sağlayıcısı oluşturma](../data/oledb/creating-an-ole-db-provider.md)   
 [OLE DB Tüketici Şablonları başvurusu](../data/oledb/ole-db-consumer-templates-reference.md)   
 [OLE DB sağlayıcı şablonları başvurusu](../data/oledb/ole-db-provider-templates-reference.md)   
 [OLE DB Şablon örnekleri](http://msdn.microsoft.com/en-us/08958863-0b5f-41ad-ae99-fca7440c553c)