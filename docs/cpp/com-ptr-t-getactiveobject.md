---
title: _com_ptr_t::GetActiveObject | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_ptr_t::GetActiveObject
dev_langs:
- C++
helpviewer_keywords:
- GetActiveObject method [C++]
ms.assetid: 2fa94853-0410-4620-91f2-136dae923f9f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4ca25ca31475d2870e62d00676e7bf3717c10fa3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="comptrtgetactiveobject"></a>_com_ptr_t::GetActiveObject
**Microsoft özel**  
  
 Varolan bir nesneyi, verilen örneğine bağlanan bir **CLSID** veya **ProgID**.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      HRESULT GetActiveObject(  
   const CLSID& rclsid   
) throw( );  
HRESULT GetActiveObject(  
   LPCWSTR clsidString   
) throw( );  
HRESULT GetActiveObject(  
   LPCSTR clsidStringA   
) throw( );  
```  
  
#### <a name="parameters"></a>Parametreler  
 `rclsid`  
 **CLSID** bir nesne.  
  
 `clsidString`  
 Ya da tutan bir UNICODE dizesi bir **CLSID** (başlayarak "**{**") veya bir **ProgID**.  
  
 `clsidStringA`  
 Ya da tutan ANSI kod sayfası kullanılarak birden çok baytlı bir dize bir **CLSID** (başlayarak "**{**") veya bir **ProgID**.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu üye işlevleri OLE ile kaydedilmiş çalışan bir nesnenin işaretçisini almak için `GetActiveObject`'i çağırır ve ardından bu akıllı işaretçinin arabirim türünü sorgular. Elde edilen işaretçi, daha bu `_com_ptr_t` nesnesinin içinde kapsüllenir. **Yayın** önceden kapsüllenmiş işaretçi başvuru sayısı azaltma için çağrılır. Bu yordam, başarıyı veya başarısızlığı göstermek için `HRESULT` döndürür.  
  
-   **GetActiveObject (**`rclsid`**)** varolan bir nesneyi, verilen örneğine bağlanan bir **CLSID**.      
  
-   **GetActiveObject (**`clsidString`**)** varolan ya da tutan bir UNICODE dizesi belirtilen bir nesne örneğine bağlanan bir **CLSID** (başlayarak "**{**") veya bir **ProgID**.      
  
-   **GetActiveObject (**`clsidStringA`**)** varolan ya da tutan çok baytlı karakter dizesi belirtilen bir nesne örneğine bağlanan bir **CLSID** (başlayarak "**{** ") veya bir **ProgID**.     Çağrıları [MultiByteToWideChar](http://msdn.microsoft.com/library/windows/desktop/dd319072), dize OEM kod sayfası yerine ANSI kod sayfası olduğunu varsayar.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_com_ptr_t Sınıfı](../cpp/com-ptr-t-class.md)