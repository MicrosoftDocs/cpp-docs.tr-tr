---
description: 'Hakkında daha fazla bilgi edinin: veritabanı öznitelikleriyle veri erişimini basitleştirme'
title: Veritabanı Öznitelikleriyle Veri Erişimini Basitleştirme
ms.date: 10/19/2018
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
ms.openlocfilehash: e265c6f59340afb86fdd59c86f78951b9e7cd0df
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97286494"
---
# <a name="simplifying-data-access-with-database-attributes"></a>Veritabanı Öznitelikleriyle Veri Erişimini Basitleştirme

Bu konu, veritabanı işlemlerini basitleştirmek için veritabanı özniteliklerinin kullanımını gösterir.

Bir veritabanından bilgilere erişmenin temel yolu, veritabanında belirli bir tablo için bir komut (veya tablo) sınıfı ve bir kullanıcı kayıt sınıfı oluşturmaktır. Veritabanı öznitelikleri, daha önce yapmak zorunda olduğunuz bazı şablon bildirimlerini basitleştirir.

Veritabanı özniteliklerinin kullanımını göstermek için aşağıdaki bölümlerde iki eşdeğer tablo ve Kullanıcı kayıt sınıfı bildirimleri gösterilmektedir: ilki öznitelikleri ve ikincisi OLE DB şablonları kullanır. Bu tür bildirim kodu genellikle tablo veya komut nesnesi (örneğin, yazarlar. h) adlı bir başlık dosyasına yerleştirilir.

İki dosyayı karşılaştırarak, öznitelikleri kullanmanın ne kadar kolay olduğunu görebilirsiniz. Farklar arasında:

- Öznitelikleri kullanarak yalnızca bir sınıf bildirmeniz gerekir: `CAuthors` , ancak şablonlar ile iki tane bildirmeniz gerekir: `CAuthorsNoAttrAccessor` ve `CAuthorsNoAttr` .

- `db_source`Öznitelikli sürümdeki çağrı, `OpenDataSource()` şablon bildirimindeki çağrıya eşdeğerdir.

- `db_table`Öznitelikli sürümdeki çağrı aşağıdaki şablon bildirimine eşdeğerdir:

    ```cpp
    class CAuthorsNoAttr : public CTable<CAccessor<CAuthorsNoAttrAccessor>>
    ```

- `db_column`Öznitelikli sürümdeki çağrılar, şablon bildiriminde sütun haritasına (bkz `BEGIN_COLUMN_MAP ... END_COLUMN_MAP` .) eşdeğerdir.

Öznitelikleri sizin için bir kullanıcı kayıt sınıfı bildirimi ekler. Kullanıcı kayıt sınıfı, `CAuthorsNoAttrAccessor` şablon bildiriminde eşittir. Tablo sınıfınız ise, `CAuthors` eklenen Kullanıcı kayıt sınıfı adlandırılır `CAuthorsAccessor` ve yalnızca eklenen koddaki bildirimini görüntüleyebilirsiniz. Daha fazla bilgi için [Kullanıcı kayıtlarında](../../data/oledb/user-records.md)"öznitelik eklenmiş Kullanıcı kaydı sınıfları" başlığına bakın.

Hem öznitelikli hem de şablonlu kodda, kullanarak satır kümesi özelliklerini ayarlamanız gerekir `CDBPropSet::AddProperty` .

Bu konuda açıklanan öznitelikler hakkında daha fazla bilgi için bkz. [OLE DB tüketici öznitelikleri](../../windows/attributes/ole-db-consumer-attributes.md).

> [!NOTE]
> Aşağıdaki `include` deyimler aşağıda örnekleri derlemek için gereklidir:

> ```cpp
> #include <atlbase.h>
> #include <atlplus.h>
> #include <atldbcli.h>
> ```

## <a name="table-and-accessor-declaration-using-attributes"></a>Öznitelikleri kullanarak tablo ve erişimci bildirimi

Aşağıdaki kod, `db_source` ve `db_table` tablo sınıfını çağırır. `db_source` kullanılacak veri kaynağını ve bağlantıyı belirtir. `db_table` tablo sınıfı bildirmek için uygun şablon kodunu çıkartır. `db_column` sütun haritasını belirtin ve erişimci bildirimini ekleme. ATL 'yi destekleyen herhangi bir projede OLE DB tüketici öznitelikleri kullanabilirsiniz.

Öznitelikleri kullanan tablo ve erişimci bildirimi aşağıda verilmiştir:

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
   DBSTATUS m_dwAuIDStatus;
   DBSTATUS m_dwAuthorStatus;
   DBSTATUS m_dwYearBornStatus;
   DBLENGTH m_dwAuIDLength;
   DBLENGTH m_dwAuthorLength;
   DBLENGTH m_dwYearBornLength;
   [db_column("1", status = "m_dwAuIDStatus", length = "m_dwAuIDLength")] LONG m_AuID;
   [db_column("2", status = "m_dwAuthorStatus", length = "m_dwAuthorLength")] TCHAR m_Author[51];
   [db_column("3", status = "m_dwYearBornStatus", length = "m_dwYearBornLength")] SHORT m_YearBorn;
   void GetRowsetProperties(CDBPropSet* pPropSet)
   {
      pPropSet->AddProperty(DBPROP_CANFETCHBACKWARDS, true);
      pPropSet->AddProperty(DBPROP_CANSCROLLBACKWARDS, true);
      pPropSet->AddProperty(DBPROP_IRowsetChange, true);
   }
};
```

## <a name="table-and-accessor-declaration-using-templates"></a>Şablonları kullanarak tablo ve erişimci bildirimi

Şablonlar kullanılarak tablo ve erişimci bildirimi aşağıda verilmiştir.

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

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB tüketici öznitelikleri](../../windows/attributes/ole-db-consumer-attributes.md)
