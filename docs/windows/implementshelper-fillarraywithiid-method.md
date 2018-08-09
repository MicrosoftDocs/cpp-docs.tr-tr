---
title: Implementshelper::fillarraywithıid yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::ImplementsHelper::FillArrayWithIid
dev_langs:
- C++
helpviewer_keywords:
- FillArrayWithIid method
ms.assetid: f60035ee-b7d6-4a08-966d-f88c646944c3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 71fe5244ecf3f7e64192d86f25104daf1139a463
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40010282"
---
# <a name="implementshelperfillarraywithiid-method"></a>ImplementsHelper::FillArrayWithIid Yöntemi
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
void FillArrayWithIid(  
   _Inout_ unsigned long *index,   
   _Inout_ IID* iids) throw();  
```  
  
### <a name="parameters"></a>Parametreler  
 *Dizin*  
 Bu işlem için başlangıç dizi öğesini gösteren sıfır tabanlı dizini. Bu işlem tamamlandığında *dizin* 1 azaltılır.  
  
 *IID'leri*  
 IID'leri türünde bir dizi.  
  
## <a name="remarks"></a>Açıklamalar  
 Belirtilen bir dizi öğesine geçerli sıfırıncı şablon parametresi tarafından belirtilen arabirim kimliği ekler.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** implements.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Implementshelper yapısı](../windows/implementshelper-structure.md)   
 [Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)