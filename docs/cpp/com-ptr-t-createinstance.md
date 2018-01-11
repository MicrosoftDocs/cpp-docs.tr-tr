---
title: _com_ptr_t::CreateInstance | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: _com_ptr_t::CreateInstance
dev_langs: C++
helpviewer_keywords: CreateInstance method [C++]
ms.assetid: ab89b0e1-9da3-4784-a079-58b17340f111
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e4764cf615bf04e9f2b1c3c816becc5a58da35f3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
  
-   **CreateInstance (** `clsidString` **,**`dwClsContext`**)** ya da tutan bir UNICODE dizesi belirtilen bir nesne yeni çalışan bir örneğini oluşturur bir **CLSID** (başlayarak "**{**") veya bir **ProgID**.  
  
-   **CreateInstance (** `clsidStringA` **,**`dwClsContext`**)** ya da tutan çok baytlı karakter dizesi belirtilen bir nesne yeni çalışan bir örneğini oluşturur bir  **CLSID** (başlayarak "**{**") veya bir **ProgID**. Çağrıları [MultiByteToWideChar](http://msdn.microsoft.com/library/windows/desktop/dd319072), dize OEM kod sayfası yerine ANSI kod sayfası olduğunu varsayar.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_com_ptr_t Sınıfı](../cpp/com-ptr-t-class.md)