---
title: ATL Veritabanı Sınıfları (OLE DB Şablonları)
ms.date: 05/02/2019
helpviewer_keywords:
- OLE DB templates [C++], ATL database classes
- database classes [C++], OLE DB
- database classes [C++], ATL
ms.assetid: 219766aa-e18a-405f-9e36-d7a0fdb31b2b
ms.openlocfilehash: 5b13a27540b12e7ac1503fbf7cd0e1fe396ce8c8
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91501898"
---
# <a name="atl-database-classes-ole-db-templates"></a>ATL Veritabanı Sınıfları (OLE DB Şablonları)

Microsoft, farklı bilgi kaynaklarındaki ve biçimlerdeki verilere tek biçimli erişim sağlayan bir COM arabirimleri kümesi olan OLE DB çeşitli uygulamaları sağlar.

OLE DB şablonları, yaygın olarak kullanılan OLE DB arabirimlerinin çoğunu uygulayan sınıflar sağlayarak OLE DB veritabanı teknolojisinin daha kolay kullanılmasını sağlayan ATL 'deki C++ şablonlarıdır.

Bu şablon kitaplığı iki bölüm içerir:

- [OLE DB tüketici şablonları](../data/oledb/ole-db-consumer-templates-cpp.md) OLE DB istemcisi (tüketici) uygulaması uygulamak için kullanılır.

- [OLE DB sağlayıcı şablonları](../data/oledb/ole-db-provider-templates-cpp.md) OLE DB sunucusu (sağlayıcı) uygulamasını uygulamak için kullanılır.

Ayrıca, [OLE DB tüketici öznitelikleri](../windows/attributes/ole-db-consumer-attributes.md) , OLE DB tüketicileri oluşturmak için kullanışlı bir yol sağlar. OLE DB öznitelikleri, çalışan OLE DB tüketicileri oluşturmak için OLE DB tüketici şablonlarına göre kod ekler.

MFC kitaplığı, denetimler içindeki veritabanı kayıtlarını görüntüleyen bir sınıf olan [COleDBRecordView](../mfc/reference/coledbrecordview-class.md)sınıfı içerdiğini unutmayın. Görünüm bir nesneye doğrudan bağlı olan bir form görünümüdür `CRowset` ve `CRowset` iletişim şablonu denetimlerinde nesnenin alanlarını görüntüler.

Daha fazla bilgi için bkz. [OLE DB Programlama](../data/oledb/ole-db-programming.md) ve [OLE DB Programcı Kılavuzu](/sql/connect/oledb/ole-db/oledb-driver-for-sql-server-programming).

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB tüketicisi oluşturma](../data/oledb/creating-an-ole-db-consumer.md)<br/>
[OLE DB sağlayıcısı oluşturma](../data/oledb/creating-an-ole-db-provider.md)<br/>
[OLE DB tüketici şablonları başvurusu](../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[OLE DB sağlayıcı şablonları başvurusu](../data/oledb/ole-db-provider-templates-reference.md)<br/>
[OLE DB şablonları örnekleri](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB)
