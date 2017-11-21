---
title: "Derleyici Hatası C3163 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3163
dev_langs: C++
helpviewer_keywords: C3163
ms.assetid: 17dcafa3-f416-4e04-a232-f9569218ba75
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 95fb254036d2883b6efe6b81bda54864d533c2a8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3163"></a>Derleyici Hatası C3163
'oluşturmak': öznitelikler önceki bildirimiyle tutarsız  
  
 Bir tanımına uygulanan öznitelikleri bir bildirimine uygulanan öznitelikleri çakışıyor.  
  
 C3163 çözmenin bir yolu, ileriye dönük bildirimi özniteliklerinde ortadan kaldırmaktır. Herhangi bir iletme bildirimi özniteliklerinde tanımı özniteliklerinde değerinden küçük olması veya gerekir, en fazla onlara eşit.  
  
 C3163 hatanın olası bir nedeni, Microsoft kaynak kodu ek açıklama dili (SAL) içerir. Kullanarak projenizi derleme sürece SAL makroları genişletmeyin **/ analyze** bayrağı. İle derlemeniz çalışırsanız olmadan düzgün bir şekilde derler / analyze bir program C3163 throw / analyze seçeneği. SAL hakkında daha fazla bilgi için bkz: [SAL ek açıklamaları](../../c-runtime-library/sal-annotations.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3163 oluşturur.  
  
```  
// C3163.cpp  
// compile with: /clr /c  
using namespace System;  
  
[CLSCompliant(true)] void f();  
[CLSCompliant(false)] void f() {}   // C3163  
// try the following line instead  
// [CLSCompliant(true)] void f() {}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SAL ek açıklamaları](../../c-runtime-library/sal-annotations.md)