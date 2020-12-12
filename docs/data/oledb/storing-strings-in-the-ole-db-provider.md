---
description: 'Hakkında daha fazla bilgi edinin: OLE DB sağlayıcıda dizeleri depolama'
title: Dizeleri OLE DB Sağlayıcısında Depolama
ms.date: 05/09/2019
helpviewer_keywords:
- user records, editing
ms.assetid: 36cb9635-067c-4cad-8f85-962f28026f6a
ms.openlocfilehash: d5a0fc7160f09d1a8b385b83481cc6fa9009f582
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97316706"
---
# <a name="storing-strings-in-the-ole-db-provider"></a>Dizeleri OLE DB Sağlayıcısında Depolama

> [!NOTE]
> ATL OLE DB sağlayıcı Sihirbazı, Visual Studio 2019 ve sonrasında kullanılamaz.

*Özel* RS. h 'de, **ATL OLE DB sağlayıcı Sihirbazı** adlı bir varsayılan kullanıcı kaydı oluşturur `CWindowsFile` . İki dizeyi işlemek için `CWindowsFile` aşağıdaki kodda gösterildiği gibi değiştirin:

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

Veri üyeleri `szCommand` ve `szText` `szCommand2` gerekirse ek sütunlarla birlikte iki dizeyi temsil eder `szText2` . Veri üyesi `dwBookmark` Bu basit salt okunurdur sağlayıcı için gerekli değildir, ancak daha sonra arabirim eklemek için kullanılır `IRowsetLocate` ; bkz. [basit salt okuma sağlayıcısını geliştirme](../../data/oledb/enhancing-the-simple-read-only-provider.md). `==`İşleç örnekleri karşılaştırır (Bu işleci uygulamak isteğe bağlıdır).

Bu işlem tamamlandığında, [dizeleri okuma işlevlerini OLE DB sağlayıcısına](../../data/oledb/reading-strings-into-the-ole-db-provider.md)ekleyebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Basit Read-Only sağlayıcıyı uygulama](../../data/oledb/implementing-the-simple-read-only-provider.md)<br/>
