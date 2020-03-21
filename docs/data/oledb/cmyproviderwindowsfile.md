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
ms.openlocfilehash: 103a1ce5568c6137994056e574ce8eec04511d8f
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80079738"
---
# <a name="ccustomwindowsfile"></a>CCustomWindowsFile

Sihirbaz bir veri satırı içeren bir sınıf oluşturur; Bu durumda, `CCustomWindowsFile`çağırılır. `CCustomWindowsFile` için aşağıdaki kod sihirbaz oluşturulur ve `WIN32_FIND_DATA` yapısını kullanarak bir dizindeki tüm dosyaları listeler. `CCustomWindowsFile` `WIN32_FIND_DATA` yapısından devralır:

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

`CCustomWindowsFile`, [Kullanıcı kayıt sınıfı](../../data/oledb/user-record.md) olarak adlandırılır çünkü sağlayıcının satır kümesindeki sütunları açıklayan bir eşlem de vardır. Sağlayıcı sütun eşlemesi, PROVIDER_COLUMN_ENTRY makroları kullanarak satır kümesindeki her alan için bir giriş içerir. Makrolar sütun adını, sıra sayısını ve bir yapı girişinin konumunu belirtir. Yukarıdaki koddaki sağlayıcı sütun girdileri `WIN32_FIND_DATA` yapısına uzaklıklar içerir. Tüketici `IRowset::GetData`çağırdığında, veriler bir bitişik arabellekte aktarılır. Bir işaretçi aritmetik yapmak yerine, eşleme bir veri üyesi belirtmenize olanak tanır.

`CCustomRowset` sınıfı `Execute` metodunu da içerir. `Execute`, yerel kaynaktaki içindeki verileri gerçekte okur. Aşağıdaki kodda, sihirbaz tarafından oluşturulan `Execute` yöntemi gösterilmektedir. İşlevi, dizindeki dosyalar hakkında bilgi almak ve bunları `CCustomWindowsFile` sınıfının örneklerine yerleştirmek için Win32 `FindFirstFile` ve `FindNextFile` API 'Lerini kullanır.

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

Arama yapılacak Dizin `m_strCommandText`gösterilir; Bu, komut nesnesindeki `ICommandText` arabirimi tarafından temsil edilen metni içerir. Dizin belirtilmemişse, geçerli dizini kullanır.

Yöntemi her dosya için bir giriş oluşturur (bir satıra karşılık gelir) ve `m_rgRowData` veri üyesine koyar. `CRowsetImpl` sınıfı `m_rgRowData` veri üyesini tanımlar. Bu dizideki veriler tablonun tamamında gösterilir ve şablonlar boyunca kullanılır.

## <a name="see-also"></a>Ayrıca bkz.

[Sağlayıcı Sihirbazı Tarafından Üretilen Dosyalar](../../data/oledb/provider-wizard-generated-files.md)<br/>
