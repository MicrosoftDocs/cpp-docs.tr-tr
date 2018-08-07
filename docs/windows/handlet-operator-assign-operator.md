---
title: HandleT::operator = işleci | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleT::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator= operator
ms.assetid: 9e42dcca-30fa-4e8b-8954-802fd64a5595
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ab629946b9fc5acec6b0fb0ba8f573a3fa90a031
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/06/2018
ms.locfileid: "39570047"
---
# <a name="handletoperator-operator"></a>HandleT::operator= İşleci
Belirtilen değer taşır **HandleT** geçerli nesneye **HandleT** nesne.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HandleT& operator=(  
   _Inout_ HandleT&& h  
);  
```  
  
### <a name="parameters"></a>Parametreler  
 *h*  
 Bir rvalue başvuru için bir tanıtıcı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Geçerli bir başvuru **HandleT** nesne.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlem geçersiz kılar **HandleT** parametresi tarafından belirtilen nesne *h*.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::wrl:: Wrappers  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [HandleT Sınıfı](../windows/handlet-class.md)