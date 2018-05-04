---
title: _com_ptr_t::CreateInstance | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_ptr_t::CreateInstance
dev_langs:
- C++
helpviewer_keywords:
- CreateInstance method [C++]
ms.assetid: ab89b0e1-9da3-4784-a079-58b17340f111
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 70ccd73980295bdda67a4c49d034b6d185d2d93c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="comptrtcreateinstance"></a>_com_ptr_t::CreateInstance
**Microsoft özel**  
  
 Verilen bir nesne yeni bir örneğini oluşturur bir **CLSID** veya **ProgID**.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      HRESULT CreateInstance(  
   const CLSID& rclsid,  
   IUnknown* pOuter=NULL,  
   DWORD dwClsContext = CLSCTX_ALL   
) throw( );  
HRESULT CreateInstance(  
   LPCWSTR clsidString,  
   IUnknown* pOuter=NULL,  
   DWORD dwClsContext = CLSCTX_ALL   
) throw( );  
HRESULT CreateInstance(  
   LPCSTR clsidStringA,  
   IUnknown* pOuter=NULL,  
   DWORD dwClsContext = CLSCTX_ALL   
) throw( );  
```  
  
#### <a name="parameters"></a>Parametreler  
 `rclsid`  
 **CLSID** bir nesne.  
  
 `clsidString`  
 Ya da tutan bir UNICODE dizesi bir **CLSID** (başlayarak "**{**") veya bir **ProgID**.  
  
 `clsidStringA`  
 Ya da tutan ANSI kod sayfası kullanılarak birden çok baytlı bir dize bir **CLSID** (başlayarak "**{**") veya bir **ProgID**.  
  
 `dwClsContext`  
 Yürütülebilir kodu çalıştırmak için bağlam.  
  
 `pOuter`  
 İçin dış bilinmeyen [toplama](../atl/aggregation.md).  
  
## <a name="remarks"></a>Açıklamalar  
 Bu üye işlevleri çağırma `CoCreateInstance` yeni bir COM nesnesi ve ardından bu akıllı işaretçinin arabirim türü için sorgular oluşturmak için. Elde edilen işaretçi, daha bu `_com_ptr_t` nesnesinin içinde kapsüllenir. **Yayın** önceden kapsüllenmiş işaretçi başvuru sayısı azaltma için çağrılır. Bu yordam, başarıyı veya başarısızlığı göstermek için `HRESULT` döndürür.  
  
-   **CreateInstance (** `rclsid` **,**`dwClsContext`**)** verilen bir nesne yeni çalışan bir örneğini oluşturur bir **CLSID**.        
  
-   **CreateInstance (** `clsidString` **,**`dwClsContext`**)** ya da tutan bir UNICODE dizesi belirtilen bir nesne yeni çalışan bir örneğini oluşturur bir **CLSID**(başlayarak "**{**") veya bir **ProgID**.        
  
-   **CreateInstance (** `clsidStringA` **,**`dwClsContext`**)** ya da tutan çok baytlı karakter dizesi belirtilen bir nesne yeni çalışan bir örneğini oluşturur bir **CLSID**  (başlayarak "**{**") veya bir **ProgID**.       Çağrıları [MultiByteToWideChar](http://msdn.microsoft.com/library/windows/desktop/dd319072), dize OEM kod sayfası yerine ANSI kod sayfası olduğunu varsayar.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_com_ptr_t Sınıfı](../cpp/com-ptr-t-class.md)