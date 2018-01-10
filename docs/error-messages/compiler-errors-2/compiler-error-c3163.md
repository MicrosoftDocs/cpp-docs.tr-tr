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
ms.workload: cplusplus
ms.openlocfilehash: 4d3cbb5c5c3e8391b3a549fc0c34661dc86b492c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
 [SAL Ek Açıklamaları](../../c-runtime-library/sal-annotations.md)