---
title: Veritabanı öznitelikleriyle veri erişimini basitleştirme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- vc-attr.db_param
- vc-attr.db_column
- vc-attr.db_accessor
- vc-attr.db_command
- vc-attr.db_table
- vc-attr.db_source
dev_langs:
- C++
helpviewer_keywords:
- attributes [C++], database
- attributes [C++], data access
- databases [C++], attributes
- data [C++], simplifying access
- data access [C++], database attributes
- database attributes [C++]
- OLE DB consumers [C++], database attributes
- attributes [C++], OLE DB consumer
ms.assetid: 560d2456-e307-4cb7-ba7b-4d0ed674697f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a9897be9bbcae0a03ef67996bda6f3ffbe894b8f
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43680458"
---
# <a name="simplifying-data-access-with-database-attributes"></a>Veritabanı Öznitelikleriyle Veri Erişimini Basitleştirme
Bu konu, veritabanı işlemleri basitleştirmek için veritabanı öznitelikleri kullanımını gösterir.  
  
 Bir veritabanından bilgilere erişmek için temel yolu komutu (veya tablo) bir sınıfı ve belirli bir tablo için bir kullanıcı kayıt sınıfı veritabanında oluşturmaktır. Veritabanı öznitelikleri bazı önceden yapmak zorunda şablon bildirimleri basitleştirin.  
  
 Veritabanı öznitelikleri kullanımını göstermek için aşağıdaki bölümleri iki eşdeğer tablo ve kullanıcı kayıt sınıf bildirimleri göster: ilk öznitelikleri ve ikinci OLE DB Şablonları kullanır. Bu tür bildirimi kod genellikle adlı tablo veya komut nesnesi için bir üstbilgi dosyası gibi Authors.h yerleştirilir.  
  
 İki dosyayı karşılaştırarak öznitelikleri ne kadar kolay olduğunu görebilirsiniz. Arasındaki farklar şunlardır:  
  
-   Öznitelikleri kullanarak, yalnızca bir sınıf bildirmeniz gerekir: `CAuthors`iki bildirmenize gerek şablonlarıyla korurken: `CAuthorsNoAttrAccessor` ve `CAuthorsNoAttr`.  
  
-   `db_source` Öznitelikli sürümdeki çağrısı eşdeğer `OpenDataSource()` şablon bildiriminde çağırın.  
  
-   `db_table` Öznitelikli sürümdeki çağrısı için aşağıdaki şablon bildirimi eşdeğerdir:  
  
    ```  
    class CAuthorsNoAttr : public CTable<CAccessor<CAuthorsNoAttrAccessor>>  
    ```  
  
-   `db_column` Öznitelikli çağrılarında sütun eşlemesi için eşdeğer olan (bkz `BEGIN_COLUMN_MAP ... END_COLUMN_MAP`) şablon bildirimindeki.  
  
 Öznitelikleri sizin için bir kullanıcı kaydı sınıf bildirimi ekleyin. Kullanıcı kayıt sınıfı eşdeğerdir `CAuthorsNoAttrAccessor` şablon bildirimindeki. Tablo sınıfınız varsa `CAuthors`, eklenen kullanıcı kayıt sınıfı adlı `CAuthorsAccessor`, ve bildiriminden eklenen kodun yalnızca görüntüleyebilir. Daha fazla bilgi için bkz: "Öznitelik eklenmiş kullanıcı kayıt sınıfları" [kullanıcı kayıtlarını](../../data/oledb/user-records.md).  
  
 Hem öznitelikli ve şablonlu kodu, kullanarak satır kümesi özelliklerini ayarlamanız gerekir `CDBPropSet::AddProperty`.  
  
 Bu konuda tartışılan öznitelikleri hakkında daha fazla bilgi için bkz: [OLE DB tüketici öznitelikleri](../../windows/ole-db-consumer-attributes.md).  
  
## <a name="table-and-accessor-declaration-using-attributes"></a>Tablo ve öznitelikleri kullanarak erişimci bildirimi  
 Aşağıdaki kod çağrıları `db_source` ve `db_table` tablo sınıfı üzerinde. `db_source` kullanılacak bağlantı ve veri kaynağını belirtir. `db_table` bir tablo sınıfı bildirmek için uygun şablonu kodu ekler. `db_column` Sütun eşlemesi belirtin ve erişimci bildirimini ekleyin. ATL destekleyen herhangi bir projede kullanabileceğiniz OLE DB tüketici öznitelikleri  
  
 Öznitelikleri kullanarak tablo ve erişimcisi bildirimi şu şekildedir:  
  
```cpp
//////////////////////////////////////////////////////////////////////  
// Table and accessor declaration using attributes  
// authors.h  
//////////////////////////////////////////////////////////////////////  
  
// Table class declaration  
// (Note that you must provide your own connection string for db_source.)  
[  
   db_source(L"your connection string"),  
   db_table("Authors")  
]  
class CAuthors  
{  
public:  
   DWORD m_dwAuIDStatus;  
   DWORD m_dwAuthorStatus;  
   DWORD m_dwYearBornStatus;  
   DWORD m_dwAuIDLength;  
   DWORD m_dwAuthorLength;  
   DWORD m_dwYearBornLength;  
   [ db_column(1, status=m_dwAuIDStatus, length=m_dwAuIDLength) ] LONG m_AuID;  
   [ db_column(2, status=m_dwAuthorStatus, length=m_dwAuthorLength) ] TCHAR m_Author[51];  
   [ db_column(3, status=m_dwYearBornStatus, length=m_dwYearBornLength) ] SHORT m_YearBorn;  
   void GetRowsetProperties(CDBPropSet* pPropSet)  
   {  
      pPropSet->AddProperty(DBPROP_CANFETCHBACKWARDS, true);  
      pPropSet->AddProperty(DBPROP_CANSCROLLBACKWARDS, true);  
      pPropSet->AddProperty(DBPROP_IRowsetChange, true);  
   }  
};  
```  
  
## <a name="table-and-accessor-declaration-using-templates"></a>Tablo ve şablonları kullanarak erişimci bildirimi  
 Şablonları kullanarak tablo ve erişimcisi bildirimi aşağıda verilmiştir.  
  
```cpp
//////////////////////////////////////////////////////////////////////  
// Table and user record class declaration using templates  
// authors.h  
//////////////////////////////////////////////////////////////////////  
  
// User record class declaration  
class CAuthorsNoAttrAccessor  
{  
public:  
   DWORD m_dwAuIDStatus;  
   DWORD m_dwAuthorStatus;  
   DWORD m_dwYearBornStatus;  
   DWORD m_dwAuIDLength;  
   DWORD m_dwAuthorLength;  
   DWORD m_dwYearBornLength;  
   LONG m_AuID;  
   TCHAR m_Author[51];  
   SHORT m_YearBorn;  
   void GetRowsetProperties(CDBPropSet* pPropSet)  
   {  
      pPropSet->AddProperty(DBPROP_CANFETCHBACKWARDS, true);  
      pPropSet->AddProperty(DBPROP_CANSCROLLBACKWARDS, true);  
      pPropSet->AddProperty(DBPROP_IRowsetChange, true);  
   }  
   HRESULT OpenDataSource()  
   {  
      CDataSource _db;  

HRESULT hr;  
      hr = _db.OpenFromInitializationString(L"your connection string");  
      if (FAILED(hr))  
      {  
#ifdef _DEBUG  
         AtlTraceErrorRecords(hr);  
#endif  
         return hr;  
      }  
      return m_session.Open(_db);  
   }  
   void CloseDataSource()  
   {  
      m_session.Close();  
   }  
   operator const CSession&()  
   {  
      return m_session;  
   }  
   CSession m_session;  
   BEGIN_COLUMN_MAP(CAuthorsNoAttrAccessor)  
      COLUMN_ENTRY_LENGTH_STATUS(1, m_AuID, m_dwAuIDLength, m_dwAuIDStatus)  
      COLUMN_ENTRY_LENGTH_STATUS(2, m_Author, m_dwAuthorLength, m_dwAuthorStatus)  
      COLUMN_ENTRY_LENGTH_STATUS(3, m_YearBorn, m_dwYearBornLength, m_dwYearBornStatus)  
   END_COLUMN_MAP()  
};  
class CAuthorsNoAttr : public CTable<CAccessor<CAuthorsNoAttrAccessor>>  
{  
public:  
   HRESULT OpenAll()  
   {  
HRESULT hr;  
      hr = OpenDataSource();  
      if (FAILED(hr))  
         return hr;  
      __if_exists(GetRowsetProperties)  
      {  
         CDBPropSet propset(DBPROPSET_ROWSET);  
         __if_exists(HasBookmark)  
         {  
            propset.AddProperty(DBPROP_IRowsetLocate, true);  
         }  
         GetRowsetProperties(&propset);  
         return OpenRowset(&propset);  
      }  
      __if_not_exists(GetRowsetProperties)  
      {  
         __if_exists(HasBookmark)  
         {  
            CDBPropSet propset(DBPROPSET_ROWSET);  
            propset.AddProperty(DBPROP_IRowsetLocate, true);  
            return OpenRowset(&propset);  
         }  
      }  
      return OpenRowset();  
   }  
   HRESULT OpenRowset(DBPROPSET *pPropSet = NULL)  
   {  
HRESULT hr = Open(m_session, "Authors", pPropSet);  
#ifdef _DEBUG  
      if(FAILED(hr))  
         AtlTraceErrorRecords(hr);  
#endif  
      return hr;  
   }  
   void CloseAll()  
   {  
      Close();  
      CloseDataSource();  
   }  
};  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Tüketici Öznitelikleri](../../windows/ole-db-consumer-attributes.md)   
