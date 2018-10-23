---
title: Alan durumu veri üyeleri sihirbazın ürettiği Erişimcilerde | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB consumer templates, field status
- field status in OLE DB templates
ms.assetid: 66e4e223-c60c-471e-860d-d23abcdfe371
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ce3ad819b6e22bfb5c760849e5f3fdf85bd4f7bc
ms.sourcegitcommit: 0164af5615389ffb1452ccc432eb55f6dc931047
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49809102"
---
# <a name="field-status-data-members-in-wizard-generated-accessors"></a>Sihirbazın Ürettiği Erişimcilerde Alan Durumu Veri Üyeleri

Bir tüketici oluşturma için ATL OLE DB Tüketicisi Sihirbazı kullandığınızda, sihirbazın veri üyesi, sütun eşlemesinde belirttiğiniz her bir alan için kullanıcı kayıt sınıfı oluşturur. Her veri üyesi türünde `DWORD` ve kendi ilgili alana karşılık gelen bir durum değeri içerir.  
  
Örneğin, bir veri üyesi için *m_OwnerID*, alan durumu için bir ek veri üyesi sihirbaz oluşturur (*dwOwnerIDStatus*) ve başka bir alan uzunluğu için (*dwOwnerIDLength*). Ayrıca, bir sütun eşlemesi COLUMN_ENTRY_LENGTH_STATUS girişi oluşturur.  
  
Bu, aşağıdaki kodda gösterilmiştir:  
  
```cpp  
[db_source("insert connection string")]  
[db_command(" \  
   SELECT \  
      Au_ID, \  
      Author, \  
      `Year Born`, \  
      FROM Authors")]  
  
class CAuthors  
{  
public:  
  
   // The following wizard-generated data members contain status   
   // values for the corresponding fields in the column map. You   
   // can use these values to hold NULL values that the database   
   // returns or to hold error information when the compiler returns   
   // errors. See "Field Status Data Members in Wizard-Generated   
   // Accessors" in the Visual C++ documentation for more information   
   // on using these fields.  
   DWORD m_dwAuIDStatus;  
   DWORD m_dwAuthorStatus;  
   DWORD m_dwYearBornStatus;  
  
   // The following wizard-generated data members contain length  
   // values for the corresponding fields in the column map.  
   DWORD m_dwAuIDLength;  
   DWORD m_dwAuthorLength;  
   DWORD m_dwYearBornLength;  
  
BEGIN_COLUMN_MAP(CAuthorsAccessor)  
   COLUMN_ENTRY_LENGTH_STATUS(1, m_AuID, dwAuIDLength, dwAuIDStatus)  
   COLUMN_ENTRY_LENGTH_STATUS(2, m_Author, dwAuthorLength, dwAuthorStatus)  
   COLUMN_ENTRY_LENGTH_STATUS(3, m_YearBorn, dwYearBornLength, dwYearBornStatus)  
END_COLUMN_MAP()  
  
   [ db_column(1, status=m_dwAuIDStatus, length=m_dwAuIDLength) ] LONG m_AuID;  
   [ db_column(2, status=m_dwAuthorStatus, length=m_dwAuthorLength) ] TCHAR m_Author[51];  
   [ db_column(3, status=m_dwYearBornStatus, length=m_dwYearBornLength) ] SHORT m_YearBorn;  
  
   void GetRowsetProperties(CDBPropSet* pPropSet)  
   {  
      pPropSet->AddProperty(DBPROP_IRowsetChange, true);  
      pPropSet->AddProperty(DBPROP_UPDATABILITY, DBPROPVAL_UP_CHANGE | DBPROPVAL_UP_INSERT | DBPROPVAL_UP_DELETE);  
   }  
};  
```  
  
> [!NOTE]
> Kullanıcı kayıt sınıfı değiştirin ya da kendi tüketici yazma, verileri değişkenleri durum ve uzunluğu değişkenlerinden önce gelmelidir.  
  
Hata ayıklama amacıyla durum değerleri kullanabilirsiniz. ATL OLE DB Tüketici Sihirbazı tarafından oluşturulan kod derleme gibi DB_S_ERRORSOCCURRED veya DB_E_ERRORSOCCURRED oluşturursa, alan durumu veri üyeleri, geçerli değerlere önce görünmelidir. Sıfır olmayan değerler sahip olanlar sorunlu sütunlara karşılık gelir.  
  
Durum değerleri, belirli bir alan için bir NULL değer ayarlamak için de kullanabilirsiniz. Bunun yapılması, bir alan değeri sıfır yerine NULL olarak ayırmak istediğiniz durumlarda yardımcı olur. Bu NULL geçerli bir değer veya özel bir değeri olup olmadığına karar vermenize ve uygulamanızı bunu nasıl işleyeceğini karar size bağlıdır. OLE DB DBSTATUS_S_ISNULL genel bir NULL değer belirtme doğru şekilde tanımlar. Tüketici verileri okur ve değer null ise, Durum alanını DBSTATUS_S_ISNULL ayarlanır. Bir NULL değer ayarlamak tüketici isterse, tüketici sağlayıcı çağırmadan önce DBSTATUS_S_ISNULL durum değeri ayarlar.  
  
Ardından, biçim ve DBSTATUSENUM araması açın. Ardından, sıfır olmayan durum DBSTATUSENUM numaralandırma değerlerinden karşı sayısal değerini eşleşebilir. Sabit listesi adı neyin yanlış olduğunu söylemek için yeterli değilse, "Bağlama veri değerleri" bölümünde "Durum" konusuna [OLE DB Programcı Kılavuzu](/previous-versions/windows/desktop/ms713643). Bu konu, veri alma veya ayarlarken kullanılan durum değerleri tabloları içerir. Uzunluk değerleri hakkında daha fazla bilgi için aynı bölüme "Uzunluğu" bölümüne bakın.  
  
## <a name="retrieving-the-length-or-status-of-a-column"></a>Uzunluk veya bir sütun durumunu alma  

Bir değişken uzunluklu sütun uzunluğu ya da bir sütun (DBSTATUS_S_ISNULL için örneğin denetlemek için) durumunu alabilirsiniz:  
  
- Uzunluğu almak için COLUMN_ENTRY_LENGTH makrosu kullanın.  
  
- Durumu almak için COLUMN_ENTRY_STATUS makrosu kullanın.  
  
- Her ikisini de almak için COLUMN_ENTRY_LENGTH_STATUS, aşağıda gösterildiği gibi kullanın.  
  
```cpp  
class CProducts  
{  
public:  
   char      szName[40];  
   long      nNameLength;  
   DBSTATUS   nNameStatus;  
  
BEGIN_COLUMN_MAP(CProducts)  
// Bind the column to CProducts.m_ProductName.  
// nOrdinal is zero-based, so the column number of m_ProductName is 1.  
   COLUMN_ENTRY_LENGTH_STATUS(1, szName, nNameLength, nNameStatus)  
END_COLUMN_MAP()  
};  
  
CTable<CAccessor<CProducts >> product;  
  
product.Open(session, "Product");  

while (product.MoveNext() == S_OK)  
{  
   // Check the product name isn't NULL before tracing it  
   if (product.nNameStatus == DBSTATUS_S_OK)  
      ATLTRACE("%s is %d characters\n", szName, nNameLength);  
}  
```  
  
Kullanırken `CDynamicAccessor`, uzunluğu ve durum sizin için otomatik olarak bağlanır. Uzunluğu ve durum değerleri almak için kullanın `GetLength` ve `GetStatus` üye işlevleri.  
  
## <a name="see-also"></a>Ayrıca Bkz.  

[OLE DB Tüketici Şablonlarıyla Çalışma](../../data/oledb/working-with-ole-db-consumer-templates.md)