---
title: "Derleyici Hatası C2441 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2441
dev_langs: C++
helpviewer_keywords: C2441
ms.assetid: ffbd6573-777a-48dd-892f-5cf4a758dcab
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 6868feadda4c0c0f3d65a86c77a403b8965fded5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2441"></a>Derleyici Hatası C2441
'değişkeni': __declspec(process) ile bildirilen bir simge const/CLR: pure modu  
  
 **/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı.  
  
 Varsayılan olarak, her uygulama etki alanı altında değişkenlerdir **/CLR: pure**. Bir değişken olarak işaretlenmiş `__declspec(process)` altında **/CLR: pure** değiştiren bir uygulama etki alanı ve başka bir programda okuma hataları yatkındır.  
  
 Bu nedenle, her işlem değişkenlerin olması derleyici zorlar `const` altında **/CLR: pure**, yalnızca tüm uygulama etki alanlarında yapma bunları okuyun.  
  
 Daha fazla bilgi için bkz: [işlem](../../cpp/process.md) ve [/CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C2441 oluşturur.  
  
```  
// C2441.cpp  
// compile with: /clr:pure /c  
__declspec(process) int i;   // C2441  
__declspec(process) const int j = 0;   // OK  
```