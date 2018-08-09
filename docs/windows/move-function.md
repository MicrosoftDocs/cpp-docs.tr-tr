---
title: Move işlevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::Move
dev_langs:
- C++
helpviewer_keywords:
- Move function
ms.assetid: c9525426-97e8-4d8c-9877-b689d8a0dc67
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 018b5832b187223484013702a1b7d4871d0b1d44
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40015722"
---
# <a name="move-function"></a>Move İşlevi
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
template<class T>  
inline typename RemoveReference<T>::Type&& Move(  
   _Inout_ T&& arg  
);  
```  
  
### <a name="parameters"></a>Parametreler  
 *T*  
 Bağımsız değişken türü.  
  
 *bağımsız değişken*  
 Taşımak için bir bağımsız değişken.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Parametre *arg* başvurusunu veya rvalue başvurusunu nitelikler sonra varsa kaldırıldı.  
  
## <a name="remarks"></a>Açıklamalar  
 Belirtilen bağımsız değişken bir konumdan diğerine taşır.  
  
 Daha fazla bilgi için **taşıma semantiği** bölümünü [Rvalue başvuru Bildirimcisi: & &](../cpp/rvalue-reference-declarator-amp-amp.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** internal.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)