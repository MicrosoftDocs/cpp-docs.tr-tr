---
title: XML Verilerine Erişme
ms.date: 10/18/2018
helpviewer_keywords:
- data access [C++], XML data
- XML [C++], accessing data
- CXMLAccessor class, retrieving XML data
- data [C++], XML data access
- rowsets [C++], retrieving XML data
- CStreamRowset class, retrieving XML data
ms.assetid: 6b693d55-a554-4846-8118-e8773b79b572
ms.openlocfilehash: be4225003211449a98d3fbe5fd686b9b8058a651
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80212283"
---
# <a name="accessing-xml-data"></a>XML Verilerine Erişme

Bir veri kaynağından XML verilerini almanın iki ayrı yöntemi vardır: biri [CStreamRowset](../../data/oledb/cstreamrowset-class.md) kullanır ve diğeri [CXMLAccessor](../../data/oledb/cxmlaccessor-class.md)kullanır.

|İşlev|CStreamRowset|CXMLAccessor|
|-------------------|-------------------|------------------|
|Aktarılan veri miktarı|Tüm sütunlardan ve satırlardaki verileri aynı anda alır.|Tek seferde yalnızca bir satır olmak üzere tüm sütunlardan verileri alır. `MoveNext`gibi yöntemleri kullanarak satırlarda gezinmeniz gerekir.|
|Dizeyi biçimlendirme|SQL Server, XML dizesini biçimlendirir ve tüketiciye gönderir.|Satır kümesi verilerini yerel biçiminde alır (sağlayıcının bunu Unicode dizeleri olarak göndermesini ister) ve sonra verileri XML biçiminde tutan dizeyi oluşturur.|
|Biçimlendirme üzerinde denetim|Bazı SQL Server 2000 özgü özellikleri ayarlayarak XML dizesinin nasıl biçimlendirildiğine ilişkin bir denetim düzeyindedir.|Oluşturulan XML dizesinin biçimi üzerinde denetiminiz yok.|

`CStreamRowset`, verileri XML biçiminde almanın daha genel verimli bir yolunu sağladığından, yalnızca SQL Server 2000 tarafından desteklenir.

## <a name="retrieving-xml-data-using-cstreamrowset"></a>CStreamRowset kullanarak XML verilerini alma

`CCommand` veya `CTable` bildiriminde [CStreamRowset](../../data/oledb/cstreamrowset-class.md) satır kümesi türü olarak belirtirsiniz. Bunu kendi erişimci veya erişimci olmadan kullanabilirsiniz, örneğin:

```cpp
CCommand<CAccessor<CMyAccessor>, CStreamRowset> myCmd;
```

-veya-

```cpp
CCommand<CNoAccessor, CStreamRowset> myCmd;
```

Genellikle `CCommand::Open` çağırdığınızda (örneğin, `TRowset` sınıfı olarak `CRowset` belirterek), bir `IRowset` işaretçisi alır. `ICommand::Execute`, `CRowset` nesnesinin `m_spRowset` üyesinde depolanan `IRowset` bir işaretçi döndürür. `MoveFirst`, `MoveNext`ve `GetData` gibi yöntemler, verileri almak için bu işaretçiyi kullanır.

Buna karşılık, `CCommand::Open` çağırdığınızda (ancak `TRowset` sınıfı olarak `CStreamRowset` belirtirseniz), `ICommand::Execute` [CStreamRowset](../../data/oledb/cstreamrowset-class.md)'in `ISequentialStream` veri üyesinde depolanan bir `m_spStream` işaretçisi döndürür. Daha sonra, (Unicode dize) verilerini XML biçiminde almak için `Read` yöntemini kullanırsınız. Örneğin:

```cpp
myCmd.m_spStream->Read()
```

SQL Server 2000, XML biçimlendirmesini yapar ve tüm sütunları ve satır kümesinin tüm satırlarını tek bir XML dizesi olarak döndürür.

`Read` yöntemi kullanan bir örnek için, bkz. [basit bir tüketici uygulama](../../data/oledb/implementing-a-simple-consumer.md)bölümünde **tüketiciye XML desteği ekleme** .

> [!NOTE]
> `CStreamRowset` kullanarak XML desteği yalnızca SQL Server 2000 ile çalışmaktadır ve SQL Server 2000 için OLE DB sağlayıcısına sahip olmanızı gerektirir (MDAC ile yüklenir).

## <a name="retrieving-xml-data-using-cxmlaccessor"></a>CXMLAccessor kullanarak XML verilerini alma

[CXMLAccessor](../../data/oledb/cxmlaccessor-class.md) , veri deposunun şeması hakkında bilginiz olmadığında veri kaynağındaki verilere dize verileri olarak erişmenizi sağlar. `CXMLAccessor` `CDynamicStringAccessorW` gibi çalışarak, ilki veri deposundan erişilen tüm verileri XML biçimli (etiketli) veriler olarak dönüştürür. XML etiketi adları, veri deposunun sütun adlarıyla mümkün olduğunca yakından eşleşir.

`CCommand` veya `CTable`şablon parametresi olarak geçirerek başka bir erişimci sınıfı gibi `CXMLAccessor` kullanın:

```cpp
CTable<CXMLAccessor, CRowset> rs;
```

Tek seferde tablodaki bir satırdan verileri almak için [GetXMLRowData](../../data/oledb/cxmlaccessor-getxmlrowdata.md) kullanın ve `MoveNext`gibi yöntemleri kullanarak satırlarda gezinme yapın, örneğin:

```cpp
// Open data source, session, and rowset
hr = rs.MoveFirst();

while(SUCCEEDED(hr) && hr != DB_S_ENDOFROWSET )
{
    CStringW strRowData;
    myCmd.GetXMLRowData(strRowData);

    printf_s( "%S\n", strRowData );

    hr = rs.MoveNext();
}
```

[GetXMLColumnData](../../data/oledb/cxmlaccessor-getxmlcolumndata.md) kullanarak sütun (veri türü) bilgilerini xml biçimli dize verileri olarak alabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Erişimcileri Kullanma](../../data/oledb/using-accessors.md)
