---
title: Chainınterfaces::ıidcount sabiti | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::ChainInterfaces::IidCount
dev_langs:
- C++
helpviewer_keywords:
- IidCount constant
ms.assetid: d4a90aa0-513c-4e99-b978-e12149734936
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6d089e9639d83150e501b32577de94fc43b516c1
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39463947"
---
# <a name="chaininterfacesiidcount-constant"></a>ChainInterfaces::IidCount Sabiti
Arabirim kimlikleri şablon parametreleri tarafından belirtilen arabirimlerden bulunan toplam sayısı *I0* aracılığıyla *I9*.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
static const unsigned long IidCount = Details::InterfaceTraits<I0>::IidCount + Details::InterfaceTraits<I1>::IidCount + Details::InterfaceTraits<I2>::IidCount + Details::InterfaceTraits<I3>::IidCount + Details::InterfaceTraits<I4>::IidCount + Details::InterfaceTraits<I5>::IidCount + Details::InterfaceTraits<I6>::IidCount + Details::InterfaceTraits<I7>::IidCount + Details::InterfaceTraits<I8>::IidCount + Details::InterfaceTraits<I9>::IidCount;  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Arabirim kimlikleri toplam sayısı.  
  
## <a name="remarks"></a>Açıklamalar  
 Şablon parametreleri *I0* ve *I1* gereklidir ve parametreleri *I2* aracılığıyla *I9* isteğe bağlıdır. Genellikle her arabirim IID'si sayısı 1'dir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ChainInterfaces Yapısı](../windows/chaininterfaces-structure.md)