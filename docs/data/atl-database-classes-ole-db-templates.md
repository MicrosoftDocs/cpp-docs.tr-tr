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
ms.openlocfilehash: 91cd06ea1d8ff697da6c4959fff34fdc3798dcfd
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43218994"
---
# <a name="atl-database-classes-ole-db-templates"></a>ATL Veritabanı Sınıfları (OLE DB Şablonları)
Microsoft, OLE DB, verilere çok çeşitli bilgi kaynakları ve biçimler Tekdüzen erişim sağlayan COM arabirimleri kümesi çeşitli uygulamalarını sağlar.  OLE DB resmi olarak kullanım dışı; eski kod bakımı geliştiriciler için belgelerdir. Yeni uygulamalar SQL veri kaynaklarına bağlanmak için ODBC kullanmanız gerekir.
  
 ATL OLE DB veritabanı teknoloji birçok yaygın olarak kullanılan bir OLE DB arabirimlerini uygulayan sınıflar sağlayarak kullanımını kolaylaştırmak şablonlarında C++ OLE DB Şablonları var.  
  
 Bu şablon kitaplığı iki bölümden oluşur:  
  
-   [OLE DB Tüketici Şablonları](../data/oledb/ole-db-consumer-templates-cpp.md) OLE DB (tüketici) istemci uygulamalarını uygulamak için kullanılır.  
  
-   [OLE DB sağlayıcı şablonları](../data/oledb/ole-db-provider-templates-cpp.md) bir OLE DB sunucusu (sağlayıcı) uygulama uygulamak için kullanılır.  
  
 Ayrıca, [OLE DB tüketici öznitelikleri](../windows/ole-db-consumer-attributes.md) OLE DB tüketicileri oluşturmak için kullanışlı bir yol sağlar. OLE DB öznitelikleri çalışan OLE DB tüketicileri oluşturmak için OLE DB Tüketici şablonları temel alan kod yerleştirir.  
  
 MFC Kitaplığı sınıfını içeren Not [COleDBRecordView](../mfc/reference/coledbrecordview-class.md), denetimlerde veritabanı kayıtlarını görüntüleyen. Doğrudan bağlı bir form görünümü görünümdür bir `CRowset` nesne ve alanlarını görüntüler `CRowset` iletişim şablonun denetimlerinde nesne.  
  
 Daha fazla bilgi için [OLE DB programlama](../data/oledb/ole-db-programming.md) ve [OLE DB Programcı Kılavuzu](http://go.microsoft.com/fwlink/p/?linkid=121548).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Tüketicisi Oluşturma](../data/oledb/creating-an-ole-db-consumer.md)   
 [OLE DB sağlayıcısı oluşturma](../data/oledb/creating-an-ole-db-provider.md)   
 [OLE DB Tüketici Şablonları başvurusu](../data/oledb/ole-db-consumer-templates-reference.md)   
 [OLE DB sağlayıcı şablonları başvurusu](../data/oledb/ole-db-provider-templates-reference.md)   
 [OLE DB Şablon örnekleri](https://msdn.microsoft.com/08958863-0b5f-41ad-ae99-fca7440c553c)