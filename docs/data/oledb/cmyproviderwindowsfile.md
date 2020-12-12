---
description: 'Daha fazla bilgi edinin: CCustomWindowsFile'
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
ms.openlocfilehash: c0df2840b68a350f9d65102fdf0a962681edefd9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97170405"
---
# <a name="ccustomwindowsfile"></a>CCustomWindowsFile

Sihirbaz bir veri satırı içeren bir sınıf oluşturur; Bu durumda, çağırılır `CCustomWindowsFile` . Aşağıdaki kod `CCustomWindowsFile` Sihirbazı oluşturulur ve yapısını kullanarak bir dizindeki tüm dosyaları listeler `WIN32_FIND_DATA` . `CCustomWindowsFile``WIN32_FIND_DATA`yapıdan devralır:

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

`CCustomWindowsFile` , sağlayıcının satır kümesindeki sütunları açıklayan bir eşlem de içerdiğinden, [Kullanıcı kayıt sınıfı](../../data/oledb/user-record.md) olarak adlandırılır. Sağlayıcı sütun eşlemesi, PROVIDER_COLUMN_ENTRY makroları kullanarak satır kümesindeki her alan için bir giriş içerir. Makrolar sütun adını, sıra sayısını ve bir yapı girişinin konumunu belirtir. Yukarıdaki koddaki sağlayıcı sütun girdileri yapıya uzaklık içerir `WIN32_FIND_DATA` . Tüketici çağırdığında `IRowset::GetData` , veriler bir ardışık arabellekte aktarılır. Bir işaretçi aritmetik yapmak yerine, eşleme bir veri üyesi belirtmenize olanak tanır.

`CCustomRowset`Sınıfı yöntemi de içerir `Execute` . `Execute` Yerel kaynaktaki içindeki verileri gerçekte okur. Aşağıdaki kod, sihirbaz tarafından oluşturulan yöntemi gösterir `Execute` . İşlevi, `FindFirstFile` `FindNextFile` dizindeki dosyalar hakkında bilgi almak ve bunları sınıfının örneklerine yerleştirmek için Win32 ve API 'leri kullanır `CCustomWindowsFile` .

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

Arama yapılacak dizin tarafından gösterilir `m_strCommandText` ; Bu, komut nesnesindeki arabirim tarafından temsil edilen metni içerir `ICommandText` . Dizin belirtilmemişse, geçerli dizini kullanır.

Yöntemi her dosya için (bir satıra karşılık gelen) bir giriş oluşturur ve bunu `m_rgRowData` veri üyesine koyar. `CRowsetImpl`Sınıf, `m_rgRowData` veri üyesini tanımlar. Bu dizideki veriler tablonun tamamında gösterilir ve şablonlar boyunca kullanılır.

## <a name="see-also"></a>Ayrıca bkz.

[Sağlayıcı Wizard-Generated dosyaları](../../data/oledb/provider-wizard-generated-files.md)<br/>
