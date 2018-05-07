---
title: Derleyici Hatası C3238 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3238
dev_langs:
- C++
helpviewer_keywords:
- C3238
ms.assetid: 19942497-b3c5-4df0-9144-142ced92468b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 33252d094847869fda07ad55563b085853681793
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3238"></a>Derleyici Hatası C3238
'type': Bu ada sahip bir türü 'assembly' derlemesine iletildi  
  
 Ayrıca, başvurulan bir derleme sözdizimi iletme türü yoluyla tanımlı bir istemci uygulamasında bir tür tanımlandı. Her iki tür uygulamayı kapsamında tanımlanamaz.  
  
 Bkz: [tür iletme (C + +/ CLI)](../../windows/type-forwarding-cpp-cli.md) daha fazla bilgi için.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, başka bir derlemeden iletildi türünü içeren bütünleştirilmiş oluşturur.  
  
```  
// C3238.cpp  
// compile with: /clr /LD  
public ref class R {};  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek tür tanımı kapsamak için kullanılmış bir derleme oluşturur, ancak yalnızca sözdizimi iletme türünü içerir.  
  
```  
// C3238_b.cpp  
// compile with: /clr /LD  
#using "C3238.dll"  
[ assembly:TypeForwardedTo(R::typeid) ];  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3238 oluşturur.  
  
```  
// C3238_c.cpp  
// compile with: /clr /c  
// C3238 expected  
// Delete the following line to resolve.  
#using "C3238_b.dll"  
public ref class R {};  
```