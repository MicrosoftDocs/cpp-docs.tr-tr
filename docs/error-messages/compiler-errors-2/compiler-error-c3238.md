---
title: "Derleyici Hatası C3238 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3238
dev_langs: C++
helpviewer_keywords: C3238
ms.assetid: 19942497-b3c5-4df0-9144-142ced92468b
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 51af2859cec319678f6b13caf7231a8f62a6177c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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