---
title: Derleyici Hatası C2589 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2589
dev_langs:
- C++
helpviewer_keywords:
- C2589
ms.assetid: 1d7942c7-8a81-4bb4-b272-76a0019e8513
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c15589358979f554a9c17114f7d78b05dd83c472
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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