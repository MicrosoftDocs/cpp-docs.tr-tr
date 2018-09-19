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
ms.openlocfilehash: 8dcefa3068cb27514671094194ba590e99402b05
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46021103"
---
# <a name="atl-database-classes-ole-db-templates"></a>ATL Veritabanı Sınıfları (OLE DB Şablonları)

Microsoft, OLE DB, verilere çok çeşitli bilgi kaynakları ve biçimler Tekdüzen erişim sağlayan COM arabirimleri kümesi çeşitli uygulamalarını sağlar.  OLE DB resmi olarak kullanım dışı; eski kod bakımı geliştiriciler için belgelerdir. Yeni uygulamalar SQL veri kaynaklarına bağlanmak için ODBC kullanmanız gerekir.
  
ATL OLE DB veritabanı teknoloji birçok yaygın olarak kullanılan bir OLE DB arabirimlerini uygulayan sınıflar sağlayarak kullanımını kolaylaştırmak şablonlarında C++ OLE DB Şablonları var.  
  
Bu şablon kitaplığı iki bölümden oluşur:  
  
- [OLE DB Tüketici Şablonları](../data/oledb/ole-db-consumer-templates-cpp.md) OLE DB (tüketici) istemci uygulamalarını uygulamak için kullanılır.  
  
- [OLE DB sağlayıcı şablonları](../data/oledb/ole-db-provider-templates-cpp.md) bir OLE DB sunucusu (sağlayıcı) uygulama uygulamak için kullanılır.  
  
Ayrıca, [OLE DB tüketici öznitelikleri](../windows/ole-db-consumer-attributes.md) OLE DB tüketicileri oluşturmak için kullanışlı bir yol sağlar. OLE DB öznitelikleri çalışan OLE DB tüketicileri oluşturmak için OLE DB Tüketici şablonları temel alan kod yerleştirir.  
  
MFC Kitaplığı sınıfını içeren Not [COleDBRecordView](../mfc/reference/coledbrecordview-class.md), denetimlerde veritabanı kayıtlarını görüntüleyen. Doğrudan bağlı bir form görünümü görünümdür bir `CRowset` nesne ve alanlarını görüntüler `CRowset` iletişim şablonun denetimlerinde nesne.  
  
Daha fazla bilgi için [OLE DB programlama](../data/oledb/ole-db-programming.md) ve [OLE DB Programcı Kılavuzu](/previous-versions/windows/desktop/ms713643\(v=vs.85\)).  
  
## <a name="see-also"></a>Ayrıca Bkz.  

[OLE DB Tüketicisi Oluşturma](../data/oledb/creating-an-ole-db-consumer.md)<br/>
[OLE DB Sağlayıcısı Oluşturma](../data/oledb/creating-an-ole-db-provider.md)<br/>
[OLE DB Tüketici Şablonları Başvurusu](../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[OLE DB Sağlayıcı Şablonları Başvurusu](../data/oledb/ole-db-provider-templates-reference.md)<br/>
[OLE DB Şablon örnekleri](https://github.com/Microsoft/VCSamples)