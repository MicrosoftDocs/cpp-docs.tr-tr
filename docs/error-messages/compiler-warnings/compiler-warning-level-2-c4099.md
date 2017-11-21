---
title: "Derleyici Uyarısı (Düzey 2) C4099 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4099
dev_langs: C++
helpviewer_keywords: C4099
ms.assetid: 00bb803d-cae7-4ab8-8969-b46f54139ac8
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: af0f7aacb5e4600b48120576135b2052af2a5315
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-2-c4099"></a>Derleyici Uyarısı (düzey 2) C4099
'tanımlayıcısı': 'şimdi 'objecttype2' kullanarak görülen objecttype1' kullanarak ilk kez görülen türü adı  
  
 Bir yapı bildirilen bir nesne bir sınıf olarak tanımlı değil veya bir sınıf olarak bildirilen bir nesne yapısı olarak tanımlanır. Derleyici tanımında belirtilen türünü kullanır.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4099 oluşturur.  
  
```  
// C4099.cpp  
// compile with: /W2 /c  
struct A;  
class A {};   // C4099, use different identifer or use same object type  
```