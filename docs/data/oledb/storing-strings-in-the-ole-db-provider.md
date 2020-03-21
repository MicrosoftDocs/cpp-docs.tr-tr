---
title: Dizeleri OLE DB Sağlayıcısında Depolama
ms.date: 05/09/2019
helpviewer_keywords:
- user records, editing
ms.assetid: 36cb9635-067c-4cad-8f85-962f28026f6a
ms.openlocfilehash: 1d6d2b73495d5ca6e275b13ed3c430f8169179d4
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80079106"
---
# <a name="storing-strings-in-the-ole-db-provider"></a>Dizeleri OLE DB Sağlayıcısında Depolama

> [!NOTE]
> ATL OLE DB sağlayıcı Sihirbazı, Visual Studio 2019 ve sonrasında kullanılamaz.

*Özel*RS. h 'de, **ATL OLE DB sağlayıcı Sihirbazı** `CWindowsFile`adlı varsayılan bir kullanıcı kaydı oluşturur. İki dizeyi işlemek için `CWindowsFile` aşağıdaki kodda gösterildiği gibi değiştirin:

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

`szCommand` ve `szText` veri üyeleri, `szCommand2` ve gerekirse ek sütunlarla `szText2` iki dizeyi temsil eder. Veri üyesi `dwBookmark`, bu basit salt okunurdur sağlayıcı için gerekli değildir, ancak daha sonra `IRowsetLocate` arabirimi eklemek için kullanılır; bkz. [basit salt okuma sağlayıcısını geliştirme](../../data/oledb/enhancing-the-simple-read-only-provider.md). `==` işleci örnekleri karşılaştırır (Bu işleci uygulamak isteğe bağlıdır).

Bu işlem tamamlandığında, [dizeleri okuma işlevlerini OLE DB sağlayıcısına](../../data/oledb/reading-strings-into-the-ole-db-provider.md)ekleyebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Basit Salt Okunur Sağlayıcıyı Uygulama](../../data/oledb/implementing-the-simple-read-only-provider.md)<br/>
