---
title: Derleyici Hatası C2434 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2434
dev_langs:
- C++
helpviewer_keywords:
- C2434
ms.assetid: 01329e26-7c74-4219-b74f-69e3a40c9738
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 543884392698a7a713dbc4c0bfd10dd19fcb0b1c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2434"></a>Derleyici Hatası C2434
'simgesi': / CLR ile __declspec(process) bildirilen bir simge dinamik olarak başlatılamaz: Saf modu  
  
 **/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı.  
  
 Dinamik olarak bir işlem içi değişken altında başlatmak mümkün değil **/CLR: pure**. Daha fazla bilgi için bkz: [/CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md) ve [işlem](../../cpp/process.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C2434 oluşturur.  
  
```  
// C2434.cpp  
// compile with: /clr:pure /c  
int f() { return 0; }  
__declspec(process) int i = f();   // C2434  
__declspec(process) int i2 = 0;   // OK  
```