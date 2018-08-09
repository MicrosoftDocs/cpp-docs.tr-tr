---
title: usesgetlasterror | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.usesgetlasterror
dev_langs:
- C++
helpviewer_keywords:
- usesgetlasterror attribute
ms.assetid: d149e33d-35a7-46cb-9137-ae6883d86122
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 011cf954a0b111e46afcaf6e55a54914075864db
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40014568"
---
# <a name="usesgetlasterror"></a>usesgetlasterror
Bu işlev çağrılırken bir hata ise sonra çağıran ardından çağırabileceğiniz çağıran söyler `GetLastError` hata kodu alınamıyor.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
[usesgetlasterror]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 **Usesgetlasterror** C++ özniteliği ile aynı işlevlere sahip [usesgetlasterror](http://msdn.microsoft.com/library/windows/desktop/aa367297) MIDL özniteliği.  
  
## <a name="example"></a>Örnek  
 Bkz: [idl_module](../windows/idl-module.md) nasıl kullanılacağına ilişkin bir örnek için örnek **usesgetlasterror**.  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**İçin geçerlidir**|**Modül** özniteliği|  
|**Tekrarlanabilir**|Hayır|  
|**Gerekli öznitelikleri**|Yok.|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDL öznitelikleri](../windows/idl-attributes.md)   