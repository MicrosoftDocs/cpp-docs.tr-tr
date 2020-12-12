---
description: 'Daha fazla bilgi edinin: tüketiciye döndürülen sütunları dinamik olarak belirleme'
title: Tüketiciye Döndürülecek Olan Sütunları Dinamik Olarak Belirleme
ms.date: 10/26/2018
helpviewer_keywords:
- bookmarks [C++], dynamically determining columns
- dynamically determining columns [C++]
ms.assetid: 58522b7a-894e-4b7d-a605-f80e900a7f5f
ms.openlocfilehash: fd70164edff5b9267e01a891a143920ac4e60a35
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97287573"
---
# <a name="dynamically-determining-columns-returned-to-the-consumer"></a>Tüketiciye Döndürülecek Olan Sütunları Dinamik Olarak Belirleme

PROVIDER_COLUMN_ENTRY makrolar normalde `IColumnsInfo::GetColumnsInfo` çağrıyı işler. Ancak, bir tüketici yer işaretlerini kullanmayı seçebildiğinden, sağlayıcının, tüketicinin bir yer işareti isteyip istemediği ile ilgili olarak döndürülen sütunları değiştirebilmeleri gerekir.

Çağrıyı işlemek için, `IColumnsInfo::GetColumnsInfo` `GetColumnInfo` `CCustomWindowsFile` *özel* RS. h içindeki kullanıcı kaydından bir işlevi tanımlayan PROVIDER_COLUMN_MAP silin ve kendi `GetColumnInfo` işlevinizin tanımıyla değiştirin:

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

Sonra, `GetColumnInfo` aşağıdaki kodda gösterildiği gibi, Işlevini *özel* RS. cpp ' de uygulayın.

`GetColumnInfo` OLE DB özelliğinin ayarlanmış olup olmadığını görmek için önce kontrol eder `DBPROP_BOOKMARKS` . Özelliği almak için, `GetColumnInfo` Rowset nesnesine bir işaretçi ( `pRowset` ) kullanır. `pThis`İşaretçi, özellik eşlemesinin depolandığı sınıf olan satır kümesini oluşturan sınıfını temsil eder. `GetColumnInfo` işaretçi işaretçiyi `pThis` bir `RCustomRowset` işaretçiye yayınlar.

Özelliğini denetlemek için, `DBPROP_BOOKMARKS` `GetColumnInfo` `IRowsetInfo` arabirimini kullanarak alabileceğiniz arabirimini kullanır `QueryInterface` `pRowset` . Alternatif olarak, bunun yerine bir ATL [CComQIPtr](../../atl/reference/ccomqiptr-class.md) yöntemi kullanabilirsiniz.

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

Bu örnek, sütun bilgilerini tutmak için bir statik dizi kullanır. Tüketici, yer işareti sütununu istemiyor, dizideki bir giriş kullanılmaz. Bilgileri işlemek için iki dizi makrosu oluşturursunuz: ADD_COLUMN_ENTRY ve ADD_COLUMN_ENTRY_EX. ADD_COLUMN_ENTRY_EX, bir yer işareti sütunu belirlemeniz gereken ek bir parametre, *bayrak* alır.

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

`GetColumnInfo`İşlevinde, yer işareti makrosu şöyle kullanılır:

```cpp
ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Bookmark"), 0, sizeof(DWORD),
   DBTYPE_BYTES, 0, 0, GUID_NULL, CAgentMan, dwBookmark,
   DBCOLUMNFLAGS_ISBOOKMARK)
```

Artık gelişmiş sağlayıcıyı derleyebilir ve çalıştırabilirsiniz. Sağlayıcıyı test etmek için, [basit bir tüketici uygulama](../../data/oledb/implementing-a-simple-consumer.md)bölümünde açıklandığı gibi test tüketicisini değiştirin. Test tüketicisini sağlayıcıyla çalıştırın ve test tüketicisinin sağlayıcıdan uygun dizeleri aldığını doğrulayın.

## <a name="see-also"></a>Ayrıca bkz.

[Basit Read-Only sağlayıcıyı geliştirme](../../data/oledb/enhancing-the-simple-read-only-provider.md)<br/>
