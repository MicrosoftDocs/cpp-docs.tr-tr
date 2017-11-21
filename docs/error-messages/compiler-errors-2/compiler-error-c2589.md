---
title: "Derleyici Hatası C2589 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2589
dev_langs: C++
helpviewer_keywords: C2589
ms.assetid: 1d7942c7-8a81-4bb4-b272-76a0019e8513
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5301caf0b52e61000a804e1d73b76343a8b7b2eb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2589"></a>Derleyici Hatası C2589
'tanımlayıcısı': geçersiz bir belirteç sağ tarafındaki '::'  
  
 Kapsam çözümü işleci (çift iki nokta üst üste) soluna sınıf, yapı veya birleşim adı görünürse, sağdaki belirteç sınıf, yapı veya bileşim üyesi olmalıdır. Aksi takdirde, herhangi bir genel tanımlayıcı sağda yer alabilir.  
  
 Kapsam çözümü işleci aşırı yüklenemez.  
  
 Aşağıdaki örnek C2589 oluşturur:  
  
```  
// C2589.cpp  
void Test(){}  
class A {};  
void operator :: ();   // C2589  
  
int main() {  
   ::Test();  
}  
```