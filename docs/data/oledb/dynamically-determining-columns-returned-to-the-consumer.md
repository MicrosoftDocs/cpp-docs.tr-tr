---
title: Tüketiciye Döndürülecek Olan Sütunları Dinamik Olarak Belirleme
ms.date: 10/26/2018
helpviewer_keywords:
- bookmarks [C++], dynamically determining columns
- dynamically determining columns [C++]
ms.assetid: 58522b7a-894e-4b7d-a605-f80e900a7f5f
ms.openlocfilehash: 81353581d22f3d075fd19d783591ec856c21e241
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59037665"
---
# <a name="dynamically-determining-columns-returned-to-the-consumer"></a>Tüketiciye Döndürülecek Olan Sütunları Dinamik Olarak Belirleme

PROVIDER_COLUMN_ENTRY normalde işlemek `IColumnsInfo::GetColumnsInfo` çağırın. Ancak, bir tüketici yer işaretlerini kullanmak isteyebilirsiniz, çünkü sağlayıcı tüketici için bir yer ister bağlı olarak döndürülecek olan sütunları değiştirmek mümkün olması gerekir.

İşlemek için `IColumnsInfo::GetColumnsInfo` çağrısı, bir işlevi tanımlayan PROVIDER_COLUMN_MAP silme `GetColumnInfo`, gelen `CCustomWindowsFile` kullanıcı kaydında *özel*RS.h kendi ilişkin tanımı değiştirin `GetColumnInfo` işlev:

```cpp
////////////////////////////////////////////////////////////////////////
// CustomRS.H
class CCustomWindowsFile
{
public:
   DWORD dwBookmark;
   static const int iSize = 256;
   TCHAR szCommand[iSize];
   TCHAR szText[iSize];
   TCHAR szCommand2[iSize];
   TCHAR szText2[iSize];
  
   static ATLCOLUMNINFO* GetColumnInfo(void* pThis, ULONG* pcCols);
   bool operator==(const CCustomWindowsFile& am)
   {
      return (lstrcmpi(szCommand, am.szCommand) == 0);
   }
};
```

Ardından, uygulama `GetColumnInfo` işlevi *özel*RS.cpp, aşağıdaki kodda gösterildiği gibi.

`GetColumnInfo` ilk denetler OLE DB özelliği `DBPROP_BOOKMARKS` ayarlanır. Özellik get yapılmaya `GetColumnInfo` bir işaretçi kullanır (`pRowset`) için satır kümesi nesnesi. `pThis` İşaretçisini özellik eşlemesi depolandığı sınıfı olduğu satır kümesi, oluşturulan sınıfı temsil eder. `GetColumnInfo` yuvarlamasını `pThis` işaretçi bir `RCustomRowset` işaretçi.

Denetlenecek `DBPROP_BOOKMARKS` özelliği `GetColumnInfo` kullanır `IRowsetInfo` çağırarak edinebilirsiniz arabirimi `QueryInterface` üzerinde `pRowset` arabirimi. Alternatif olarak, bir ATL kullanabileceğiniz [CComQIPtr](../../atl/reference/ccomqiptr-class.md) yöntemi yerine.

```cpp
////////////////////////////////////////////////////////////////////
// CustomRS.cpp
ATLCOLUMNINFO* CCustomWindowsFile::GetColumnInfo(void* pThis, ULONG* pcCols)
{
   static ATLCOLUMNINFO _rgColumns[5];
   ULONG ulCols = 0;
  
   // Check the property flag for bookmarks; if it is set, set the zero 
   // ordinal entry in the column map with the bookmark information.
   CCustomRowset* pRowset = (CCustomRowset*) pThis;
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
         DBTYPE_BYTES, 0, 0, GUID_NULL, CCustomWindowsFile, dwBookmark, 
         DBCOLUMNFLAGS_ISBOOKMARK)
         ulCols++;
      }
   }
  
   // Next, set the other columns up.
   ADD_COLUMN_ENTRY(ulCols, OLESTR("Command"), 1, 256, DBTYPE_STR, 0xFF, 0xFF, 
      GUID_NULL, CCustomWindowsFile, szCommand)
   ulCols++;
   ADD_COLUMN_ENTRY(ulCols, OLESTR("Text"), 2, 256, DBTYPE_STR, 0xFF, 0xFF, 
      GUID_NULL, CCustomWindowsFile, szText)
   ulCols++;
  
   ADD_COLUMN_ENTRY(ulCols, OLESTR("Command2"), 3, 256, DBTYPE_STR, 0xFF, 0xFF, 
      GUID_NULL, CCustomWindowsFile, szCommand2)
   ulCols++;
   ADD_COLUMN_ENTRY(ulCols, OLESTR("Text2"), 4, 256, DBTYPE_STR, 0xFF, 0xFF, 
      GUID_NULL, CCustomWindowsFile, szText2)
   ulCols++;
  
   if (pcCols != NULL)
      *pcCols = ulCols;
  
   return _rgColumns;
}
```

Bu örnek, statik bir dizi sütun bilgileri tutmak için kullanır. Yer işareti sütunu tüketici istememektedir, dizi bir giriş kullanılmıyor. Bilgilerini işlemek için iki dizi makro oluşturun: ADD_COLUMN_ENTRY ve ADD_COLUMN_ENTRY_EX. ADD_COLUMN_ENTRY_EX ek bir parametre alan *bayrakları*, yani sizin belirlediğiniz bir yer işareti sütunu gerekli.

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

İçinde `GetColumnInfo` işlevi, yer işareti makrosu şu şekilde kullanılır:

```cpp
ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Bookmark"), 0, sizeof(DWORD),
   DBTYPE_BYTES, 0, 0, GUID_NULL, CAgentMan, dwBookmark,
   DBCOLUMNFLAGS_ISBOOKMARK)
```

Şimdi, derleyin ve Gelişmiş Sağlayıcısı'nı çalıştırın. Sağlayıcıyı test için test tüketici açıklandığı şekilde değiştirmeniz [basit tüketici uygulama](../../data/oledb/implementing-a-simple-consumer.md). Test müşteri ve sağlayıcı ile çalıştırmak ve test tüketici sağlayıcıdan doğru dizeleri alır doğrulayın.

## <a name="see-also"></a>Ayrıca bkz.

[Basit Salt Okunur Sağlayıcıyı Geliştirme](../../data/oledb/enhancing-the-simple-read-only-provider.md)<br/>
