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
ms.openlocfilehash: fcd27ab7132739987859024270ac6c82be06e590
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39607799"
---
# <a name="hstringreferencecopyto-method"></a>HStringReference::CopyTo Yöntemi
Geçerli kopyalar **HStringReference** nesnesini bir HSTRING nesnesine.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT CopyTo(  
   _Out_ HSTRING *str  
   ) const throw();  
```  
  
#### <a name="parameters"></a>Parametreler  
 *str*  
 Kopyayı alan HSTRING.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntemin çağırdığı [WindowsDuplicateString](http://msdn.microsoft.com/library/br224634.aspx) işlevi.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::wrl:: Wrappers  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [HStringReference Sınıfı](../windows/hstringreference-class.md)