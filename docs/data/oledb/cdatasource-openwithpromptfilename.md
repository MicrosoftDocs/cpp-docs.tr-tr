---
title: CDataSource::OpenWithPromptFileName | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDataSource.OpenWithPromptFileName
- OpenWithPromptFileName
- ATL::CDataSource::OpenWithPromptFileName
- ATL.CDataSource.OpenWithPromptFileName
- CDataSource::OpenWithPromptFileName
dev_langs:
- C++
helpviewer_keywords:
- OpenWithPromptFileName method
ms.assetid: 89460504-1aaf-4412-aa7b-fa5a4b39ada3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: abaf78245dabff8349795fbd8cb7ab38b32c4978
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="cdatasourceopenwithpromptfilename"></a>CDataSource::OpenWithPromptFileName
Bu yöntem kullanıcıdan bir iletişim kutusu, sonra kullanıcı tarafından belirtilen dosyası kullanarak bir veri kaynağı açar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
HRESULT OpenWithPromptFileName(HWND hWnd = GetActiveWindow(   ),   
   DBPROMPTOPTIONS dwPromptOptions = DBPROMPTOPTIONS_NONE,   
   LPCOLESTR szInitialDirectory = NULL) throw();  
```  
  
#### <a name="parameters"></a>Parametreler  
 `hWnd`  
 [in] İletişim kutusunun üst olacak penceresine işleyin.  
  
 `dwPromptOptions`  
 [in] Bulucu iletişim kutusunu görüntülemek için stilini belirler. Olası değerler için msdasc.h bakın.  
  
 *szInitialDirectory*  
 [in] Bulucu iletişim kutusunda görüntülenecek başlangıç dizini.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT`.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem oledb32.dll içinde hizmet Bileşenleri'ni kullanarak bir veri kaynağı nesnesi açar; Bu DLL kaynak havuzu, otomatik işlem kaydı vb. gibi hizmet bileşenleri özellikleri uygulamasını içerir. Daha fazla bilgi için bkz: "OLE DB hizmetleri" OLE DB Programcı Başvurusu, [http://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true](http://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CDataSource Sınıfı](../../data/oledb/cdatasource-class.md)