---
title: "WeakReference::SetUnknown yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::Details::WeakReference::SetUnknown
dev_langs: C++
helpviewer_keywords: SetUnknown method
ms.assetid: 5dddb9e3-a7c1-4195-8166-97c5ab6e972f
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 82a556ddc855c2ab9793f74fa091c464e094cb80
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="weakreferencesetunknown-method"></a>WeakReference::SetUnknown Yöntemi
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void SetUnknown(  
   _In_ IUnknown* unk  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `unk`  
 Bir işaretçi `IUnknown` nesnenin arabirimi.  
  
## <a name="remarks"></a>Açıklamalar  
 Güçlü Başvuru geçerli ayarlar `WeakReference` belirtilen arabirim işaretçisi nesnesine.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** implements.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.
[WeakReference sınıfı](../windows/weakreference-class1.md)  
 [Microsoft::wrl:: details Namespace](../windows/microsoft-wrl-details-namespace.md)