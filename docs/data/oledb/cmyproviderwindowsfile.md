---
title: CMyProviderWindowsFile | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cmyproviderwindowsfile
dev_langs:
- C++
helpviewer_keywords:
- CMyProviderWindowsFile class
- OLE DB providers, wizard-generated files
ms.assetid: 0e9e72ac-1e1e-445f-a7ac-690c20031f9d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5f9549dc81529f4c045a0f27a169516070a09900
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="cmyproviderwindowsfile"></a>CMyProviderWindowsFile
Sihirbaz, bir satır veri içeren sınıf oluşturur; Bu durumda, adlı `CMyProviderWindowsFile`. Aşağıdaki kod `CMyProviderWindowsFile` oluşturulan Sihirbazı'nı ve bir dizindeki tüm dosyaları kullanarak listeleri **WIN32_FIND_DATA** yapısı. `CMyProviderWindowsFile` öğesinden devralınan **WIN32_FIND_DATA** yapısı:  
  
```cpp
/////////////////////////////////////////////////////////////////////  
// MyProviderRS.H  
  
class CMyProviderWindowsFile:   
   public WIN32_FIND_DATA  
{  
public:  
BEGIN_PROVIDER_COLUMN_MAP(CMyProviderWindowsFile)  
   PROVIDER_COLUMN_ENTRY("FileAttributes", 1, dwFileAttributes)  
   PROVIDER_COLUMN_ENTRY("FileSizeHigh", 2, nFileSizeHigh)  
   PROVIDER_COLUMN_ENTRY("FileSizeLow", 3, nFileSizeLow)  
   PROVIDER_COLUMN_ENTRY_STR("FileName", 4, cFileName)  
   PROVIDER_COLUMN_ENTRY_STR("AltFileName", 5, cAlternateFileName)  
END_PROVIDER_COLUMN_MAP()  
};  
```  
  
 `CMyProviderWindowsFile` adlandırılır [kullanıcı kayıt sınıfı](../../data/oledb/user-record.md) de sağlayıcının satır kümesi sütunları tanımlayan bir eşleme içerdiğinden. Sağlayıcı sütun eşlemesi PROVIDER_COLUMN_ENTRY kullanarak satır kümesindeki her bir alan için bir giriş içerir. Makrolar sütun adı, sıra ve girdi yapısına uzaklık belirtin. Yukarıdaki koddaki sağlayıcı sütun girdileri içine uzaklıkları içeren **WIN32_FIND_DATA** yapısı. Tüketici çağırdığında **'yı**, veriler, bir sürekli arabelleğe aktarılır. İşaretçi aritmetiği yapmanıza yapmak yerine, harita, bir veri üyesi belirtmenizi sağlar.  
  
 `CMyProviderRowset` Sınıfı ayrıca içerir `Execute` yöntemi. `Execute` hangi verileri yerel kaynaktan okuyan yöntemdir. Aşağıdaki kod sihirbaz tarafından oluşturulan gösterir `Execute` yöntemi. Win32 işlevini kullanıyor **FindFirstFile** ve `FindNextFile` dizinindeki dosyaları hakkında bilgi almak ve bunları örneklerine yerleştirmek için API'ler `CMyProviderWindowsFile` sınıfı.  
  
```cpp
/////////////////////////////////////////////////////////////////////  
// MyProviderRS.H  
  
HRESULT Execute(DBPARAMS * pParams, LONG* pcRowsAffected)  
{  
   USES_CONVERSION;  
   BOOL bFound = FALSE;  
   HANDLE hFile;  
   LPTSTR  szDir = (m_strCommandText == _T("")) ? _T("*.*") :  
       OLE2T(m_strCommandText);  
   CMyProviderWindowsFile wf;  
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
  
 Arama dizini tarafından temsil edilen `m_strCommandText`; bu tarafından temsil edilen metni içeren `ICommandText` komutu nesnesindeki arabirim. Hiçbir dizin belirtilirse, geçerli dizin kullanır.  
  
 Yöntem (karşılık gelen bir satır) her dosya için bir girdi oluşturur ve yerleştirir **m_rgRowData** veri üyesi. `CRowsetImpl` Sınıfı tanımlayan **m_rgRowData** veri üyesi. Bu dizideki veri tüm tabloyu temsil eder ve tüm şablonlarda kullanılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sağlayıcı Sihirbazı Tarafından Üretilen Dosyalar](../../data/oledb/provider-wizard-generated-files.md)