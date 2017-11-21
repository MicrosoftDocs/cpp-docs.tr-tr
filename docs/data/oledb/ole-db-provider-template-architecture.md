---
title: "OLE DB Sağlayıcı Şablonu Mimarisi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- OLE DB [C++], object model
- architecture [C++], OLE DB Provider
- OLE DB provider templates, object model
ms.assetid: 639304a3-f9e0-44dc-8d0c-0ebd2455b363
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 289d1d5f09f60b829c6dd7d1f1b00c0de3562518
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ole-db-provider-template-architecture"></a>OLE DB Sağlayıcı Şablonu Mimarisi
## <a name="data-sources-and-sessions"></a>Veri Kaynakları ve Oturumlar  
 OLE DB sağlayıcı mimarisi, bir veri kaynağı nesnesi ve bir veya daha fazla oturum içerir. Veri kaynağı nesnesi her sağlayıcı örneği gerekir ilk nesnesidir. Bir tüketici uygulaması verilere ihtiyaç duyduğunda birlikte sağlayıcıyı başlatmak için veri kaynağı nesnesi oluşturur. Veri kaynağı nesnesi bir oturum nesnesi oluşturur (kullanarak **IDBCreateSession** arabirimi) veri kaynağı nesnesi tüketici bağlayan aracılığıyla. ODBC programcıları düşünme eşdeğer olarak veri kaynağı nesnesinin **HENV** ve eşdeğer olarak oturum nesnesi **HDBC**.  
  
 ![Sağlayıcı mimarisi](../../data/oledb/media/vc4twb1.gif "vc4twb1")  
  
 OLE DB Sağlayıcı Sihirbazı tarafından oluşturulan kaynak dosyaları ile birlikte, OLE DB Şablonları bir veri kaynağı nesnesi uygular. OLE DB için karşılık gelen bir nesne oturumdur **TSession**.  
  
## <a name="mandatory-and-optional-interfaces"></a>Zorunlu ve isteğe bağlı arabirimler  
 OLE DB sağlayıcı şablonları, paketlenmiş uygulamaları için gerekli tüm arabirimleri sağlar. Zorunlu ve isteğe bağlı arabirimler OLE DB birçok türdeki nesneler için tanımlanır:  
  
-   [Veri kaynağı](../../data/oledb/data-source-object-interfaces.md)  
  
-   [Oturumu](../../data/oledb/session-object-interfaces.md)  
  
-   [Satır kümesi](../../data/oledb/rowset-object-interfaces.md)  
  
-   [Komutu](../../data/oledb/command-object-interfaces.md)  
  
-   [İşlem](../../data/oledb/transaction-object-interfaces.md)  
  
 OLE DB sağlayıcı şablonları satır ve depolama nesnelerinin kullanılmaz unutmayın.  
  
 Aşağıdaki tabloda, yukarıda listelenen nesneleri için zorunlu ve isteğe bağlı arabirimleri listeler göre [OLE DB 2.6 SDK Belgeleri](https://msdn.microsoft.com/en-us/library/ms722784.aspx).  
  
|Bileşen|Arabirim|Yorum|  
|---------------|---------------|-------------|  
|[Veri kaynağı](../../data/oledb/data-source-object-interfaces.md) ([CDataSource](../../data/oledb/cdatasource-class.md))|[zorunlu] **IDBCreateSession**<br /><br /> [zorunlu] **IDBInitialize**<br /><br /> [zorunlu]`IDBProperties`<br /><br /> [zorunlu]`IPersist`<br /><br /> [isteğe bağlı] **IConnectionPointContainer**<br /><br /> [isteğe bağlı] **IDBAsynchStatus**<br /><br /> [isteğe bağlı] **IDBDataSourceAdmin**<br /><br /> [isteğe bağlı] **IDBInfo'yu**<br /><br /> [isteğe bağlı]`IPersistFile`<br /><br /> [isteğe bağlı] **ISupportErrorInfo**|Sağlayıcı ile tüketici arasındaki bağlantı. Nesne, kullanıcı kimliği, parola ve veri kaynağı adı gibi bağlantı özelliklerini belirtmek için kullanılır. Nesne bir veri kaynağı yönetmek için de kullanılabilir (oluşturmak, güncelleştirmek, silmek, tablolar vb.).|  
|[Oturum](../../data/oledb/session-object-interfaces.md) ([CSession](../../data/oledb/cdataconnection-operator-csession-amp.md))|[zorunlu] **IGetDataSource**<br /><br /> [zorunlu]`IOpenRowset`<br /><br /> [zorunlu] **ISessionProperties**<br /><br /> [isteğe bağlı] **IAlterIndex**<br /><br /> [isteğe bağlı] **IAlterTable**<br /><br /> [isteğe bağlı] **IBindResource**<br /><br /> [isteğe bağlı] **ICreateRow**<br /><br /> [isteğe bağlı] **IDBCreateCommand**<br /><br /> [isteğe bağlı] **IDBSchemaRowset**<br /><br /> [isteğe bağlı] **IIndexDefinition**<br /><br /> [isteğe bağlı] **ISupportErrorInfo**<br /><br /> [isteğe bağlı] **ITableCreation**<br /><br /> [isteğe bağlı] **ITableDefinition**<br /><br /> [isteğe bağlı] **ITableDefinitionWithConstraints**<br /><br /> [isteğe bağlı] **ITransaction**<br /><br /> [isteğe bağlı] **ITransactionJoin'i**<br /><br /> [isteğe bağlı] **ITransactionLocal**<br /><br /> [isteğe bağlı] **ITransactionObject**|Oturum nesnesi bir tüketici ve sağlayıcı arasında tek bir görüşmeyi temsil eder. ODBC biraz benzer **HSTMT** olabilir, fazla eşzamanlı oturum etkin.<br /><br /> Oturum nesnesi için OLE DB işlevselliğini kazanması için birincil bağlantıdır. Komut, işlem veya satır kümesi nesnesi almak için oturum nesnesi gidin.|  
|[Satır kümesi](../../data/oledb/rowset-object-interfaces.md) ([CRowset](../../data/oledb/crowset-class.md))|[zorunlu]`IAccessor`<br /><br /> [zorunlu]`IColumnsInfo`<br /><br /> [zorunlu] **IConvertType**<br /><br /> [zorunlu]`IRowset`<br /><br /> [zorunlu]`IRowsetInfo`<br /><br /> [isteğe bağlı] **IChapteredRowset**<br /><br /> [isteğe bağlı] **IColumnsInfo2**<br /><br /> [isteğe bağlı] **IColumnsRowset**<br /><br /> [isteğe bağlı] **IConnectionPointContainer**<br /><br /> [isteğe bağlı] **IDBAsynchStatus**<br /><br /> [isteğe bağlı] **IGetRow**<br /><br /> [isteğe bağlı]`IRowsetChange`<br /><br /> [isteğe bağlı] **IRowsetChapterMember**<br /><br /> [isteğe bağlı] **IRowsetCurrentIndex**<br /><br /> [isteğe bağlı] **IRowsetFind**<br /><br /> [isteğe bağlı] **IRowsetIdentity**<br /><br /> [isteğe bağlı] **IRowsetIndex**<br /><br /> [isteğe bağlı]`IRowsetLocate`<br /><br /> [isteğe bağlı] **IRowsetRefresh**<br /><br /> [isteğe bağlı]`IRowsetScroll`<br /><br /> [isteğe bağlı]`IRowsetUpdate`<br /><br /> [isteğe bağlı] **IRowsetView**<br /><br /> [isteğe bağlı] **ISupportErrorInfo**<br /><br /> [isteğe bağlı] **IRowsetBookmark**|Satır kümesi nesnesi, veri kaynağından verileri temsil eder. Nesne, bu verileri ve tüm temel (güncelleştirme, getirme, taşıma ve diğerleri) veriler üzerinde işlemler bağlamaları sorumludur. Her zaman içerir ve verileri işlemek için bir satır kümesi nesnesi var.|  
|[Komut](../../data/oledb/command-object-interfaces.md) ([CCommand](http://msdn.microsoft.com/en-us/52bef5da-c1a0-4223-b4e6-9e464b6db409))|[zorunlu]`IAccessor`<br /><br /> [zorunlu]`IColumnsInfo`<br /><br /> [zorunlu]`ICommand`<br /><br /> [zorunlu] **ICommandProperties**<br /><br /> [zorunlu]`ICommandText`<br /><br /> [zorunlu] **IConvertType**<br /><br /> [isteğe bağlı] **IColumnsRowset**<br /><br /> [isteğe bağlı] **ICommandPersist**<br /><br /> [isteğe bağlı] **ICommandPrepare**<br /><br /> [isteğe bağlı]`ICommandWithParameters`<br /><br /> [isteğe bağlı] **ISupportErrorInfo**<br /><br /> [isteğe bağlı] **ICommandStream**|Komut nesnesi verileri sorgular gibi işlemleri gerçekleştirir. Parametreli veya parametresiz deyimleri işleyebilir.<br /><br /> Komut nesnesi, parametreler ve çıktı sütunları için bağlamaları işlemekten sorumludur. Bir bağlama bir satır kümesindeki bir sütuna nasıl alınacağını hakkında bilgi içeren bir yapıdır. Sıra, veri türü, uzunluğu ve durumu gibi bilgileri içerir.|  
|[İşlem](../../data/oledb/transaction-object-interfaces.md) (isteğe bağlı)|[zorunlu] **IConnectionPointContainer**<br /><br /> [zorunlu] **ITransaction**<br /><br /> [isteğe bağlı] **ISupportErrorInfo**|İşlem nesnesi bir veri kaynağında iş atomik bir ölçü tanımlar ve bu iş birimlerinin birbirleriyle nasıl ilişkili olduğunu belirler. Bu nesne OLE DB sağlayıcı şablonları tarafından doğrudan desteklenmeyen (diğer bir deyişle, kendi nesne oluşturma).|  
  
 Daha fazla bilgi için aşağıdaki konulara bakın:  
  
-   [Özellik eşlemeleri](../../data/oledb/property-maps.md)  
  
-   [Kullanıcı kaydı](../../data/oledb/user-record.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB arabirimleri](https://msdn.microsoft.com/en-us/library/ms709709.aspx)