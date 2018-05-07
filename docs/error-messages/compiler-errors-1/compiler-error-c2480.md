---
title: Derleyici Hatası C2480 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2480
dev_langs:
- C++
helpviewer_keywords:
- C2480
ms.assetid: 1a58d1c2-971b-4084-96fa-f94aa51c02f1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 987cefa42b3f3f8d9588e446ca181c0b7cd48f8c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2480"></a>Derleyici Hatası C2480
'tanımlayıcısı': 'iş parçacığı' statik kapsam veri öğeleri için geçerli değil yalnızca  
  
 Kullanamazsınız `thread` özniteliği bir otomatik değişkeni, statik olmayan veri üyesi, işlev parametresi veya işlev bildirimleri ya da tanımları.  
  
 Kullanım `thread` genel değişkenler, statik veri üyeleri ve yalnızca yerel statik değişkenler özniteliği.  
  
 Aşağıdaki örnek C2480 oluşturur:  
  
```  
// C2480.cpp  
// compile with: /c  
__declspec( thread ) void func();   // C2480  
__declspec( thread ) static int i;   // OK  
```