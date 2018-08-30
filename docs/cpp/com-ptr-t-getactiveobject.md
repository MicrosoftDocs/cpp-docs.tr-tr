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
ms.openlocfilehash: 0555b050770d5fbd411e1720282e3fb50769385b
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43208410"
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
 Bu üye işlevleri çağırma **GetActiveObject** OLE ile kaydedilmiş çalışan bir nesnenin işaretçisini almak için ve ardından bu akıllı işaretçinin sorgularında arabirim türü. Elde edilen işaretçi, daha bu `_com_ptr_t` nesnesinin içinde kapsüllenir. `Release` daha önce Kapsüllenen işaretçi için başvuru sayısını azaltma için çağrılır. Bu yordam, başarıyı veya başarısızlığı göstermek için HRESULT döndürür.  
  
-   **GetActiveObject (**`rclsid`**)** için verilen bir nesnenin varolan örneğine bir `CLSID`.  
  
-   **GetActiveObject (**`clsidString`**)** bulunduran Unicode dizesi verilmiş nesnenin varolan örneğine için bir `CLSID` (sürümünden itibaren "**{**") veya bir `ProgID`.  
  
-   **GetActiveObject (**`clsidStringA`**)** bulunduran çok baytlı karakter dizesi verilmiş nesnenin varolan örneğine bağlanan bir `CLSID` (sürümünden itibaren "**{**") veya `ProgID`. Çağrıları [MultiByteToWideChar](/windows/desktop/api/stringapiset/nf-stringapiset-multibytetowidechar), dizenin OEM kod sayfası yerine ANSI kod sayfası olduğunu varsayar.  
  
 **END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [_com_ptr_t Sınıfı](../cpp/com-ptr-t-class.md)