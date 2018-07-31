---
title: Döndürülen tüketiciye dinamik olarak sütunlar belirleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- bookmarks [C++], dynamically determining columns
- dynamically determining columns [C++]
ms.assetid: 58522b7a-894e-4b7d-a605-f80e900a7f5f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 28150a39042305ab96c4dba7746c0b79dbec9509
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39340462"
---
# <a name="dynamically-determining-columns-returned-to-the-consumer"></a>Tüketiciye Döndürülecek Olan Sütunları Dinamik Olarak Belirleme
PROVIDER_COLUMN_ENTRY normalde işlemek `IColumnsInfo::GetColumnsInfo` çağırın. Ancak, bir tüketici yer işaretlerini kullanmak isteyebilirsiniz, çünkü sağlayıcı tüketici için bir yer ister bağlı olarak döndürülecek olan sütunları değiştirmek mümkün olması gerekir.  
  
 İşlenecek `IColumnsInfo::GetColumnsInfo` çağrısı, bir işlevi tanımlayan PROVIDER_COLUMN_MAP silme `GetColumnInfo`, gelen `CAgentMan` kullanıcı kaydından içinde ve kendi tanımını değiştirin `GetColumnInfo` işlevi:  
  
```cpp
////////////////////////////////////////////////////////////////////////  
// MyProviderRS.H  
class CAgentMan  
{  
public:  
   DWORD dwBookmark;  
   TCHAR szCommand[256];  
   TCHAR szText[256];  
   TCHAR szCommand2[256];  
   TCHAR szText2[256];  
  
   static ATLCOLUMNINFO* GetColumnInfo(void* pThis, ULONG* pcCols);  
   bool operator==(const CAgentMan& am)  
   {  
      return (lstrcmpi(szCommand, am.szCommand) == 0);  
   }  
  
};  
```  
  
 Ardından, uygulama `GetColumnInfo` MyProviderRS.cpp aşağıdaki kodda gösterildiği gibi işlev.  
  
 `GetColumnInfo` ilk denetler OLE DB özelliği `DBPROP_BOOKMARKS` ayarlanır. Özellik get yapılmaya `GetColumnInfo` bir işaretçi kullanır (`pRowset`) için satır kümesi nesnesi. `pThis` İşaretçisini özellik eşlemesi depolandığı sınıfı olduğu satır kümesi, oluşturulan sınıfı temsil eder. `GetColumnInfo` yuvarlamasını `pThis` işaretçi bir `RMyProviderRowset` işaretçi.  
  
 Denetlenecek `DBPROP_BOOKMARKS` özelliği `GetColumnInfo` kullanan `IRowsetInfo` çağırarak elde edebileceğiniz arabirimi `QueryInterface` üzerinde `pRowset` arabirimi. Alternatif olarak, bir ATL kullanabileceğiniz [CComQIPtr](../../atl/reference/ccomqiptr-class.md) yöntemi yerine.  
  
```cpp
////////////////////////////////////////////////////////////////////  
// MyProviderRS.cpp  
ATLCOLUMNINFO* CAgentMan::GetColumnInfo(void* pThis, ULONG* pcCols)  
{  
   static ATLCOLUMNINFO _rgColumns[5];  
   ULONG ulCols = 0;  
  
   // Check the property flag for bookmarks; if it is set, set the zero   
   // ordinal entry in the column map with the bookmark information.  
   CAgentRowset* pRowset = (CAgentRowset*) pThis;  
   CComQIPtr<IRowsetInfo, &IID_IRowsetInfo> spRowsetProps = pRowset;  
  
   CDBPropIDSet set(DBPROPSET_ROWSET);  
   set.AddPropertyID(DBPROP_BOOKMARKS);  
   DBPROPSET* pPropSet = NULL;  
   ULONG ulPropSet = 0;  
   HRESULT hr;  
  
   if (spRowsetProps)  
      hr = spRowsetProps->GetProperties(1, &set, &ulPropSet, &pPropSet);  
  
   if (pPropSet)  
   {  
      CComVariant var = pPropSet->rgProperties[0].vValue;  
      CoTaskMemFree(pPropSet->rgProperties);  
      CoTaskMemFree(pPropSet);  
  
      if (SUCCEEDED(hr) && (var.boolVal == VARIANT_TRUE))  
      {  
         ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Bookmark"), 0, sizeof(DWORD),   
         DBTYPE_BYTES, 0, 0, GUID_NULL, CAgentMan, dwBookmark,   
         DBCOLUMNFLAGS_ISBOOKMARK)  
         ulCols++;  
      }  
   }  
  
   // Next, set the other columns up.  
   ADD_COLUMN_ENTRY(ulCols, OLESTR("Command"), 1, 256, DBTYPE_STR, 0xFF, 0xFF,   
      GUID_NULL, CAgentMan, szCommand)  
   ulCols++;  
   ADD_COLUMN_ENTRY(ulCols, OLESTR("Text"), 2, 256, DBTYPE_STR, 0xFF, 0xFF,   
      GUID_NULL, CAgentMan, szText)  
   ulCols++;  
  
   ADD_COLUMN_ENTRY(ulCols, OLESTR("Command2"), 3, 256, DBTYPE_STR, 0xFF, 0xFF,   
      GUID_NULL, CAgentMan, szCommand2)  
   ulCols++;  
   ADD_COLUMN_ENTRY(ulCols, OLESTR("Text2"), 4, 256, DBTYPE_STR, 0xFF, 0xFF,   
      GUID_NULL, CAgentMan, szText2)  
   ulCols++;  
  
   if (pcCols != NULL)  
      *pcCols = ulCols;  
  
   return _rgColumns;  
}  
```  
  
 Bu örnek, statik bir dizi sütun bilgileri içerecek şekilde kullanır. Tüketici yer işareti sütunu istemezse, dizi bir giriş kullanılmıyor. İki dizi makro oluşturma bilgilerini işlemek için: ADD_COLUMN_ENTRY ve ADD_COLUMN_ENTRY_EX. ADD_COLUMN_ENTRY_EX ek bir parametre alan `flags`, yani sizin belirlediğiniz bir yer işareti sütunu gerekli.  
  
```cpp
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
  
 İçinde `GetColumnInfo` işlevi, yer işareti makrosu şu şekilde kullanılır:  
  
```cpp  
ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Bookmark"), 0, sizeof(DWORD),  
   DBTYPE_BYTES, 0, 0, GUID_NULL, CAgentMan, dwBookmark,   
   DBCOLUMNFLAGS_ISBOOKMARK)  
```  
  
 Şimdi, derleyin ve Gelişmiş Sağlayıcısı'nı çalıştırın. Sağlayıcıyı test için test tüketici açıklandığı şekilde değiştirmeniz [basit tüketici uygulama](../../data/oledb/implementing-a-simple-consumer.md). Test tüketici, sağlayıcı ile çalıştırın. Test tüketici tıkladığınızda sağlayıcısından uygun dizelerden görüntüleyip getirdiğini doğrulayın **çalıştırma** düğmesine **Test tüketici** iletişim kutusu.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Basit Salt Okunur Sağlayıcıyı Geliştirme](../../data/oledb/enhancing-the-simple-read-only-provider.md)