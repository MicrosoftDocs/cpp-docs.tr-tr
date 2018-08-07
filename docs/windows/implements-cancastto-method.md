---
title: Implements::cancastto yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Implements::CanCastTo
dev_langs:
- C++
helpviewer_keywords:
- CanCastTo method
ms.assetid: a8e85c7d-4dcd-446d-bebc-a97da46ce44a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 53b17558998812895ece4b47f5de03700e502b8e
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39608949"
---
# <a name="implementscancastto-method"></a>Implements::CanCastTo Yöntemi
Belirtilen arabirim için bir işaretçi alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
__forceinline HRESULT CanCastTo(  
   REFIID riid,  
   _Deref_out_ void **ppv  
);  
```  
  
### <a name="parameters"></a>Parametreler  
 *riid*  
 Başvuru için bir arabirim kimliği.  
  
 *ppv*  
 Başarılı bir arabirim işaretçisi tarafından belirttiyseniz *riid*.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK; Aksi takdirde, e_noınterface gibi hatayı gösteren HRESULT.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu QueryInterface işlemi gerçekleştiren bir iç yardımcı işlevdir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Implements Yapısı](../windows/implements-structure.md)