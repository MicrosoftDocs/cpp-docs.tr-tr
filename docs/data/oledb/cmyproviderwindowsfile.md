---
title: CCustomWindowsFile | Microsoft Docs
ms.custom: ''
ms.date: 10/22/2018
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- cmyproviderwindowsfile
- ccustomwindowsfile
dev_langs:
- C++
helpviewer_keywords:
- CMyProviderWindowsFile class
- OLE DB providers, wizard-generated files
- CCustomWindowsFile class
ms.assetid: 0e9e72ac-1e1e-445f-a7ac-690c20031f9d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 947efa181a6b632050c01c4f2b327cf11a113e3f
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50070939"
---
# <a name="ccustomwindowsfile"></a>CCustomWindowsFile

Sihirbaz, bir veri satırı içerecek şekilde bir sınıf oluşturur; Bu durumda, adlı `CCustomWindowsFile`. Aşağıdaki kod için `CCustomWindowsFile` Sihirbazı tarafından oluşturulan ve bir dizindeki tüm dosyaları kullanarak listeleri `WIN32_FIND_DATA` yapısı. `CCustomWindowsFile` devralınan `WIN32_FIND_DATA` yapısı:

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

`CCustomWindowsFile` çağrılır [kullanıcı kayıt sınıfı](../../data/oledb/user-record.md) Ayrıca sağlayıcının satır sütunları açıklayan bir harita içerdiğinden. Sağlayıcı sütun eşlemesini PROVIDER_COLUMN_ENTRY kullanarak satır kümesindeki her bir alan için bir girdi içeriyor. Makroları, sıra ve yapısı girdi için uzaklık sütun adı belirtin. Yukarıdaki kodda sağlayıcısı sütun girişleri içine uzaklıkları içeren `WIN32_FIND_DATA` yapısı. Tüketici çağırdığında `IRowset::GetData`, verileri bitişik bir arabellek aktarılır. İşaretçi aritmetiği Bunu yapmak yerine, eşleme, bir veri üyesi belirtmenizi sağlar.

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

Arama dizini tarafından temsil edilen `m_strCommandText`; bu tarafından gösterilen metni içeren `ICommandText` arabiriminde komut nesnesi. Hiçbir dizin belirtilirse, geçerli dizin kullanır.

Yöntem (karşılık gelen bir satıra) her dosya için bir girdi oluşturur ve yerleştirir `m_rgRowData` veri üyesi. `CRowsetImpl` Sınıfı tanımlar `m_rgRowData` veri üyesi. Bu dizi verilerinde tablonun tamamını temsil eder ve tüm şablonlarda kullanılır.

## <a name="see-also"></a>Ayrıca Bkz.

[Sağlayıcı Sihirbazı Tarafından Üretilen Dosyalar](../../data/oledb/provider-wizard-generated-files.md)