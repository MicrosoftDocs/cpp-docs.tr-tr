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
ms.openlocfilehash: bde476af66ae0a5a560019db29d25385c718e517
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43201808"
---
# <a name="comptrtcreateinstance"></a>_com_ptr_t::CreateInstance
**Microsoft'a özgü**  
  
 Verilen nesne yeni bir örneğini oluşturur bir `CLSID` veya `ProgID`.  
  
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
 *rclsid*  
 `CLSID` Bir nesne.  
  
 *clsidString*  
 Bulunduran bir Unicode dizesini bir `CLSID` (sürümünden itibaren "**{**") veya bir `ProgID`.  
  
 *clsidStringA*  
 Bulunduran ANSI kod sayfasını kullanarak çok baytlı bir dize bir `CLSID` (sürümünden itibaren "**{**") veya bir `ProgID`.  
  
 *dwClsContext*  
 Yürütülebilir kodu çalıştırmak için bağlam.  
  
 *pOuter*  
 İçin dış bilinmeyen [toplama](../atl/aggregation.md).  
  
## <a name="remarks"></a>Açıklamalar  
 Bu üye işlevleri çağırma `CoCreateInstance` yeni bir COM nesnesi ve ardından bu akıllı işaretçinin arabirim türünü sorgularını oluşturmak için. Elde edilen işaretçi, daha bu `_com_ptr_t` nesnesinin içinde kapsüllenir. `Release` daha önce Kapsüllenen işaretçi için başvuru sayısını azaltma için çağrılır. Bu yordam, başarıyı veya başarısızlığı göstermek için HRESULT döndürür.  
  
-   **CreateInstance (***rclsid* **,***dwClsContext***)** bir verilmişbirnesneninyeniçalışanbirörneğinioluşturur`CLSID`.  
  
-   **CreateInstance (***clsidString* **,***dwClsContext***)** verilmiş bir nesnenin yeni çalışan bir örneğini oluşturur bir Bulunduran Unicode dizesi bir `CLSID` (sürümünden itibaren "**{**") veya bir `ProgID`.  
  
-   **CreateInstance (***clsidStringA* **,***dwClsContext***)** verilmiş bir nesnenin yeni çalışan bir örneğini oluşturur bir bulunduran çok baytlı karakter dizesi bir `CLSID` (sürümünden itibaren "**{**") veya bir `ProgID`. Çağrıları [MultiByteToWideChar](/windows/desktop/api/stringapiset/nf-stringapiset-multibytetowidechar), dizenin OEM kod sayfası yerine ANSI kod sayfası olduğunu varsayar.  
  
 **END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [_com_ptr_t Sınıfı](../cpp/com-ptr-t-class.md)