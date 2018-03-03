---
title: "Derleyici Hatası C2441 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2441
dev_langs:
- C++
helpviewer_keywords:
- C2441
ms.assetid: ffbd6573-777a-48dd-892f-5cf4a758dcab
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 645e06a0685f00359d468a4a4b9bd3522921b511
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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