---
title: "HString::Operator = işleci | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HString::operator=
dev_langs: C++
ms.assetid: 8e68c1ff-bc57-4526-810e-af3c284b4e30
caps.latest.revision: "2"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ec8e77d1074b3dbd10d68f205af656d7f33aa334
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [HString sınıfı](../windows/hstring-class.md)