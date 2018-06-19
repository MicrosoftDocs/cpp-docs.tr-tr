---
title: Derleyici Hatası C2785 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2785
dev_langs:
- C++
helpviewer_keywords:
- C2785
ms.assetid: d8d13360-0d00-4815-8475-b49c7f0dc0f3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dc0ca6235e0fd4bdd22330e807464e96280ae461
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33234035"
---
# <a name="compiler-error-c2785"></a>Derleyici Hatası C2785
'declaration1' ve 'declaration2' farklı dönüş türlerine sahip  
  
 İşlev şablonu uzmanlık dönüş türü birincil işlev şablonunun dönüş türünden farklı.  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
1.  Tüm özelleştirmeleri işlevi şablonunun tutarlılığını denetleyin.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C2785 oluşturur:  
  
```  
// C2785.cpp  
// compile with: /c  
template<class T> void f(T);  
  
template<> int f(int); // C2785  
template<> void f(int); // OK  
```