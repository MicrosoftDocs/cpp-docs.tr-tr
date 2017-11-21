---
title: "Yer işaretleri sağlayıcı desteği | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- IRowsetLocate class, provider support for bookmarks
- OLE DB provider templates, bookmarks
- bookmarks, OLE DB
- IRowsetLocate class
- OLE DB providers, bookmark support
ms.assetid: 1b14ccff-4f76-462e-96ab-1aada815c377
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 445aa5a2a609c3cf2da83e9ff876195a05a33d6f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="provider-support-for-bookmarks"></a>Yer İşaretleri Sağlayıcı Desteği
Bu konudaki örnek ekler `IRowsetLocate` arabirimini `CMyProviderRowset` sınıfı. Neredeyse her durumda, var olan bir COM nesnesine bir arabirim ekleyerek başlatın. Ardından, tüketici şablonlarından çağrılar ekleyerek test edebilirsiniz. Örnek gösterir nasıl yapılır:  
  
-   Bir arabirim için bir sağlayıcı ekleyin.  
  
-   Tüketiciye döndürülecek olan sütunları dinamik olarak belirler.  
  
-   Yer işareti desteği ekleyin.  
  
 `IRowsetLocate` Arabirimi devraldığı `IRowset` arabirimi. Eklemek için `IRowsetLocate` arabirim, devralınan `CMyProviderRowset` gelen [IRowsetLocateImpl](../../data/oledb/irowsetlocateimpl-class.md).  
  
 Ekleme `IRowsetLocate` arabirimi, çoğu arabirimlerinden biraz farklıdır. Vtable çizgiyi oluşturan, OLE DB sağlayıcı şablonları türetilmiş bir arabirim işlemek için bir şablon parametresi gerekir. Aşağıdaki kod yeni devralma listesi gösterir:  
  
```  
////////////////////////////////////////////////////////////////////////  
// MyProviderRS.h  
  
// CMyProviderRowset  
class CMyProviderRowset : public CRowsetImpl< CMyProviderRowset,   
      CTextData, CMyProviderCommand, CAtlArray<CTextData>,   
      CSimpleRow,   
          IRowsetLocateImpl<CMyProviderRowset, IRowsetLocate> >  
```  
  
 Dördüncü, beşinci ve altıncı parametrelerin hepsi eklenmiştir. Bu örnek için dördüncü Varsayılanları kullanır ve beşinci parametreleri ancak `IRowsetLocateImpl` altıncı parametre olarak. `IRowsetLocateImpl`iki parametre şablonu alan bir OLE DB Şablon sınıfı: Bunlar takma `IRowsetLocate` arabirimini `CMyProviderRowset` sınıfı. Çoğu arabirimleri eklemek için bu adımı atlayın ve sonraki adıma geçebilirsiniz. Yalnızca `IRowsetLocate` ve `IRowsetScroll` arabirimleri bu şekilde ele alınması gerekir.  
  
 Ardından bildirmeniz gerekir `CMyProviderRowset` çağırmak için `QueryInterface` için `IRowsetLocate` arabirimi. Satırı ekleyin `COM_INTERFACE_ENTRY(IRowsetLocate)` eşleme. İçin arabirim eşlemesi `CMyProviderRowset` aşağıdaki kodda gösterildiği gibi görünmelidir:  
  
```  
////////////////////////////////////////////////////////////////////////  
// MyProviderRS.h  
  
typedef CRowsetImpl< CMyProviderRowset, CTextData, CMyProviderCommand, CAtlArray<CTextData>, CSimpleRow, IRowsetLocateImpl<CMyProviderRowset, IRowsetLocate> > _RowsetBaseClass;  
  
BEGIN_COM_MAP(CMyProviderRowset)  
   COM_INTERFACE_ENTRY(IRowsetLocate)  
   COM_INTERFACE_ENTRY_CHAIN(_RowsetBaseClass)  
END_COM_MAP()  
```  
  
 Ayrıca eşlemenizi kanca gerek `CRowsetImpl` sınıfı. İçin COM_INTERFACE_ENTRY_CHAIN makrosu eklemek `CRowsetImpl` eşleme. Ayrıca, adlı bir typedef oluşturun `RowsetBaseClass` devralma bilgilerinin oluşur. Bu typedef isteğe bağlıdır ve göz ardı edilebilir.  
  
 Son olarak, işleme **IColumnsInfo::GetColumnsInfo** çağırın. Bunu yapmak için PROVIDER_COLUMN_ENTRY normalde kullanırsınız. Ancak, bir tüketici yer işaretleri kullanmak isteyebilirsiniz. Tüketici için bir yer işareti ister bağlı olarak sağlayıcının döndürdüğü sütunları değiştirmek mümkün olması gerekir.  
  
 İşlenecek **IColumnsInfo::GetColumnsInfo** çağrısı, silme **PROVIDER_COLUMN** içinde eşleme `CTextData` sınıfı. Bir işlev PROVIDER_COLUMN_MAP makrosu tanımlar `GetColumnInfo`. Tanımlamak kendi ihtiyacınız `GetColumnInfo` işlevi. İşlev bildirimi aşağıdaki gibi görünmelidir:  
  
```  
////////////////////////////////////////////////////////////////////////  
// MyProviderRS.H  
  
class CTextData  
{  
   ...  
     // NOTE: Be sure you removed the PROVIDER_COLUMN_MAP!  
   static ATLCOLUMNINFO* GetColumnInfo(CMyProviderRowset* pThis,   
        ULONG* pcCols);  
   static ATLCOLUMNINFO* GetColumnInfo(CMyProviderCommand* pThis,   
        ULONG* pcCols);  
...  
};  
```  
  
 Ardından, uygulama `GetColumnInfo` MyProviderRS.cpp dosyasındaki gibi işlev:  
  
```  
////////////////////////////////////////////////////////////////////  
// MyProviderRS.cpp  
  
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
  
ATLCOLUMNINFO* CTextData::GetColumnInfo(CMyProviderCommand* pThis,   
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
  
 `GetColumnInfo`bir özellik olarak adlandırılan olup olmadığını görmek için ilk denetimleri **DBPROP_IRowsetLocate** ayarlanır. OLE DB satır kümesi nesnesi kapalı isteğe bağlı arabirimler her özelliğe sahiptir. Tüketici Bu isteğe bağlı arabirimler birini kullanmak istiyorsa, bir özellik true olarak ayarlanır. Sağlayıcı bu özelliğini denetleyin ve dayalı özel eylemi gerçekleştirin.  
  
 Uygulamanızda, komut nesnesi için işaretçi kullanarak özelliği alın. `pThis` İşaretçi satır kümesi veya komut sınıfını temsil eder. Burada şablon kullandığınızdan dolayı olarak geçirmek zorunda bir `void` işaretçi veya kod derlenmez.  
  
 Sütun bilgileri içerecek şekilde statik bir dizi belirtin. Tüketici yer işareti sütunu istemezse bir dizi girişi boşa harcanmış olur. Bu dizi dinamik olarak ayırabilir, ancak düzgün destroy emin olmak gerekir. Bu örnek tanımlar ve ADD_COLUMN_ENTRY ve ADD_COLUMN_ENTRY_EX makrolarını diziye bilgileri eklemek için kullanır. Aşağıdaki kodda gösterildiği gibi MyProviderRS.H dosyasına makrolar ekleyebilirsiniz:  
  
```  
////////////////////////////////////////////////////////////////////////  
// MyProviderRS.h  
  
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
  
 Tüketicideki kodu test etmek için bazı değişiklikler yapmanız gerekir `OnRun` işleyicisi. İlk işlevi için bir özellik için özellik kümesi eklemek için kodu ekleyin değişikliktir. Kod kümeleri **DBPROP_IRowsetLocate** özelliğinin true, böylece sağlayıcı yer işareti sütununu istediğinizi söyler. `OnRun` İşleyici kodu aşağıdaki gibi görünmelidir:  
  
```  
//////////////////////////////////////////////////////////////////////  
// TestProv Consumer Application in TestProvDlg.cpp  
  
void CTestProvDlg::OnRun()   
{  
   CCommand<CAccessor<CProvider> > table;  
   CDataSource source;  
   CSession   session;  
  
   if (source.Open("MyProvider.MyProvider.1", NULL, NULL, NULL,   
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
  
 While döngü içeren çağırmak için kodu `Compare` yönteminde `IRowsetLocate` arabirimi. Tam aynı yer işaretleri karşılaştırma çünkü kodunuz her zaman geçmelidir. Ayrıca, böylece süre sonra kullanabilirsiniz bir yer işareti geçici bir değişkende depolayın döngü çağrı tamamlanmadan `MoveToBookmark` Tüketici Şablonları işlevinde. `MoveToBookmark` İşlev çağrıları `GetRowsAt` yönteminde `IRowsetLocate`.  
  
 Ayrıca tüketicideki kullanıcı kayıt güncelleştirmeniz gerekir. Yer işareti ve bir girişe işlemek için sınıfa bir giriş eklemek **COLUMN_MAP**:  
  
```  
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
  
 Kod güncelleştirildiğinde, yapı ve sağlayıcı ile yürütme gerekir `IRowsetLocate` arabirimi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Gelişmiş Sağlayıcı teknikleri](../../data/oledb/advanced-provider-techniques.md)