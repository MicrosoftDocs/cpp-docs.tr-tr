---
title: Dizeleri OLE DB Sağlayıcısında Depolama
ms.date: 10/26/2018
helpviewer_keywords:
- user records, editing
ms.assetid: 36cb9635-067c-4cad-8f85-962f28026f6a
ms.openlocfilehash: 54dfdb347c621cf6f8645feb6d13742f32503f9f
ms.sourcegitcommit: 943c792fdabf01c98c31465f23949a829eab9aad
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/07/2018
ms.locfileid: "51264625"
---
# <a name="storing-strings-in-the-ole-db-provider"></a>Dizeleri OLE DB Sağlayıcısında Depolama

İçinde *özel*RS.h, **ATL OLE DB sağlayıcısı Sihirbazı** adlı bir varsayılan kullanıcı kayıt oluşturur `CWindowsFile`. İki dizenin işlemek için değiştirme `CWindowsFile` aşağıdaki kodda gösterildiği gibi:

```cpp
////////////////////////////////////////////////////////////////////////
class CCustomWindowsFile:
   public WIN32_FIND_DATA
{
public:
DWORD dwBookmark;
static const int iSize = 256;    // Add this
TCHAR szCommand[iSize];          // Add this
TCHAR szText[iSize];             // Add this
TCHAR szCommand2[iSize];         // Add this
TCHAR szText2[iSize];            // Add this

BEGIN_PROVIDER_COLUMN_MAP(CCustomWindowsFile)
   PROVIDER_COLUMN_ENTRY("FileAttributes", 1, dwFileAttributes)
   PROVIDER_COLUMN_ENTRY("FileSizeHigh", 2, nFileSizeHigh)
   PROVIDER_COLUMN_ENTRY("FileSizeLow", 3, nFileSizeLow)
   PROVIDER_COLUMN_ENTRY_STR("FileName", 4, cFileName)
   PROVIDER_COLUMN_ENTRY_STR("AltFileName", 5, cAlternateFileName)

   PROVIDER_COLUMN_ENTRY_STR("Command", 6, szCommand)    // Add this
   PROVIDER_COLUMN_ENTRY_STR("Text", 7, szText)          // Add this
   PROVIDER_COLUMN_ENTRY_STR("Command2", 8, szCommand2)  // Add this
   PROVIDER_COLUMN_ENTRY_STR("Text2", 9, szText2)        // Add this
END_PROVIDER_COLUMN_MAP()

   bool operator==(const CCustomWindowsFile& am) // This is optional
   {
      return (lstrcmpi(cFileName, am.cFileName) == 0);
   }
};
```

Veri üyeleri `szCommand` ve `szText` ile iki dizeyi temsil eden `szCommand2` ve `szText2` gerekirse ek sütunlar içeren. Veri üyesi `dwBookmark` bu basit bir salt okunur sağlayıcı için gerekli değildir ancak daha sonra eklemek için kullanılan bir `IRowsetLocate` arabirim; bkz [basit salt okunur sağlayıcıyı geliştirme](../../data/oledb/enhancing-the-simple-read-only-provider.md). `==` İşleci örnekleri karşılaştırır (Bu imlecini uygulamadan isteğe bağlı).

Bu yapıldığında, işlevselliğini ekleyebilirsiniz [dizeleri OLE DB sağlayıcısına okuma](../../data/oledb/reading-strings-into-the-ole-db-provider.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Basit Salt Okunur Sağlayıcıyı Uygulama](../../data/oledb/implementing-the-simple-read-only-provider.md)<br/>
