---
title: Döndürülen tüketiciye dinamik olarak sütunlar belirleme | Microsoft Docs
ms.custom: ''
ms.date: 10/26/2018
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
ms.openlocfilehash: a2149c50f4dc8880e20bff2401adf0db46ad6588
ms.sourcegitcommit: 840033ddcfab51543072604ccd5656fc6d4a5d3a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2018
ms.locfileid: "50216506"
---
# <a name="dynamically-determining-columns-returned-to-the-consumer"></a>Tüketiciye Döndürülecek Olan Sütunları Dinamik Olarak Belirleme

PROVIDER_COLUMN_ENTRY normalde işlemek `IColumnsInfo::GetColumnsInfo` çağırın. Ancak, bir tüketici yer işaretlerini kullanmak isteyebilirsiniz, çünkü sağlayıcı tüketici için bir yer ister bağlı olarak döndürülecek olan sütunları değiştirmek mümkün olması gerekir.

İşlenecek `IColumnsInfo::GetColumnsInfo` çağrısı, bir işlevi tanımlayan PROVIDER_COLUMN_MAP silme `GetColumnInfo`, gelen `CAgentMan` kullanıcı kayıt içinde CustomRS.h ve kendi tanımını değiştirin `GetColumnInfo` işlevi:

```cpp
////////////////////////////////////////////////////////////////////////
// CustomRS.H
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

Ardından, uygulama `GetColumnInfo` işlevi *özel*RS.cpp, aşağıdaki kodda gösterildiği gibi.

`GetColumnInfo` ilk denetler OLE DB özelliği `DBPROP_BOOKMARKS` ayarlanır. Özellik get yapılmaya `GetColumnInfo` bir işaretçi kullanır (`pRowset`) için satır kümesi nesnesi. `pThis` İşaretçisini özellik eşlemesi depolandığı sınıfı olduğu satır kümesi, oluşturulan sınıfı temsil eder. `GetColumnInfo` yuvarlamasını `pThis` işaretçi bir `RCustomRowset` işaretçi.

Denetlenecek `DBPROP_BOOKMARKS` özelliği `GetColumnInfo` kullanır `IRowsetInfo` çağırarak edinebilirsiniz arabirimi `QueryInterface` üzerinde `pRowset` arabirimi. Alternatif olarak, bir ATL kullanabileceğiniz [CComQIPtr](../../atl/reference/ccomqiptr-class.md) yöntemi yerine.

```cpp
////////////////////////////////////////////////////////////////////
// CustomRS.cpp
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

Bu örnek, statik bir dizi sütun bilgileri tutmak için kullanır. Yer işareti sütunu tüketici istememektedir, dizi bir giriş kullanılmıyor. İki dizi makro oluşturma bilgilerini işlemek için: ADD_COLUMN_ENTRY ve ADD_COLUMN_ENTRY_EX. ADD_COLUMN_ENTRY_EX ek bir parametre alan *bayrakları*, yani sizin belirlediğiniz bir yer işareti sütunu gerekli.

```cpp
ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Bookmark"), 0, sizeof(DWORD),
   DBTYPE_BYTES, 0, 0, GUID_NULL, CAgentMan, dwBookmark,
   DBCOLUMNFLAGS_ISBOOKMARK)
```

Şimdi, derleyin ve Gelişmiş Sağlayıcısı'nı çalıştırın. Sağlayıcıyı test için test tüketici açıklandığı şekilde değiştirmeniz [basit tüketici uygulama](../../data/oledb/implementing-a-simple-consumer.md). Test tüketici, sağlayıcı ile çalıştırın. Test tüketici tıkladığınızda sağlayıcısından uygun dizelerden görüntüleyip getirdiğini doğrulayın **çalıştırma** düğmesine **Test tüketici** iletişim kutusu.

## <a name="see-also"></a>Ayrıca Bkz.

[Basit Salt Okunur Sağlayıcıyı Geliştirme](../../data/oledb/enhancing-the-simple-read-only-provider.md)<br/>
