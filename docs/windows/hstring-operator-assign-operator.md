---
title: "HString::Operator = işleci | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString::operator=
dev_langs:
- C++
ms.assetid: 8e68c1ff-bc57-4526-810e-af3c284b4e30
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5abaa00030b301607c19def42920cb01eb72600a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="hstringoperator-operator"></a>HString::Operator= İşleci
Başka bir HString nesnenin değerini geçerli HString nesneye taşır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HString& operator=(HString&& other) throw()  
```  
  
#### <a name="parameters"></a>Parametreler  
 `other`  
 Varolan bir HString nesne.  
  
## <a name="remarks"></a>Açıklamalar  
 Var olan değerin `other` nesne geçerli HString nesnesine kopyalanır ve ardından `other` nesne yok.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::wrl:: Wrappers  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [HString Sınıfı](../windows/hstring-class.md)