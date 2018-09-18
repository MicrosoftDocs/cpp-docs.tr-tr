---
title: XML verilerine erişme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- data access [C++], XML data
- XML [C++], accessing data
- CXMLAccessor class, retrieving XML data
- data [C++], XML data access
- rowsets [C++], retrieving XML data
- CStreamRowset class, retrieving XML data
ms.assetid: 6b693d55-a554-4846-8118-e8773b79b572
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: cfde3980e58ba86d6923eaac765332a23e40ad7e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46062507"
---
# <a name="accessing-xml-data"></a>XML Verilerine Erişme

XML verileri bir veri kaynağından veri almak için iki ayrı yöntem vardır: biri [CStreamRowset](../../data/oledb/cstreamrowset-class.md) ve diğer kullanımları [CXMLAccessor](../../data/oledb/cxmlaccessor-class.md).  
  
|İşlevi|CStreamRowset|CXMLAccessor|  
|-------------------|-------------------|------------------|  
|Aktarılan veri miktarı|Verileri tek seferde tüm sütunları ve satırları alır.|Tüm sütunları verilerden ancak aynı anda yalnızca bir satır alır. Satırlar gibi yöntemlerle gitmeniz gerekir `MoveNext`.|  
|Biçimlendirme dizesi|SQL Server XML dizesi olarak biçimlendirir ve tüketiciye gönderir.|Satır kümesi verileri yerel biçiminde (sağlayıcı Unicode dize olarak gönderin isteği) alır ve ardından XML biçiminde veriler içeren bir dize oluşturur.|  
|Biçimlendirme denetimi|Belirli bir düzeyde bazı SQL Server 2000 özgü özelliklerini ayarlayarak XML dizesi nasıl biçimlendirildiğini denetim var.|Oluşturulan XML dizesi biçimi üzerinde denetiminiz yoktur.|  
  
Sırada `CStreamRowset` XML biçiminde veri alma, daha fazla bir genel etkili yöntem, yalnızca desteklenen SQL Server 2000 tarafından sağlar.  
  
## <a name="retrieving-xml-data-using-cstreamrowset"></a>CStreamRowset kullanarak XML verilerini alma  

Belirttiğiniz [CStreamRowset](../../data/oledb/cstreamrowset-class.md) satır kümesi türü olarak sizin `CCommand` veya `CTable` bildirimi. Bunu kendi erişimci veya erişimci, örneğin kullanabilirsiniz:  
  
```cpp  
CCommand<CAccessor<CMyAccessor>, CStreamRowset> myCmd;  
```  
  
veya  
  
```cpp  
CCommand<CNoAccessor, CStreamRowset> myCmd;  
```  
  
Normalde çağırdığınızda `CCommand::Open` (belirterek, örneğin, `CRowset` olarak `TRowset` sınıfı), alır bir `IRowset` işaretçi. `ICommand::Execute` döndürür bir `IRowset` depolanan işaretçi `m_spRowset` üyesi `CRowset` nesne. Yöntemler gibi `MoveFirst`, `MoveNext`, ve `GetData` verilerini almak için bu işaretçiyi kullanın.  
  
Bunun aksine, çağırdığınızda `CCommand::Open` (ancak `CStreamRowset` olarak `TRowset` sınıfı), `ICommand::Execute` döndürür bir `ISequentialStream` depolanan işaretçi `m_spStream` veri üyesi [CStreamRowset](../../data/oledb/cstreamrowset-class.md). Daha sonra `Read` XML biçiminde (Unicode dize) veri almak için yöntemi. Örneğin:  
  
```cpp  
myCmd.m_spStream->Read()  
```  
  
SQL Server 2000, XML biçimlendirme gerçekleştirir ve tüm sütun ve satır kümesinin bir XML dizesi olarak tüm satırları döndürür.  
  
Bir örnek için `Read` yöntemi, "Ekleyerek XML destek tüketiciye" bölümüne bakın [basit tüketici uygulama](../../data/oledb/implementing-a-simple-consumer.md).  
  
> [!NOTE]
>  XML desteği kullanarak `CStreamRowset` yalnızca çalışan SQL Server 2000 ve SQL Server 2000 (MDAC yüklü) için bir OLE DB sağlayıcısı sahip olmasını gerektirir.  
  
## <a name="retrieving-xml-data-using-cxmlaccessor"></a>CXMLAccessor kullanarak XML verilerini alma  

[CXMLAccessor](../../data/oledb/cxmlaccessor-class.md) olanağıyla veri deposunun şeması olduğunda veri dize verileri bir veri kaynağından erişmenize olanak sağlar. `CXMLAccessor` gibi çalışır `CDynamicStringAccessorW` dışında önceki XML biçimli (etiketli) veri veri deposundan erişilen tüm verileri dönüştürür. XML etiket adları veri deposunun sütun adları mümkün olduğunca eşleştirin.  
  
Kullanım `CXMLAccessor` başka bir erişimci sınıfı gibi bir şablon parametresi olarak geçirerek `CCommand` veya `CTable`:  
  
```cpp  
CTable<CXMLAccessor, CRowset> rs;  
```  
  
Kullanım [GetXMLRowData](../../data/oledb/cxmlaccessor-getxmlrowdata.md) aynı anda tablo bir satırdaki verileri almak ve satırlar gibi yöntemlerle gitmek için `MoveNext`, örneğin:  
  
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
  
Kullanabileceğiniz [GetXMLColumnData](../../data/oledb/cxmlaccessor-getxmlcolumndata.md) XML biçimli dize verileri olarak sütun (veri türü) bilgileri alınamıyor.  
  
## <a name="see-also"></a>Ayrıca Bkz.  

[Erişimcileri Kullanma](../../data/oledb/using-accessors.md)