---
title: Derleyici Hatası C2435 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2435
dev_langs:
- C++
helpviewer_keywords:
- C2435
ms.assetid: be6aa8f8-579b-42ea-bdd8-2d01393646ad
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 44c4dec71cdf077dc8fbd1ba81b555090b524007
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2435"></a>Derleyici Hatası C2435
'var': / clr: safe ile derlenemiyor, yönetilen CRT gerektirdiğinde dinamik başlatma  
  
 **/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı.  
  
 Genel uygulama başına etki alanı değişkenini, başlatma gerektiriyorsa ile derlenmiş CRT `/clr:pure`, hangi değil üretmek doğrulanabilen bir görüntüsü.  
  
 Daha fazla bilgi için bkz: [appdomain](../../cpp/appdomain.md) ve [işlem](../../cpp/process.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C2435 oluşturur:  
  
```  
// C2435.cpp  
// compile with: /clr:safe /c  
int globalvar = 0;   // C2435  
  
__declspec(process)  
int globalvar2 = 0;  
```