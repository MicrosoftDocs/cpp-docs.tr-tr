---
description: 'Daha fazla bilgi edinin: OLE DB sağlayıcı şablonu mimarisi'
title: OLE DB Sağlayıcı Şablonu Mimarisi
ms.date: 11/19/2018
helpviewer_keywords:
- OLE DB [C++], object model
- architecture [C++], OLE DB Provider
- OLE DB provider templates, object model
ms.assetid: 639304a3-f9e0-44dc-8d0c-0ebd2455b363
ms.openlocfilehash: 1cc1619ab7ed13c2d7962f75229df2ecd8cf0d78
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97317135"
---
# <a name="ole-db-provider-template-architecture"></a>OLE DB Sağlayıcı Şablonu Mimarisi

## <a name="data-sources-and-sessions"></a>Veri Kaynakları ve Oturumlar

OLE DB sağlayıcısı mimarisi bir veri kaynağı nesnesi ve bir veya daha fazla oturum içerir. Veri kaynağı nesnesi, her sağlayıcının örneği oluşturması gereken ilk nesnedir. Bir tüketici uygulamasının veri ihtiyacı olduğunda, sağlayıcıyı başlatmak için veri kaynağı nesnesini birlikte oluşturur. Veri kaynağı nesnesi, `IDBCreateSession` tüketicinin veri kaynağı nesnesine bağlandığı bir oturum nesnesi (arabirimini kullanarak) oluşturur. ODBC programcıları, veri kaynağı nesnesini `HENV` ile eşdeğer olarak ve oturum nesnesine eşdeğer olarak düşünebilir `HDBC` .

![Sağlayıcı mimarisi](../../data/oledb/media/vc4twb1.gif "Sağlayıcı mimarisi")

**OLE DB sağlayıcı Sihirbazı** tarafından oluşturulan kaynak dosyalarla birlikte, OLE DB şablonları bir veri kaynağı nesnesi uygular. Oturum, OLE DB karşılık gelen bir nesnedir `TSession` .

## <a name="mandatory-and-optional-interfaces"></a>Zorunlu ve Isteğe bağlı arabirimler

OLE DB sağlayıcı şablonları, tüm gerekli arabirimlerin önceden paketlenmiş uygulamalarını sağlar. Zorunlu ve isteğe bağlı arabirimler birkaç tür nesne için OLE DB tarafından tanımlanır:

- [Veri kaynağı](../../data/oledb/data-source-object-interfaces.md)

- [Oturum](../../data/oledb/session-object-interfaces.md)

- [Kümesi](../../data/oledb/rowset-object-interfaces.md)

- [Komut](../../data/oledb/command-object-interfaces.md)

- [İşlem](../../data/oledb/transaction-object-interfaces.md)

OLE DB sağlayıcı şablonları, satır ve depolama nesnelerini uygulamaz.

Aşağıdaki tabloda, [OLE DB 2,6 SDK belgelerine](/previous-versions/windows/desktop/ms722784(v=vs.85))göre yukarıda listelenen nesneler için zorunlu ve isteğe bağlı arabirimler listelenmektedir.

|Bileşen|Arabirim|Yorum|
|---------------|---------------|-------------|
|[Veri kaynağı](../../data/oledb/data-source-object-interfaces.md) ([CDataSource](../../data/oledb/cdatasource-class.md))|girilmesi `IDBCreateSession`<br /><br /> girilmesi `IDBInitialize`<br /><br /> girilmesi `IDBProperties`<br /><br /> girilmesi `IPersist`<br /><br /> seçim `IConnectionPointContainer`<br /><br /> seçim `IDBAsynchStatus`<br /><br /> seçim `IDBDataSourceAdmin`<br /><br /> seçim `IDBInfo`<br /><br /> seçim `IPersistFile`<br /><br /> seçim `ISupportErrorInfo`|Tüketiciden sağlayıcıya bağlantı. Nesne, bağlantıda Kullanıcı KIMLIĞI, parola ve veri kaynağı adı gibi özellikleri belirtmek için kullanılır. Nesne ayrıca bir veri kaynağını (oluşturma, güncelleştirme, silme, tablolar vb.) yönetmek için de kullanılabilir.|
|[Oturum](../../data/oledb/session-object-interfaces.md) ([CSession](./cdataconnection-class.md#op_csession_amp))|girilmesi `IGetDataSource`<br /><br /> girilmesi `IOpenRowset`<br /><br /> girilmesi `ISessionProperties`<br /><br /> seçim `IAlterIndex`<br /><br /> seçim `IAlterTable`<br /><br /> seçim `IBindResource`<br /><br /> seçim `ICreateRow`<br /><br /> seçim `IDBCreateCommand`<br /><br /> seçim `IDBSchemaRowset`<br /><br /> seçim `IIndexDefinition`<br /><br /> seçim `ISupportErrorInfo`<br /><br /> seçim `ITableCreation`<br /><br /> seçim `ITableDefinition`<br /><br /> seçim `ITableDefinitionWithConstraints`<br /><br /> seçim `ITransaction`<br /><br /> seçim `ITransactionJoin`<br /><br /> seçim `ITransactionLocal`<br /><br /> seçim `ITransactionObject`|Oturum nesnesi, bir tüketici ve sağlayıcı arasında tek bir konuşmadan yapılır. `HSTMT`Birçok eşzamanlı oturumu etkin hale getirebilirsiniz.<br /><br /> Oturum nesnesi OLE DB işlevselliğine ulaşmak için birincil bağlantıdır. Bir komut, işlem veya satır kümesi nesnesine ulaşmak için oturum nesnesine gidin.|
|[Satır kümesi](../../data/oledb/rowset-object-interfaces.md) ([CRowset](../../data/oledb/crowset-class.md))|girilmesi `IAccessor`<br /><br /> girilmesi `IColumnsInfo`<br /><br /> girilmesi `IConvertType`<br /><br /> girilmesi `IRowset`<br /><br /> girilmesi `IRowsetInfo`<br /><br /> seçim `IChapteredRowset`<br /><br /> seçim `IColumnsInfo2`<br /><br /> seçim `IColumnsRowset`<br /><br /> seçim `IConnectionPointContainer`<br /><br /> seçim `IDBAsynchStatus`<br /><br /> seçim `IGetRow`<br /><br /> seçim `IRowsetChange`<br /><br /> seçim `IRowsetChapterMember`<br /><br /> seçim `IRowsetCurrentIndex`<br /><br /> seçim `IRowsetFind`<br /><br /> seçim `IRowsetIdentity`<br /><br /> seçim `IRowsetIndex`<br /><br /> seçim `IRowsetLocate`<br /><br /> seçim `IRowsetRefresh`<br /><br /> seçim `IRowsetScroll`<br /><br /> seçim `IRowsetUpdate`<br /><br /> seçim `IRowsetView`<br /><br /> seçim `ISupportErrorInfo`<br /><br /> seçim `IRowsetBookmark`|Satır kümesi nesnesi veri kaynağından alınan veri. Nesnesi bu verilerin bağlamaları ve veriler üzerinde herhangi bir temel işlem (güncelleştirme, getirme, taşıma ve diğerleri) için kullanılır. Verileri tutmak ve işlemek için her zaman bir satır kümesi nesneniz vardır.|
|[Komut](../../data/oledb/command-object-interfaces.md) ([CCommand](ccommand-class.md))|girilmesi `IAccessor`<br /><br /> girilmesi `IColumnsInfo`<br /><br /> girilmesi `ICommand`<br /><br /> girilmesi `ICommandProperties`<br /><br /> girilmesi `ICommandText`<br /><br /> girilmesi `IConvertType`<br /><br /> seçim `IColumnsRowset`<br /><br /> seçim `ICommandPersist`<br /><br /> seçim `ICommandPrepare`<br /><br /> seçim `ICommandWithParameters`<br /><br /> seçim `ISupportErrorInfo`<br /><br /> seçim `ICommandStream`|Komut nesnesi sorgular gibi veriler üzerinde işlemleri işler. Parametreli veya parametreli olmayan deyimleri işleyebilir.<br /><br /> Komut nesnesi Ayrıca parametreler ve çıkış sütunları için bağlamaları işlemekten sorumludur. Bağlama, bir satır kümesindeki bir sütunun nasıl alınması gerektiği hakkında bilgi içeren bir yapıdır. Sıra, veri türü, uzunluk ve durum gibi bilgileri içerir.|
|[İşlem](../../data/oledb/transaction-object-interfaces.md) (isteğe bağlı)|girilmesi `IConnectionPointContainer`<br /><br /> girilmesi `ITransaction`<br /><br /> seçim `ISupportErrorInfo`|İşlem nesnesi bir veri kaynağında atomik bir iş birimi tanımlar ve bu iş birimlerinin birbirleriyle nasıl ilgili olduğunu belirler. Bu nesne OLE DB sağlayıcı şablonları tarafından doğrudan desteklenmez (diğer bir deyişle, kendi nesneniz oluşturursunuz).|

Daha fazla bilgi edinmek için aşağıdaki kaynaklara bakın:

- [Özellik eşlemeleri](../../data/oledb/property-maps.md)

- [Kullanıcı kaydı](../../data/oledb/user-record.md)

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB arabirimleri](/previous-versions/windows/desktop/ms709709(v=vs.85))<br/>
