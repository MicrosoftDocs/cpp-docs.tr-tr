---
title: "Derleyici Uyarısı (Düzey 2) C4099 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4099
dev_langs:
- C++
helpviewer_keywords:
- C4099
ms.assetid: 00bb803d-cae7-4ab8-8969-b46f54139ac8
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1eb64e859ef40397edeb872cc7f6f228f7ae89e8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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