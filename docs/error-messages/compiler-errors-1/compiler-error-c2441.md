---
title: Derleyici Hatası C2441 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2441
dev_langs:
- C++
helpviewer_keywords:
- C2441
ms.assetid: ffbd6573-777a-48dd-892f-5cf4a758dcab
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6557e913f2bd34fda9d435d44020697a925af4e4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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