---
title: HString::CopyTo yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
ms.assetid: a1fd2ef0-e175-4c18-927b-550e02a89e43
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b44974faf5fc1f068d28d7febe3ed2a266f4869e
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33874778"
---
# <a name="hstringcopyto-method"></a>HString::CopyTo Yöntemi
Kopya geçerli HString HSTRING nesneye nesne.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
HRESULT CopyTo(  
   _Out_ HSTRING *str  
   ) const throw();  
```  
  
#### <a name="parameters"></a>Parametreler  
 `str`  
 Kopya alır HSTRING.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntemi çağırır [WindowsDuplicateString](http://msdn.microsoft.com/library/br224634.aspx) işlevi.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::wrl:: Wrappers  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [HString Sınıfı](../windows/hstring-class.md)