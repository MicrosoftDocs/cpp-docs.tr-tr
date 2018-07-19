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
ms.openlocfilehash: ccff761cb9b738de9e2f0debc470746d1482ab56
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37940374"
---
# <a name="comptrtgetactiveobject"></a>_com_ptr_t::GetActiveObject
**Microsoft'a özgü**  
  
 Verilen bir nesnenin varolan örneğine için bir `CLSID` veya `ProgID`.  
  
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
 *rclsid*  
 `CLSID` Bir nesne.  
  
 *clsidString*  
 Bulunduran bir Unicode dizesini bir `CLSID` (sürümünden itibaren "**{**") veya bir `ProgID`.  
  
 *clsidStringA*  
 Bulunduran ANSI kod sayfasını kullanarak çok baytlı bir dize bir `CLSID` (sürümünden itibaren "**{**") veya bir `ProgID`.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu üye işlevleri OLE ile kaydedilmiş çalışan bir nesnenin işaretçisini almak için `GetActiveObject`'i çağırır ve ardından bu akıllı işaretçinin arabirim türünü sorgular. Elde edilen işaretçi, daha bu `_com_ptr_t` nesnesinin içinde kapsüllenir. `Release` daha önce Kapsüllenen işaretçi için başvuru sayısını azaltma için çağrılır. Bu yordam, başarıyı veya başarısızlığı göstermek için HRESULT döndürür.  
  
-   **GetActiveObject (**`rclsid`**)** için verilen bir nesnenin varolan örneğine bir `CLSID`.      
  
-   **GetActiveObject (**`clsidString`**)** bulunduran Unicode dizesi verilmiş nesnenin varolan örneğine için bir `CLSID` (sürümünden itibaren "**{**") veya bir `ProgID`.      
  
-   **GetActiveObject (**`clsidStringA`**)** bulunduran çok baytlı karakter dizesi verilmiş nesnenin varolan örneğine bağlanan bir `CLSID` (sürümünden itibaren "**{**") veya `ProgID`.     Çağrıları [MultiByteToWideChar](http://msdn.microsoft.com/library/windows/desktop/dd319072), dizenin OEM kod sayfası yerine ANSI kod sayfası olduğunu varsayar.  
  
 **END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_com_ptr_t Sınıfı](../cpp/com-ptr-t-class.md)