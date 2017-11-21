---
title: "Conditional sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: type_traits/std::conditional
dev_langs: C++
helpviewer_keywords:
- conditional class
- conditional
ms.assetid: ece9f539-fb28-4e26-a79f-3264bc984493
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 08c0428f5ed82c0890cdbcbb051f128c52281ce7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="conditional-class"></a>conditional Sınıfı
Belirtilen koşula göre, iki türden birini seçer.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <bool B, class T1, class T2>  
struct conditional;

template <bool _Test, class _T1, class _T2>  
using conditional_t = typename conditional<_Test, _T1, _T2>::type;
```  
  
#### <a name="parameters"></a>Parametreler  
 `B`  
 Seçili türü belirleyen değer.  
  
 `T1`  
 B true olduğunda türü sonucu.  
  
 `T2`  
 B false olduğunda türü sonucu.  
  
## <a name="remarks"></a>Açıklamalar  
 Şablon üye typedef `conditional<B, T1, T2>::type` değerlendiren `T1` zaman `B` değerlendiren `true`ve değerlendiren `T2` zaman `B` değerlendiren `false`.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<type_traits >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [< type_traits >](../standard-library/type-traits.md)



