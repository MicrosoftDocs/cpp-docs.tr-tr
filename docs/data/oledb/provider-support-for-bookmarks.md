---
description: 'Hakkında daha fazla bilgi edinin: yer Işaretleri için sağlayıcı desteği'
title: Yer İşaretleri Sağlayıcı Desteği
ms.date: 11/04/2016
helpviewer_keywords:
- IRowsetLocate class, provider support for bookmarks
- OLE DB provider templates, bookmarks
- bookmarks, OLE DB
- IRowsetLocate class
- OLE DB providers, bookmark support
ms.assetid: 1b14ccff-4f76-462e-96ab-1aada815c377
ms.openlocfilehash: 0a2225f44d9d094f52e97b88eb58c6942906edf6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97286663"
---
# <a name="provider-support-for-bookmarks"></a>Yer İşaretleri Sağlayıcı Desteği

Bu konudaki örnek, `IRowsetLocate` arabirimini `CCustomRowset` sınıfına ekler. Neredeyse tüm durumlarda, var olan bir COM nesnesine bir arabirim ekleyerek başlayın. Daha sonra tüketici şablonlarından daha fazla çağrı ekleyerek test edebilirsiniz. Örnek, nasıl yapılacağını göstermektedir:

- Sağlayıcıya arabirim ekleme.

- Tüketiciye döndürülecek sütunları dinamik olarak belirleme.

- Yer işareti desteği ekleyin.

`IRowsetLocate`Arabirim `IRowset` arabiriminden devralır. Arabirimi eklemek için `IRowsetLocate` , `CCustomRowset` [IRowsetLocateImpl](../../data/oledb/irowsetlocateimpl-class.md)'den devralma.

Arabirimi eklemek, `IRowsetLocate` çoğu arabirimden farklı bir bittir. VTABLEs 'ın ölçeğini oluşturmak için, OLE DB sağlayıcı şablonlarının türetilmiş arabirimi işlemek için bir şablon parametresi vardır. Aşağıdaki kod, yeni devralma listesini gösterir:

```cpp
////////////////////////////////////////////////////////////////////////
// CustomRS.h

// CCustomRowset
class CCustomRowset : public CRowsetImpl< CCustomRowset,
      CTextData, CCustomCommand, CAtlArray<CTextData>,
      CSimpleRow,
          IRowsetLocateImpl<CCustomRowset, IRowsetLocate>>
```

Dördüncü, beşinci ve altıncı parametrelerin hepsi eklenmiştir. Bu örnek, dördüncü ve beşinci parametreler için varsayılan değerleri kullanır, ancak `IRowsetLocateImpl` altıncı parametre olarak belirtin. `IRowsetLocateImpl` , iki şablon parametresi alan bir OLE DB Şablon sınıfıdır: Bu, `IRowsetLocate` arabirimini `CCustomRowset` sınıfına yedekler. Birçok arabirimi eklemek için bu adımı atlayabilir ve bir sonrakine geçebilirsiniz. Yalnızca `IRowsetLocate` ve `IRowsetScroll` arabirimlerinin bu şekilde işlenmesi gerekir.

Daha sonra `CCustomRowset` arayüzü için çağrısına söylemeniz gerekir `QueryInterface` `IRowsetLocate` . Satırı haritaya ekleyin `COM_INTERFACE_ENTRY(IRowsetLocate)` . İçin arabirim eşlemesi `CCustomRowset` aşağıdaki kodda gösterildiği gibi görünmelidir:

```cpp
////////////////////////////////////////////////////////////////////////
// CustomRS.h

typedef CRowsetImpl< CCustomRowset, CTextData, CCustomCommand, CAtlArray<CTextData>, CSimpleRow, IRowsetLocateImpl<CCustomRowset, IRowsetLocate>> _RowsetBaseClass;

BEGIN_COM_MAP(CCustomRowset)
   COM_INTERFACE_ENTRY(IRowsetLocate)
   COM_INTERFACE_ENTRY_CHAIN(_RowsetBaseClass)
END_COM_MAP()
```

Ayrıca, eşlemenizi sınıfına da eklemeniz gerekir `CRowsetImpl` . Haritada kanca eklemek için COM_INTERFACE_ENTRY_CHAIN makroya ekleyin `CRowsetImpl` . Ayrıca, devralma bilgilerinden oluşan adlı bir typedef oluşturun `RowsetBaseClass` . Bu typedef rastgele ve yoksayılabilir.

Son olarak, `IColumnsInfo::GetColumnsInfo` çağrıyı işleyin. Bunu yapmak için normalde PROVIDER_COLUMN_ENTRY makroları kullanırsınız. Ancak, bir tüketici yer işaretlerini kullanmak isteyebilir. Tüketicinin bir yer işareti isteyip istemediği, sağlayıcının döndürdüğü sütunları değiştirebilmelisiniz.

Çağrıyı işlemek için `IColumnsInfo::GetColumnsInfo` , sınıfındaki PROVIDER_COLUMN haritasını silin `CTextData` . PROVIDER_COLUMN_MAP makrosu bir işlevi tanımlar `GetColumnInfo` . Kendi `GetColumnInfo` işlevinizi tanımlayın. İşlev bildirimi şöyle görünmelidir:

```cpp
////////////////////////////////////////////////////////////////////////
// CustomRS.H

class CTextData
{
   ...
     // NOTE: Be sure you removed the PROVIDER_COLUMN_MAP!
   static ATLCOLUMNINFO* GetColumnInfo(CCustomRowset* pThis,
        ULONG* pcCols);
   static ATLCOLUMNINFO* GetColumnInfo(CCustomCommand* pThis,
        ULONG* pcCols);
...
};
```

Ardından, `GetColumnInfo` Işlevi *özel* RS. cpp dosyasında aşağıdaki gibi uygulayın:

```cpp
////////////////////////////////////////////////////////////////////
// CustomRS.cpp

template <class TInterface>
ATLCOLUMNINFO* CommonGetColInfo(IUnknown* pPropsUnk, ULONG* pcCols)
{
   static ATLCOLUMNINFO _rgColumns[5];
   ULONG ulCols = 0;

   CComQIPtr<TInterface> spProps = pPropsUnk;

   CDBPropIDSet set(DBPROPSET_ROWSET);
   set.AddPropertyID(DBPROP_BOOKMARKS);
   DBPROPSET* pPropSet = NULL;
   ULONG ulPropSet = 0;
   HRESULT hr;

   if (spProps)
      hr = spProps->GetProperties(1, &set, &ulPropSet, &pPropSet);

   // Check the property flag for bookmarks, if it is set, set the
// zero ordinal entry in the column map with the bookmark
// information.

   if (pPropSet)
   {
      CComVariant var = pPropSet->rgProperties[0].vValue;
      CoTaskMemFree(pPropSet->rgProperties);
      CoTaskMemFree(pPropSet);

      if ((SUCCEEDED(hr) && (var.boolVal == VARIANT_TRUE)))
      {
         ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Bookmark"), 0,
                     sizeof(DWORD), DBTYPE_BYTES,
            0, 0, GUID_NULL, CAgentMan, dwBookmark,
                        DBCOLUMNFLAGS_ISBOOKMARK)
         ulCols++;
      }
   }

   // Next set the other columns up.
   ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Field1"), 1, 16, DBTYPE_STR,
          0xFF, 0xFF, GUID_NULL, CTextData, szField1)
   ulCols++;
   ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Field2"), 2, 16, DBTYPE_STR,
       0xFF, 0xFF, GUID_NULL, CTextData, szField2)
   ulCols++;

   if (pcCols != NULL)
      *pcCols = ulCols;

   return _rgColumns;
}

ATLCOLUMNINFO* CTextData::GetColumnInfo(CCustomCommand* pThis,
     ULONG* pcCols)
{
   return CommonGetColInfo<ICommandProperties>(pThis->GetUnknown(),
        pcCols);
}

ATLCOLUMNINFO* CAgentMan::GetColumnInfo(RUpdateRowset* pThis, ULONG* pcCols)
{
   return CommonGetColInfo<IRowsetInfo>(pThis->GetUnknown(), pcCols);
}
```

`GetColumnInfo` İlk olarak, çağrılan bir özelliğin ayarlanmış olup olmadığını kontrol eder `DBPROP_IRowsetLocate` . OLE DB, satır kümesi nesnesindeki isteğe bağlı arabirimlerin her biri için özelliklere sahiptir. Tüketici, bu isteğe bağlı arabirimlerden birini kullanmak isterse, bir özelliği true olarak ayarlar. Sağlayıcı daha sonra bu özelliği denetleyebilir ve temel alınarak özel eylem gerçekleştirebilir.

Uygulamanızda, komut nesnesine yönelik işaretçiyi kullanarak özelliği alırsınız. `pThis`İşaretçi satır kümesi veya komut sınıfını temsil eder. Burada şablonları kullandığınız için, bunu bir işaretçi olarak geçirmeniz **`void`** veya kodun derlenmeyeceği olması gerekir.

Sütun bilgilerini tutacak bir statik dizi belirtin. Tüketici, yer işareti sütununu istemiyor, dizideki bir giriş boşa harcanmış olur. Bu diziyi dinamik olarak ayırabilirsiniz, ancak doğru şekilde yok etmeniz gerekir. Bu örnek ADD_COLUMN_ENTRY makroları tanımlar ve kullanır ve bilgileri diziye eklemek için ADD_COLUMN_ENTRY_EX. Makroları *özel* RS 'ye ekleyebilirsiniz. H dosyası aşağıdaki kodda gösterildiği gibi:

```cpp
////////////////////////////////////////////////////////////////////////
// CustomRS.h

#define ADD_COLUMN_ENTRY(ulCols, name, ordinal, colSize, type, precision, scale, guid, dataClass, member) \
   _rgColumns[ulCols].pwszName = (LPOLESTR)name; \
   _rgColumns[ulCols].pTypeInfo = (ITypeInfo*)NULL; \
   _rgColumns[ulCols].iOrdinal = (ULONG)ordinal; \
   _rgColumns[ulCols].dwFlags = 0; \
   _rgColumns[ulCols].ulColumnSize = (ULONG)colSize; \
   _rgColumns[ulCols].wType = (DBTYPE)type; \
   _rgColumns[ulCols].bPrecision = (BYTE)precision; \
   _rgColumns[ulCols].bScale = (BYTE)scale; \
   _rgColumns[ulCols].cbOffset = offsetof(dataClass, member);

#define ADD_COLUMN_ENTRY_EX(ulCols, name, ordinal, colSize, type, precision, scale, guid, dataClass, member, flags) \
   _rgColumns[ulCols].pwszName = (LPOLESTR)name; \
   _rgColumns[ulCols].pTypeInfo = (ITypeInfo*)NULL; \
   _rgColumns[ulCols].iOrdinal = (ULONG)ordinal; \
   _rgColumns[ulCols].dwFlags = flags; \
   _rgColumns[ulCols].ulColumnSize = (ULONG)colSize; \
   _rgColumns[ulCols].wType = (DBTYPE)type; \
   _rgColumns[ulCols].bPrecision = (BYTE)precision; \
   _rgColumns[ulCols].bScale = (BYTE)scale; \
   _rgColumns[ulCols].cbOffset = offsetof(dataClass, member); \
   memset(&(_rgColumns[ulCols].columnid), 0, sizeof(DBID)); \
   _rgColumns[ulCols].columnid.uName.pwszName = (LPOLESTR)name;
```

Tüketicideki kodu test etmek için, işleyicide birkaç değişiklik yapmanız gerekir `OnRun` . İşlevine yapılan ilk değişiklik, özellik kümesine bir özellik eklemek için kod eklemektir. Kod, `DBPROP_IRowsetLocate` özelliği true olarak ayarlar, böylece sağlayıcıya Bookmark sütununu istediğinizi söyleyerek. `OnRun`İşleyici kodu aşağıdaki gibi görünmelidir:

```cpp
//////////////////////////////////////////////////////////////////////
// TestProv Consumer Application in TestProvDlg.cpp

void CTestProvDlg::OnRun()
{
   CCommand<CAccessor<CProvider>> table;
   CDataSource source;
   CSession   session;

   if (source.Open("Custom.Custom.1", NULL, NULL, NULL,
          NULL) != S_OK)
      return;

   if (session.Open(source) != S_OK)
      return;

   CDBPropSet propset(DBPROPSET_ROWSET);
   propset.AddProperty(DBPROP_IRowsetLocate, true);
   if (table.Open(session, _T("c:\\public\\testprf2\\myData.txt"),
          &propset) != S_OK)
      return;

   CBookmark<4> tempBookmark;
   ULONG ulCount=0;
   while (table.MoveNext() == S_OK)
   {

      DBCOMPARE compare;
      if (ulCount == 2)
         tempBookmark = table.bookmark;

HRESULT hr = table.Compare(table.dwBookmark, table.dwBookmark,
                 &compare);
      if (FAILED(hr))
         ATLTRACE(_T("Compare failed: 0x%X\n"), hr);
      else
         _ASSERTE(compare == DBCOMPARE_EQ);

      m_ctlString1.AddString(table.szField1);
      m_ctlString2.AddString(table.szField2);
      ulCount++;
   }

   table.MoveToBookmark(tempBookmark);
   m_ctlString1.AddString(table.szField1);
   m_ctlString2.AddString(table.szField2);
}
```

**`while`** Döngü, arabirimindeki yöntemi çağırmak için kod içerir `Compare` `IRowsetLocate` . Tam olarak aynı yer imlerini karşılaştırdığınız için, sahip olduğunuz kod her zaman geçmelidir. Ayrıca, bir yer işaretini geçici bir değişkende depolayın, böylece **`while`** döngü tamamlandıktan sonra `MoveToBookmark` işlevi tüketici şablonlarında çağırın. `MoveToBookmark`İşlevi `GetRowsAt` içindeki yöntemini çağırır `IRowsetLocate` .

Ayrıca, tüketicideki Kullanıcı kaydını da güncelleştirmeniz gerekir. Bir yer işaretini ve COLUMN_MAP bir girişi işlemek için sınıfa bir giriş ekleyin:

```cpp
///////////////////////////////////////////////////////////////////////
// TestProvDlg.cpp

class CProvider
{
// Attributes
public:
   CBookmark<4>    bookmark;  // Add this line
   char   szCommand[16];
   char   szText[256];

   // Binding Maps
BEGIN_ACCESSOR_MAP(CProvider, 1)
   BEGIN_ACCESSOR(0, true)   // auto accessor
      BOOKMARK_ENTRY(bookmark)  // Add this line
      COLUMN_ENTRY(1, szField1)
      COLUMN_ENTRY(2, szField2)
   END_ACCESSOR()
END_ACCESSOR_MAP()
};
```

Kodu güncelleştirdikten sonra, sağlayıcıyı arabirimiyle oluşturup yürütebilmelisiniz `IRowsetLocate` .

## <a name="see-also"></a>Ayrıca bkz.

[Gelişmiş sağlayıcı teknikleri](../../data/oledb/advanced-provider-techniques.md)
