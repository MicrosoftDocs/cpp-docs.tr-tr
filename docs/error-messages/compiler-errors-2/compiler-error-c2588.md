---
title: Derleyici Hatası C2588 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2588
dev_langs:
- C++
helpviewer_keywords:
- C2588
ms.assetid: 19a0cabd-ca13-44a5-9be3-ee676abf9bc4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 67eb6362ff55e09b05349d10fcdc2377d8ff2996
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33231676"
---
# <a name="compiler-error-c2588"></a>Derleyici Hatası C2588
':: ~ tanımlayıcısı ': Geçersiz Genel yok Edicisi  
  
 Yıkıcı bir şey için sınıf, yapı veya birleşim dışında tanımlanır. Bu duruma izin verilmez.  
  
 Bu hata eksik sınıf, yapı veya kapsam çözümü sol tarafındaki birleşim adı neden olabilir (`::`) işleci.  
  
 Aşağıdaki örnek C2588 oluşturur:  
  
```  
// C2588.cpp  
~F();   // C2588  
```