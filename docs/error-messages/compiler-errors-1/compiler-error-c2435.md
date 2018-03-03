---
title: "Derleyici Hatası C2435 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2435
dev_langs:
- C++
helpviewer_keywords:
- C2435
ms.assetid: be6aa8f8-579b-42ea-bdd8-2d01393646ad
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1616208a5ea0b8c3680e87a23846fc58be816623
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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