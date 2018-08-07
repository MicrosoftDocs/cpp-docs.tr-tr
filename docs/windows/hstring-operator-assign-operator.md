---
title: HString::Operator = işleci | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString::operator=
dev_langs:
- C++
ms.assetid: 8e68c1ff-bc57-4526-810e-af3c284b4e30
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9cc496f4f1c23508b2ebba2788910ff9c9ca2066
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39608605"
---
# <a name="hstringoperator-operator"></a>HString::Operator= İşleci
Başka bir değer taşır **Hstrıng** geçerli nesneye **Hstrıng** nesne.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HString& operator=(HString&& other) throw()  
```  
  
### <a name="parameters"></a>Parametreler  
 *Diğer*  
 Mevcut bir **Hstrıng** nesne.  
  
## <a name="remarks"></a>Açıklamalar  
 Varolan değerin *diğer* nesne geçerli kopyalanır **Hstrıng** nesnesi ve ardından *diğer* nesnesi yok edildiğinde.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::wrl:: Wrappers  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [HString Sınıfı](../windows/hstring-class.md)