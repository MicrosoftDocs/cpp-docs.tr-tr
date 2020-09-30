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
ms.openlocfilehash: 437f1d103420ec5727294894c02587c68cffbdda
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91509135"
---
# <a name="accessing-xml-data"></a>XML Verilerine Erişme

Bir veri kaynağından XML verilerini almanın iki ayrı yöntemi vardır: biri [CStreamRowset](../../data/oledb/cstreamrowset-class.md) kullanır ve diğeri [CXMLAccessor](../../data/oledb/cxmlaccessor-class.md)kullanır.

|İşlev|CStreamRowset|CXMLAccessor|
|-------------------|-------------------|------------------|
|Aktarılan veri miktarı|Tüm sütunlardan ve satırlardaki verileri aynı anda alır.|Tek seferde yalnızca bir satır olmak üzere tüm sütunlardan verileri alır. Gibi yöntemleri kullanarak satırlarda gezinmeniz gerekir `MoveNext` .|
|Dizeyi biçimlendirme|SQL Server, XML dizesini biçimlendirir ve tüketiciye gönderir.|Satır kümesi verilerini yerel biçiminde alır (sağlayıcının bunu Unicode dizeleri olarak göndermesini ister) ve sonra verileri XML biçiminde tutan dizeyi oluşturur.|
|Biçimlendirme üzerinde denetim|Bazı SQL Server 2000 özgü özellikleri ayarlayarak XML dizesinin nasıl biçimlendirildiğine ilişkin bir denetim düzeyindedir.|Oluşturulan XML dizesinin biçimi üzerinde denetiminiz yok.|

`CStreamRowset`VERILERI XML biçiminde almanın daha genel verimli bir yolu sağlar, ancak yalnızca SQL Server 2000 tarafından desteklenir.

## <a name="retrieving-xml-data-using-cstreamrowset"></a>CStreamRowset kullanarak XML verilerini alma

Or bildirimindeki satır kümesi türü olarak [CStreamRowset](../../data/oledb/cstreamrowset-class.md) belirtirsiniz `CCommand` `CTable` . Bunu kendi erişimci veya erişimci olmadan kullanabilirsiniz, örneğin:

```cpp
CCommand<CAccessor<CMyAccessor>, CStreamRowset> myCmd;
```

-veya-

```cpp
CCommand<CNoAccessor, CStreamRowset> myCmd;
```

Genellikle çağırdığınızda `CCommand::Open` (örneğin, `CRowset` `TRowset` sınıf olarak), bir `IRowset` işaretçi alır. `ICommand::Execute``IRowset`nesnenin üyesinde depolanan bir işaretçi döndürür `m_spRowset` `CRowset` . , Ve gibi yöntemler, `MoveFirst` `MoveNext` `GetData` verileri almak için bu işaretçiyi kullanır.

Bunun aksine, öğesini çağırdığınızda `CCommand::Open` (ancak `CStreamRowset` sınıfı olarak belirttiğinizde `TRowset` ), `ICommand::Execute` `ISequentialStream` `m_spStream` [CStreamRowset](../../data/oledb/cstreamrowset-class.md)'in veri üyesinde depolanan bir işaretçi döndürür. Daha sonra, `Read` (Unicode dize) VERILERINI XML biçiminde almak için yöntemini kullanabilirsiniz. Örneğin:

```cpp
myCmd.m_spStream->Read()
```

SQL Server 2000, XML biçimlendirmesini yapar ve tüm sütunları ve satır kümesinin tüm satırlarını tek bir XML dizesi olarak döndürür.

Yöntemini kullanarak bir örnek için `Read` bkz. [basit bir tüketici uygulama](../../data/oledb/implementing-a-simple-consumer.md)bölümünde **tüketiciye XML desteği ekleme** .

> [!NOTE]
> `CStreamRowset`Yalnızca SQL Server 2000 ile birlikte ÇALıŞARAK XML desteği, SQL Server 2000 için OLE DB sağlayıcısına sahip olmanızı gerektirir (MDAC ile yüklenir).

## <a name="retrieving-xml-data-using-cxmlaccessor"></a>CXMLAccessor kullanarak XML verilerini alma

[CXMLAccessor](../../data/oledb/cxmlaccessor-class.md) , veri deposunun şeması hakkında bilginiz olmadığında veri kaynağındaki verilere dize verileri olarak erişmenizi sağlar. `CXMLAccessor` daha `CDynamicStringAccessorW` önce, veri deposundan erişilen tüm VERILER XML biçimli (etiketli) veriler olarak dönüştürülemediği için de geçerlidir. XML etiketi adları, veri deposunun sütun adlarıyla mümkün olduğunca yakından eşleşir.

`CXMLAccessor`Diğer herhangi bir erişimci sınıfı gibi kullanın, bunu bir şablon parametresi olarak veya öğesine geçirerek `CCommand` yapın `CTable` :

```cpp
CTable<CXMLAccessor, CRowset> rs;
```

Tek seferde tablodaki bir satırdan verileri almak için [GetXMLRowData](./cxmlaccessor-class.md#getxmlrowdata) kullanın ve gibi yöntemleri kullanarak satırlarda gezinme yapın `MoveNext` , örneğin:

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

[GetXMLColumnData](./cxmlaccessor-class.md#getxmlcolumndata) kullanarak sütun (veri türü) bilgilerini xml biçimli dize verileri olarak alabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Erişimcileri kullanma](../../data/oledb/using-accessors.md)
