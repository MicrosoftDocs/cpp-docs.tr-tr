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
ms.openlocfilehash: e665369f292a646353d1a180661982ce4c902665
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="simplifying-data-access-with-database-attributes"></a>Veritabanı Öznitelikleriyle Veri Erişimini Basitleştirme
Bu konu, veritabanı işlemleri basitleştirmek için veritabanı özelliklerinin kullanımını gösterir.  
  
 Bir veritabanından bilgilere erişmek için temel bir komut (veya tablo) ve bir kullanıcı kaydı sınıfı belirli bir tablo için veritabanının oluşturulacağı yoludur. Veritabanı öznitelikleri daha önce yapmak zorunda olduğunuz şablon bildirimlerinin bazılarını basitleştirir.  
  
 Veritabanı öznitelikleri kullanımını göstermek için aşağıdaki bölümleri iki eşdeğer tablo ve kullanıcı kayıt sınıf bildirimleri göster: ilk öznitelikleri ve ikinci OLE DB Şablonları kullanır. Böyle bir bildirim kodu genellikle tablo ya da komut nesnesi için adlandırılmış bir üstbilgi dosyası Örneğin, Authors.h yerleştirilir.  
  
 İki dosya karşılaştırarak, öznitelikleri kullanmak ne kadar kolay olduğunu görebilirsiniz. Arasındaki farklar şunlardır:  
  
-   Öznitelikleri kullanarak, yalnızca bir sınıf bildirmeniz gerekir: `CAuthors`iki bildirmek sahip şablonlarıyla: `CAuthorsNoAttrAccessor` ve `CAuthorsNoAttr`.  
  
-   `db_source` Öznitelikli sürümdeki çağrıdır eşdeğer `OpenDataSource()` şablon bildirimindeki çağırın.  
  
-   **Db_table** Öznitelikli sürümdeki çağrısı aşağıdaki şablon bildirimine eşdeğerdir:  
  
    ```  
    class CAuthorsNoAttr : public CTable<CAccessor<CAuthorsNoAttrAccessor>>  
    ```  
  
-   **Db_column** öznitelikli sürüm çağrılarında sütun eşlemesi eşdeğer (bkz: `BEGIN_COLUMN_MAP ... END_COLUMN_MAP`) şablonu bildirimi.  
  
 Öznitelikleri sizin için bir kullanıcı kayıt sınıfı bildirimi yerleştirir. Kullanıcı kayıt sınıfı eşdeğerdir `CAuthorsNoAttrAccessor` şablon bildirimi. Tablo sınıfınız ise `CAuthors`, eklenen kullanıcı kayıt sınıfı adlı `CAuthorsAccessor`, eklenen kodda yalnızca bildiriminden görüntüleyebilirsiniz. Daha fazla bilgi için bkz: "Öznitelik eklenmiş kullanıcı kayıt sınıfları" [kullanıcı kayıtlarını](../../data/oledb/user-records.md).  
  
 Öznitelikli hem şablonlu kod de, satır kümesi özelliklerini kullanarak ayarlamalısınız Not `CDBPropSet::AddProperty`.  
  
 Bu konuda tartışılan öznitelikler hakkında daha fazla bilgi için bkz: [OLE DB tüketici öznitelikleri](../../windows/ole-db-consumer-attributes.md).  
  
## <a name="table-and-accessor-declaration-using-attributes"></a>Tablo ve Erişimci Beyanı öznitelikleri kullanma  
 Aşağıdaki kod çağrıları `db_source` ve **db_table** tablo sınıfında. `db_source` kullanılacak bağlantı ve veri kaynağını belirtir. **db_table** tablo sınıfı bildirmek için uygun şablon kodunu ekler. **db_column** sütun eşlemesi belirtin ve erişimci bildirimini ekleyin. OLE DB tüketici öznitelikleri ATL destekleyen herhangi bir projede kullanabilirsiniz  
  
 Öznitelikleri kullanarak tablo ve erişen bildirimi aşağıda verilmiştir:  
  
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
  
## <a name="table-and-accessor-declaration-using-templates"></a>Tablo ve Erişimci Beyanı şablonlarını kullanma  
 Şablonları kullanarak tablo ve erişen bildirimi aşağıda verilmiştir.  
  
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
 [OLE DB tüketici öznitelikleri](../../windows/ole-db-consumer-attributes.md)   
 [Öznitelikleri izlenecek yollar](http://msdn.microsoft.com/en-us/73df1d5d-261a-4521-98fb-06dcbf5ec0d0)