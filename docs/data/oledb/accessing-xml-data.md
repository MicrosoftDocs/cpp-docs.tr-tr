---
title: "XML verilerine erişme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- data access [C++], XML data
- XML [C++], accessing data
- CXMLAccessor class, retrieving XML data
- data [C++], XML data access
- rowsets [C++], retrieving XML data
- CStreamRowset class, retrieving XML data
ms.assetid: 6b693d55-a554-4846-8118-e8773b79b572
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4cccb224553bc217bbbcd37030f03419f6f5d55e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="accessing-xml-data"></a>XML Verilerine Erişme
XML verilerini bir veri kaynağından veri almak için iki ayrı yöntem vardır: biri kullanır [CStreamRowset](../../data/oledb/cstreamrowset-class.md) ve diğer kullanımlar [CXMLAccessor](../../data/oledb/cxmlaccessor-class.md).  
  
|İşlevi|CStreamRowset|CXMLAccessor|  
|-------------------|-------------------|------------------|  
|Aktarılan veri miktarı|Verileri aynı anda tüm sütunları ve satırları alır.|Tüm sütunları verilerden ancak aynı anda yalnızca bir satır alır. Satırları gibi yöntemleri kullanarak gitmeniz gerekir `MoveNext`.|  
|Biçimlendirme dizesi|SQL Server XML dizesi biçimlendirir ve tüketiciye gönderir.|Satır kümesi verileri yerel biçiminde (sağlayıcı Unicode dizeleri olarak gönderin istekleri) alır ve XML biçimindeki verileri içeren dize oluşturur.|  
|Biçimlendirme denetimi|Belirli bir düzeyde bazı SQL Server 2000 özgü özellikleri ayarlayarak XML dizesi nasıl biçimlendirildiğini üzerinde denetime sahip.|Oluşturulan XML dizesi biçimi üzerinde hiçbir denetimi yoktur.|  
  
 Sırada `CStreamRowset` , yalnızca desteklenen SQL Server 2000 tarafından XML biçiminde veri almanın daha fazla genel verimli şekilde sağlar.  
  
## <a name="retrieving-xml-data-using-cstreamrowset"></a>CStreamRowset kullanarak XML verilerini alma  
 Belirttiğiniz [CStreamRowset](../../data/oledb/cstreamrowset-class.md) satır kümesi türü olarak, `CCommand` veya `CTable` bildirimi. Bunu kendi erişimcisi veya erişimcisine, örneğin kullanabilirsiniz:  
  
```  
CCommand<CAccessor<CMyAccessor>, CStreamRowset> myCmd;  
```  
  
 veya  
  
```  
CCommand<CNoAccessor, CStreamRowset> myCmd;  
```  
  
 Çağırdığınızda normalde `CCommand::Open` (belirtme, örneğin, `CRowset` olarak `TRowset` sınıfı), alır bir `IRowset` işaretçi. `ICommand::Execute`döndüren bir `IRowset` depolanan işaretçi `m_spRowset` üyesi `CRowset` nesnesi. Gibi yöntemler `MoveFirst`, `MoveNext`, ve `GetData` verileri almak için bu işaretçiyi kullanın.  
  
 Çağırdığınızda aksine, `CCommand::Open` (ancak belirtin `CStreamRowset` olarak `TRowset` sınıfı), `ICommand::Execute` döndüren bir `ISequentialStream` depolanan işaretçi `m_spStream` veri üyesi [CStreamRowset](../../data/oledb/cstreamrowset-class.md). Daha sonra `Read` XML biçiminde (UNICODE dizesi) verileri almak üzere yöntemi. Örneğin:  
  
```  
myCmd.m_spStream->Read()  
```  
  
 SQL Server 2000 XML biçimlendirmesini gerçekleştirir ve tüm sütunları ve satır kümesinin bir XML dizesi olarak tüm satırları döndürür.  
  
 Bir örnek kullanmak için `Read` yöntemi, "Ekleme XML destek tüketiciye" bölümüne bakın [basit tüketici uygulama](../../data/oledb/implementing-a-simple-consumer.md).  
  
> [!NOTE]
>  XML desteği kullanarak `CStreamRowset` yalnızca SQL Server 2000 ile çalışır ve SQL Server 2000 (MDAC ile yüklenmiş) için bir OLE DB sağlayıcısı sahip olmasını gerektirir.  
  
## <a name="retrieving-xml-data-using-cxmlaccessor"></a>CXMLAccessor kullanarak XML verilerini alma  
 [CXMLAccessor](../../data/oledb/cxmlaccessor-class.md) veri deposunun şeması hiçbir bilgiye sahip olduğunda veri dize verilerini bir veri kaynağından erişmenize olanak tanır. `CXMLAccessor`gibi çalışır `CDynamicStringAccessorW` dışında eski veri deposu XML biçimli (etiketli) veri olarak erişilen tüm verileri dönüştürür. XML etiket adları mümkün olduğunca yakın veri deposunun sütun adlarının eşleşmesi.  
  
 Kullanım `CXMLAccessor` diğer bir erişimci sınıfı gibi bir şablon parametresi olarak geçirme `CCommand` veya `CTable`:  
  
```  
CTable<CXMLAccessor, CRowset> rs;  
```  
  
 Kullanım [GetXMLRowData](../../data/oledb/cxmlaccessor-getxmlrowdata.md) aynı anda tablo bir satırdaki verileri almak ve gibi yöntemleri kullanarak satırları gezinmek için `MoveNext`, örneğin:  
  
```  
// Open data source, session, and rowset  
hr = rs.MoveFirst();  
while( SUCCEEDED(hr) && hr != DB_S_ENDOFROWSET )  
{  
    CStringW strRowData;  
    myCmd.GetXMLRowData(strRowData);  
  
    printf_s( "%S\n", strRowData );  
  
    hr = rs.MoveNext();  
}  
```  
  
 Kullanabileceğiniz [GetXMLColumnData](../../data/oledb/cxmlaccessor-getxmlcolumndata.md) XML biçimli dize veri olarak sütun (veri türü) bilgisini almak için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Erişimcileri kullanma](../../data/oledb/using-accessors.md)