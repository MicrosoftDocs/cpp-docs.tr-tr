---
title: CCustomWindowsFile
ms.date: 10/22/2018
f1_keywords:
- cmyproviderwindowsfile
- ccustomwindowsfile
helpviewer_keywords:
- CMyProviderWindowsFile class
- OLE DB providers, wizard-generated files
- CCustomWindowsFile class
ms.assetid: 0e9e72ac-1e1e-445f-a7ac-690c20031f9d
ms.openlocfilehash: 4af302d8a391de359f3b8ac66d41b5d7198fd8f6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62182918"
---
# <a name="ccustomwindowsfile"></a>CCustomWindowsFile

Sihirbaz, bir veri satırı olan bir sınıf oluşturur; Bu durumda, adlı `CCustomWindowsFile`. Aşağıdaki kod için `CCustomWindowsFile` Sihirbazı tarafından oluşturulan ve bir dizindeki tüm dosyaları kullanarak listeleri `WIN32_FIND_DATA` yapısı. `CCustomWindowsFile` devralınan `WIN32_FIND_DATA` yapısı:

```cpp
/////////////////////////////////////////////////////////////////////
// CustomRS.H

class CCustomWindowsFile: 
   public WIN32_FIND_DATA
{
public:
BEGIN_PROVIDER_COLUMN_MAP(CCustomWindowsFile)
   PROVIDER_COLUMN_ENTRY("FileAttributes", 1, dwFileAttributes)
   PROVIDER_COLUMN_ENTRY("FileSizeHigh", 2, nFileSizeHigh)
   PROVIDER_COLUMN_ENTRY("FileSizeLow", 3, nFileSizeLow)
   PROVIDER_COLUMN_ENTRY_STR("FileName", 4, cFileName)
   PROVIDER_COLUMN_ENTRY_STR("AltFileName", 5, cAlternateFileName)
END_PROVIDER_COLUMN_MAP()
};
```

`CCustomWindowsFile` çağrılır [kullanıcı kayıt sınıfı](../../data/oledb/user-record.md) Ayrıca sağlayıcının satır sütunları açıklayan bir eşlemesi olduğundan. Sağlayıcı sütun eşlemesini PROVIDER_COLUMN_ENTRY kullanarak satır kümesindeki her bir alan için bir girdi içeriyor. Makroları, sıra ve yapısı girdi için uzaklık sütun adı belirtin. Yukarıdaki kodda sağlayıcısı sütun girişleri içine uzaklıkları içeren `WIN32_FIND_DATA` yapısı. Tüketici çağırdığında `IRowset::GetData`, verileri bitişik bir arabellek aktarılır. İşaretçi aritmetiği Bunu yapmak yerine, eşleme, bir veri üyesi belirtmenizi sağlar.

`CCustomRowset` Sınıfı da içeren `Execute` yöntemi. `Execute` hangi verileri yerel kaynaktan okuyan yöntemdir. Aşağıdaki kod Sihirbazı tarafından oluşturulan gösterir `Execute` yöntemi. Win32 işlevini kullanan `FindFirstFile` ve `FindNextFile` dizindeki dosyaları hakkında bilgi almak ve bunları örneklerine yerleştirmek için API'ler `CCustomWindowsFile` sınıfı.

```cpp
/////////////////////////////////////////////////////////////////////
// CustomRS.H

HRESULT Execute(DBPARAMS * pParams, LONG* pcRowsAffected)
{
   USES_CONVERSION;
   BOOL bFound = FALSE;
   HANDLE hFile;
   LPTSTR  szDir = (m_strCommandText == _T("")) ? _T("*.*") :
       OLE2T(m_strCommandText);
   CCustomWindowsFile wf;
   hFile = FindFirstFile(szDir, &wf);
   if (hFile == INVALID_HANDLE_VALUE)
      return DB_E_ERRORSINCOMMAND;
   LONG cFiles = 1;
   BOOL bMoreFiles = TRUE;
   while (bMoreFiles)
   {
      if (!m_rgRowData.Add(wf))
         return E_OUTOFMEMORY;
      bMoreFiles = FindNextFile(hFile, &wf);
      cFiles++;
   }
   FindClose(hFile);
   if (pcRowsAffected != NULL)
      *pcRowsAffected = cFiles;
   return S_OK;
}
```

Arama dizini tarafından gösterilen `m_strCommandText`; bu tarafından gösterilen metni içeren `ICommandText` arabiriminde komut nesnesi. Hiçbir dizin belirtilirse, geçerli dizin kullanır.

Yöntem (karşılık gelen bir satıra) her dosya için bir girdi oluşturur ve yerleştirir `m_rgRowData` veri üyesi. `CRowsetImpl` Sınıfı tanımlar `m_rgRowData` veri üyesi. Bu dizi verilerinde tablonun tamamını gösterilir ve tüm şablonlarda kullanılır.

## <a name="see-also"></a>Ayrıca bkz.

[Sağlayıcı Sihirbazı Tarafından Üretilen Dosyalar](../../data/oledb/provider-wizard-generated-files.md)<br/>
