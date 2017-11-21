---
title: "HandleT::operator = işleci | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HandleT::operator=
dev_langs: C++
helpviewer_keywords: operator= operator
ms.assetid: 9e42dcca-30fa-4e8b-8954-802fd64a5595
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5c71e29fa31c89c030b74843a9d776923fed6789
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="handletoperator-operator"></a>HandleT::operator= İşleci
Belirtilen HandleT nesnenin değerini geçerli HandleT nesneye taşır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HandleT& operator=(  
   _Inout_ HandleT&& h  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `h`  
 Bir rvalue başvuru bir işlenecek.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Geçerli HandleT nesneye başvuru.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlem parametresi tarafından belirtilen HandleT nesnesi geçersiz kılar `h`.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::wrl:: Wrappers  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [HandleT sınıfı](../windows/handlet-class.md)