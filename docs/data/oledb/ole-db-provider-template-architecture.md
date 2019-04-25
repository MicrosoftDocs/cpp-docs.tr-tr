---
title: OLE DB Sağlayıcı Şablonu Mimarisi
ms.date: 11/19/2018
helpviewer_keywords:
- OLE DB [C++], object model
- architecture [C++], OLE DB Provider
- OLE DB provider templates, object model
ms.assetid: 639304a3-f9e0-44dc-8d0c-0ebd2455b363
ms.openlocfilehash: 65a7e5b8f169d06ca11d8d27ec99ce3db4b63014
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62283997"
---
# <a name="ole-db-provider-template-architecture"></a>OLE DB Sağlayıcı Şablonu Mimarisi

## <a name="data-sources-and-sessions"></a>Veri Kaynakları ve Oturumlar

OLE DB sağlayıcı mimarisi, bir veri kaynağı nesnesi ve bir veya daha fazla oturum içerir. Veri kaynağı nesnesinin her sağlayıcı örneği gerekir ilk nesnedir. Bir tüketici uygulama verilere ihtiyaç duyduğunda birlikte sağlayıcıyı başlatmak için veri kaynağı nesnesi oluşturur. Veri kaynağı nesnesi bir oturum nesnesi oluşturur (kullanarak `IDBCreateSession` arabirimi) için veri kaynağı nesnesinin tüketici bağlayan aracılığıyla. ODBC programcıları düşünme eşdeğer olarak veri kaynağı nesnesinin `HENV` ve eşdeğer olarak oturum nesnesi `HDBC`.

![Sağlayıcı mimarisi](../../data/oledb/media/vc4twb1.gif "sağlayıcı mimarisi")

Tarafından oluşturulan kaynak dosyalarıyla birlikte **OLE DB sağlayıcısı Sihirbazı**, OLE DB Şablonları bir veri kaynağı nesnesi uygular. OLE DB için karşılık gelen bir nesne oturumdur `TSession`.

## <a name="mandatory-and-optional-interfaces"></a>Zorunlu ve isteğe bağlı arabirimler

OLE DB sağlayıcı şablonları, önceden paketlenmiş uygulamalar için gerekli tüm arabirimleri sağlar. Zorunlu ve isteğe bağlı arabirimler çeşitli nesneleri için OLE DB tanımlanır:

- [Veri kaynağı](../../data/oledb/data-source-object-interfaces.md)

- [Oturum](../../data/oledb/session-object-interfaces.md)

- [Satır kümesi](../../data/oledb/rowset-object-interfaces.md)

- [Komutu](../../data/oledb/command-object-interfaces.md)

- [İşlem](../../data/oledb/transaction-object-interfaces.md)

OLE DB sağlayıcı şablonları satır ve depolama nesnelerinin kullanılmaz.

Aşağıdaki tabloda, yukarıda listelenen nesneler için zorunlu ve isteğe bağlı arabirimler listelenmiştir göre [OLE DB 2.6 SDK Belgeleri](/previous-versions/windows/desktop/ms722784(v=vs.85)).

|Bileşen|Arabirim|Yorum|
|---------------|---------------|-------------|
|[Veri kaynağı](../../data/oledb/data-source-object-interfaces.md) ([CDataSource](../../data/oledb/cdatasource-class.md))|[zorunlu] `IDBCreateSession`<br /><br /> [zorunlu] `IDBInitialize`<br /><br /> [zorunlu] `IDBProperties`<br /><br /> [zorunlu] `IPersist`<br /><br /> [isteğe bağlı] `IConnectionPointContainer`<br /><br /> [isteğe bağlı] `IDBAsynchStatus`<br /><br /> [isteğe bağlı] `IDBDataSourceAdmin`<br /><br /> [isteğe bağlı] `IDBInfo`<br /><br /> [isteğe bağlı] `IPersistFile`<br /><br /> [isteğe bağlı] `ISupportErrorInfo`|Sağlayıcı için tüketici bağlantısı. Nesnesi, kullanıcı Kimliğinizi, parolanızı ve veri kaynağı adı gibi bağlantı özelliklerini belirtmek için kullanılır. Nesne veri kaynağı yönetmek için de kullanılabilir (oluşturmak, güncelleştirmek, tablo, silme ve benzeri).|
|[Oturum](../../data/oledb/session-object-interfaces.md) ([CSession](../../data/oledb/cdataconnection-operator-csession-amp.md))|[zorunlu] `IGetDataSource`<br /><br /> [zorunlu] `IOpenRowset`<br /><br /> [zorunlu] `ISessionProperties`<br /><br /> [isteğe bağlı] `IAlterIndex`<br /><br /> [isteğe bağlı] `IAlterTable`<br /><br /> [isteğe bağlı] `IBindResource`<br /><br /> [isteğe bağlı] `ICreateRow`<br /><br /> [isteğe bağlı] `IDBCreateCommand`<br /><br /> [isteğe bağlı] `IDBSchemaRowset`<br /><br /> [isteğe bağlı] `IIndexDefinition`<br /><br /> [isteğe bağlı] `ISupportErrorInfo`<br /><br /> [isteğe bağlı] `ITableCreation`<br /><br /> [isteğe bağlı] `ITableDefinition`<br /><br /> [isteğe bağlı] `ITableDefinitionWithConstraints`<br /><br /> [isteğe bağlı] `ITransaction`<br /><br /> [isteğe bağlı] `ITransactionJoin`<br /><br /> [isteğe bağlı] `ITransactionLocal`<br /><br /> [isteğe bağlı] `ITransactionObject`|Bir müşteri ve sağlayıcı arasında tek bir konuşma oturum nesnedir. ODBC benzer `HSTMT` olabilir, birçok eş zamanlı oturumların etkin.<br /><br /> Oturum nesnesi, OLE DB işlevselliğine erişmek için birincil bağlantıdır. Komut, işlem veya satır kümesi nesnesi almak için oturum nesnesini gözden geçirin.|
|[Satır kümesi](../../data/oledb/rowset-object-interfaces.md) ([CRowset](../../data/oledb/crowset-class.md))|[zorunlu] `IAccessor`<br /><br /> [zorunlu] `IColumnsInfo`<br /><br /> [zorunlu] `IConvertType`<br /><br /> [zorunlu] `IRowset`<br /><br /> [zorunlu] `IRowsetInfo`<br /><br /> [isteğe bağlı] `IChapteredRowset`<br /><br /> [isteğe bağlı] `IColumnsInfo2`<br /><br /> [isteğe bağlı] `IColumnsRowset`<br /><br /> [isteğe bağlı] `IConnectionPointContainer`<br /><br /> [isteğe bağlı] `IDBAsynchStatus`<br /><br /> [isteğe bağlı] `IGetRow`<br /><br /> [isteğe bağlı] `IRowsetChange`<br /><br /> [isteğe bağlı] `IRowsetChapterMember`<br /><br /> [isteğe bağlı] `IRowsetCurrentIndex`<br /><br /> [isteğe bağlı] `IRowsetFind`<br /><br /> [isteğe bağlı] `IRowsetIdentity`<br /><br /> [isteğe bağlı] `IRowsetIndex`<br /><br /> [isteğe bağlı] `IRowsetLocate`<br /><br /> [isteğe bağlı] `IRowsetRefresh`<br /><br /> [isteğe bağlı] `IRowsetScroll`<br /><br /> [isteğe bağlı] `IRowsetUpdate`<br /><br /> [isteğe bağlı] `IRowsetView`<br /><br /> [isteğe bağlı] `ISupportErrorInfo`<br /><br /> [isteğe bağlı] `IRowsetBookmark`|Satır kümesi nesnesi, veri kaynağından alınan verilerdir. Nesnesi, bu verileri veri çubuğunda temel işlemleri (güncelleştirme, alma, taşıma ve diğerleri) ve bağlamaları için kullanılır. Her zaman tutmak ve veri işlemek için bir satır kümesi nesnesi var.|
|[Command](../../data/oledb/command-object-interfaces.md) ([CCommand](ccommand-class.md))|[zorunlu] `IAccessor`<br /><br /> [zorunlu] `IColumnsInfo`<br /><br /> [zorunlu] `ICommand`<br /><br /> [zorunlu] `ICommandProperties`<br /><br /> [zorunlu] `ICommandText`<br /><br /> [zorunlu] `IConvertType`<br /><br /> [isteğe bağlı] `IColumnsRowset`<br /><br /> [isteğe bağlı] `ICommandPersist`<br /><br /> [isteğe bağlı] `ICommandPrepare`<br /><br /> [isteğe bağlı] `ICommandWithParameters`<br /><br /> [isteğe bağlı] `ISupportErrorInfo`<br /><br /> [isteğe bağlı] `ICommandStream`|Komut nesnesi, sorgular gibi veri işlemlerini işler. Bu, parametreli forceseek ifade başa çıkabilir.<br /><br /> Komut nesnesi, parametreleri ve çıkış sütunları için bağlamaları işlenmesinden sorumludur. Bir bağlama bir satır kümesindeki bir sütun nasıl alınacağını hakkında bilgi içeren bir yapıdır. Sıra, veri türü, uzunluğu ve durumu gibi bilgileri içerir.|
|[İşlem](../../data/oledb/transaction-object-interfaces.md) (isteğe bağlı)|[zorunlu] `IConnectionPointContainer`<br /><br /> [zorunlu] `ITransaction`<br /><br /> [isteğe bağlı] `ISupportErrorInfo`|İşlem nesnesi, bir veri kaynağında atomik bir iş birimi tanımlar ve bu iş birimleri birbirleriyle nasıl ilişki kuracağını belirler. Bu nesne OLE DB sağlayıcı şablonları tarafından doğrudan desteklenmiyor (diğer bir deyişle, kendi nesne oluştur).|

Daha fazla bilgi için aşağıdaki konulara bakın:

- [Özellik Eşlemeleri](../../data/oledb/property-maps.md)

- [Kullanıcı kaydı](../../data/oledb/user-record.md)

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB arabirimleri](/previous-versions/windows/desktop/ms709709(v=vs.85))<br/>
