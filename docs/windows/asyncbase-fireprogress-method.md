---
title: AsyncBase::FireProgress yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::FireProgress
dev_langs:
- C++
helpviewer_keywords:
- FireProgress method
ms.assetid: 4512bef6-0ebc-4465-9b8a-4c9dfa82084c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: faa2e1af556f0184fa88055bcbf154eb783e24e5
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39463603"
---
# <a name="asyncbasefireprogress-method"></a>AsyncBase::FireProgress Yöntemi
Geçerli ilerleme olay işleyicisini çağırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void FireProgress(  
   const typename ProgressTraits::Arg2Type arg  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *bağımsız değişken*  
 Çağrılacak olay işleyicisi yöntemi.  
  
## <a name="remarks"></a>Açıklamalar  
 `ProgressTraits` türetilen [ArgTraitsHelper yapısı](../windows/argtraitshelper-structure.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** async.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [AsyncBase Sınıfı](../windows/asyncbase-class.md)