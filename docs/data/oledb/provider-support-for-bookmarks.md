---
title: Yer işaretleri sağlayıcı desteği | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IRowsetLocate class, provider support for bookmarks
- OLE DB provider templates, bookmarks
- bookmarks, OLE DB
- IRowsetLocate class
- OLE DB providers, bookmark support
ms.assetid: 1b14ccff-4f76-462e-96ab-1aada815c377
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ce718e84d50552e01c84e9d0df01c9f169bdf322
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50077016"
---
# <a name="provider-support-for-bookmarks"></a>Yer İşaretleri Sağlayıcı Desteği

Bu konudaki örnek ekler `IRowsetLocate` arabirimini `CCustomRowset` sınıfı. Hemen hemen tüm durumlarda, var olan bir COM nesnesine bir arabirim ekleyerek başlayın. Ardından, tüketici şablonlardan daha fazla çağrıları ekleyerek sınayabilirsiniz. Örnek gösterir nasıl yapılır:

- Bir arabirim için sağlayıcı ekleyin.

- Tüketiciye döndürülecek olan sütunları dinamik olarak belirler.

- Yer işareti desteği eklendi.

`IRowsetLocate` Arabirimi devralır `IRowset` arabirimi. Eklenecek `IRowsetLocate` arabirim, devralma `CCustomRowset` gelen [IRowsetLocateImpl](../../data/oledb/irowsetlocateimpl-class.md).

Ekleme `IRowsetLocate` arabirimidir çoğu arabirimlerden biraz farklıdır. Vtable çizgiyi oluşturan, OLE DB sağlayıcı şablonları türetilmiş bir arabirim işlemek için bir şablon parametresi gerekir. Aşağıdaki kod, yeni devralma listeyi gösterir:

```cpp
////////////////////////////////////////////////////////////////////////
// CustomRS.h

// CCustomRowset
class CCustomRowset : public CRowsetImpl< CCustomRowset,
      CTextData, CCustomCommand, CAtlArray<CTextData>,
      CSimpleRow,
          IRowsetLocateImpl<CCustomRowset, IRowsetLocate>>
```

Dördüncü, beşinci ve altıncı parametreleri tüm eklendi. Bu örnek, dördüncü için varsayılan değerleri kullanır ve beşinci parametreleri ancak `IRowsetLocateImpl` altıncı parametre olarak. `IRowsetLocateImpl` iki şablon parametre bir OLE DB Şablon sınıfıdır: Bu takma `IRowsetLocate` arabirimini `CCustomRowset` sınıfı. Çoğu arabirimleri eklemek, bu adımı atlayın ve sonraki adıma geçebilirsiniz. Yalnızca `IRowsetLocate` ve `IRowsetScroll` bu şekilde ele alınması gereken arabirimler.

Ardından söylemeniz gerekir `CCustomRowset` çağrılacak `QueryInterface` için `IRowsetLocate` arabirimi. Satır Ekle `COM_INTERFACE_ENTRY(IRowsetLocate)` eşleme. Arabirim eşlemesini `CCustomRowset` aşağıdaki kodda gösterildiği gibi görünmelidir:

```cpp
////////////////////////////////////////////////////////////////////////
// CustomRS.h

typedef CRowsetImpl< CCustomRowset, CTextData, CCustomCommand, CAtlArray<CTextData>, CSimpleRow, IRowsetLocateImpl<CCustomRowset, IRowsetLocate>> _RowsetBaseClass;

BEGIN_COM_MAP(CCustomRowset)
   COM_INTERFACE_ENTRY(IRowsetLocate)
   COM_INTERFACE_ENTRY_CHAIN(_RowsetBaseClass)
END_COM_MAP()
```

Ayrıca eşlemenizi bağlamanız gerekir `CRowsetImpl` sınıfı. İçin COM_INTERFACE_ENTRY_CHAIN makro Ekle `CRowsetImpl` eşleme. Ayrıca, adlı bir tür tanımı oluşturma `RowsetBaseClass` devralma bilgilerinin oluşur. Bu typedef isteğe bağlıdır ve yok sayılabilir.

Son olarak, işleme `IColumnsInfo::GetColumnsInfo` çağırın. Bunu yapmak için normalde PROVIDER_COLUMN_ENTRY kullanmanız gerekir. Ancak, bir tüketici yer işaretlerini kullanmak isteyebilirsiniz. Sağlayıcı için bir yer ister bağlı olarak tüketici döndürür sütunları değiştirmek mümkün olması gerekir.

İşlemek için `IColumnsInfo::GetColumnsInfo` çağrı, silme `PROVIDER_COLUMN` içinde harita `CTextData` sınıfı. Bir işlev PROVIDER_COLUMN_MAP makro tanımlar `GetColumnInfo`. Tanımlamak kendi ihtiyacınız `GetColumnInfo` işlevi. İşlev bildiriminin şöyle görünmelidir:

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

Ardından, uygulama `GetColumnInfo` CustomRS.cpp dosyasında aşağıdaki gibi işlev:

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

`GetColumnInfo` bir özellik adında olup olmadığını görmek için ilk denetimleri `DBPROP_IRowsetLocate` ayarlanır. OLE DB, her bir satır kümesi nesnesi kapalı isteğe bağlı arabirimler için özellikleri vardır. Tüketici Bu isteğe bağlı arabirimlerinden birini kullanmak istiyorsa, bir özellik true olarak ayarlanır. Sağlayıcı bu özelliği kontrol edin ve temel alan özel eylem.

Uygulamanızda, komut nesnesi için bir işaretçi kullanarak özellik alın. `pThis` İşaretçi satır kümesi ya da komut sınıfı temsil eder. Şablonları burada kullandığından, bu konuda geçirmek zorunda bir `void` işaretçi veya kod derlenmez.

Statik bir dizi sütun bilgileri içerecek şekilde belirtin. Tüketici yer işareti sütunu istemezse, dizi bir giriş boşa harcanmış olur. Bu dizi dinamik olarak tahsis edebilirsiniz, ancak düzgün edilecek emin olmanız gerekir. Bu örnek, tanımlar ve bilgileri diziye eklenecek ADD_COLUMN_ENTRY ve ADD_COLUMN_ENTRY_EX makrolarını kullanır. Aşağıdaki kodda gösterildiği gibi CustomRS.H dosyasına makrolar ekleyebilirsiniz:

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

Tüketici, kodu test etmek için birkaç değişiklik yapmak ihtiyacınız `OnRun` işleyici. İlk işlev için bir özellik için özellik kümesi eklemek için kod ekleme değişikliktir. Kod kümeleri `DBPROP_IRowsetLocate` true, bu nedenle, yer işareti sütunu istediğiniz sağlayıcı belirten özellik. `OnRun` İşleyicinizin kodunu şu şekilde görünmelidir:

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

**Sırada** döngü çağırmak için kod içeren `Compare` yönteminde `IRowsetLocate` arabirimi. Tam aynı yer işaretleri arasında karşılaştırma yaptığımızı düşündüğümüzde, kodunuz geçirmesi gerekir. Ayrıca, böylece sonra kullanabileceğiniz bir yer işareti geçici bir değişkende depolayın **sırada** döngü çağırabilmek için `MoveToBookmark` Tüketici Şablonları işlevi. `MoveToBookmark` İşlev çağrılarında `GetRowsAt` yönteminde `IRowsetLocate`.

Ayrıca, tüketicideki kullanıcı kayıt güncelleştirmeniz gerekiyor. Sınıfında bir yer işareti ve bir girdi işlemek için bir giriş ekleyin `COLUMN_MAP`:

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

Kodu güncelleştirdikten sonra sağlayıcı ile oluşturup erişebileceğinizi `IRowsetLocate` arabirimi.

## <a name="see-also"></a>Ayrıca Bkz.

[Gelişmiş Sağlayıcı Teknikleri](../../data/oledb/advanced-provider-techniques.md)