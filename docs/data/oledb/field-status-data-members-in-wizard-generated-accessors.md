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
ms.openlocfilehash: 3f1017c3decacfee223f0e0f89267b192208fe7a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33104405"
---
# <a name="field-status-data-members-in-wizard-generated-accessors"></a>Sihirbazın Ürettiği Erişimcilerde Alan Durumu Veri Üyeleri
Bir tüketici oluşturmak için ATL OLE DB Tüketici Sihirbazı'nı kullandığınızda, sihirbaz veri üyesi, sütun eşlemesi belirttiğiniz her bir alan için kullanıcı kayıt sınıfı oluşturur. Her veri üyesi türünde `DWORD` ve ilgili alana karşılık gelen bir durum değeri içerir.  
  
 Örneğin, bir veri üyesi *m_OwnerID*, sihirbaz alan durumu için bir ek veri üyesi oluşturur (*dwOwnerIDStatus*) ve başka bir alan uzunluğu için (*dwOwnerIDLength*). Ayrıca bir sütun eşlemesi ile oluşturur `COLUMN_ENTRY_LENGTH_STATUS` girişleri.  
  
 Bu aşağıdaki kodda gösterilir:  
  
```  
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
>  Kullanıcı kayıt sınıfı değiştirmek veya kendi tüketici yazma, veri değişkenleri durum ve uzunluk değişkenlerinden önce gelmelidir.  
  
 Hata ayıklama amacıyla durum değerlerini kullanabilirsiniz. ATL OLE DB Tüketici Sihirbazı tarafından oluşturulan kod derleme hataları gibi oluşturursa **DB_S_ERRORSOCCURRED** veya **DB_E_ERRORSOCCURRED**, ilk alan durumu geçerli değerlere göz önünde bulundurmanız gerekenler veri üyeleri. Sıfır olmayan değerler olan, soruna neden olan sütunlara karşılık gelir.  
  
 Durum değerleri, belirli bir alan için bir NULL değer ayarlamak için de kullanabilirsiniz. Bunun yapılması, bir alan değeri sıfır yerine NULL olarak ayırt etmek istediğiniz durumlarda yardımcı olur. Bu NULL geçerli bir değer veya özel bir değer olup olmadığına karar vermek ve uygulamanızı bunu nasıl yöneteceğini karar size bağlıdır. OLE DB tanımlar **DBSTATUS_S_ISNULL** olarak genel bir NULL değerini belirtmenin doğru anlamına gelir. Tüketici veri okuyan ve değer null ise, durum alanı kümesine **DBSTATUS_S_ISNULL**. Tüketici NULL değeri ayarlamak istiyorsa tüketici durum değeri ayarlar **DBSTATUS_S_ISNULL** sağlayıcı çağırmadan önce.  
  
 Ardından, biçim açın ve arama **DBSTATUSENUM**. Sıfır olmayan durum karşı sayısal değerini sonra eşleştirebilirsiniz **DBSTATUSENUM** numaralandırma değerleri. Numaralandırma adı neyin yanlış olduğunu söylemek için yeterli değilse, "Bağlama veri değerleri" bölümündeki "Durum" konusuna [OLE DB Programcı Kılavuzu](http://go.microsoft.com/fwlink/p/?linkid=121548). Bu konu, tabloları veri alırken veya ayarlarken kullanılan durum değerlerini içerir. Uzunluk değerleri hakkında daha fazla bilgi için aynı bölüm "Uzunluğu" konusuna bakın.  
  
## <a name="retrieving-the-length-or-status-of-a-column"></a>Uzunluk veya bir sütun durumunu alma  
 Değişken uzunluklu sütun uzunluğu ya da bir sütun durumunu alabilir (denetlemek için **DBSTATUS_S_ISNULL**, örneğin):  
  
-   Uzunluğu almak için kullanmak `COLUMN_ENTRY_LENGTH` makrosu.  
  
-   Durumunu almak için kullanmak `COLUMN_ENTRY_STATUS` makrosu.  
  
-   Her ikisi de almak için `COLUMN_ENTRY_LENGTH_STATUS`, aşağıda gösterildiği gibi.  
  
```  
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
  
 Kullandığınızda `CDynamicAccessor`, uzunluğu ve durumu sizin için otomatik olarak bağlanır. Uzunluk ve durum değerleri almak için kullanmak `GetLength` ve **GetStatus** üye işlevleri.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Tüketici Şablonlarıyla Çalışma](../../data/oledb/working-with-ole-db-consumer-templates.md)