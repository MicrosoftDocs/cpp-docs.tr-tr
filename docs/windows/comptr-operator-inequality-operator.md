---
title: ComPtr::operator! = işleci | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::operator!=
dev_langs:
- C++
ms.assetid: 63647240-dec7-4eb9-9272-96c07d01493c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0a4c15946862a66c0d4d830f590230763ce3e6f9
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39461828"
---
# <a name="comptroperator-operator"></a>ComPtr::operator!= İşleci
Belirtir olup iki **ComPtr** nesneler eşit değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
bool operator!=(  
   const ComPtr<T>& a,  
   const ComPtr<U>& b  
);  
  
bool operator!=(  
   const ComPtr<T>& a,  
   decltype(__nullptr)  
);  
  
bool operator!=(  
   decltype(__nullptr),  
   const ComPtr<T>& a  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *a*  
 Bir başvuru bir **ComPtr** nesne.  
  
 *b*  
 Başka bir başvuru **ComPtr** nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 İlk işleç sayıları **true** , nesne *bir* nesnesine eşit değil *b*; Aksi takdirde **false**.  
  
 İkinci ve üçüncü işleçleri yield **true** , nesne *bir* eşit değildir **nullptr**; Aksi takdirde **false**.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL Namespace](../windows/microsoft-wrl-namespace.md)   
 [ComPtr Sınıfı](../windows/comptr-class.md)