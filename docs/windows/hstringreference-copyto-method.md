---
title: HStringReference::CopyTo yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
ms.assetid: 179d9b14-1ced-4b16-b297-19ca1e92a462
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f65c08cad438328eb1a0e15495774dbde6845f4d
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="hstringreferencecopyto-method"></a>HStringReference::CopyTo Yöntemi
Kopya geçerli HStringReference HSTRING nesneye nesne.  
  
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
 [HStringReference Sınıfı](../windows/hstringreference-class.md)