---
title: Derleyici Hatası C2262 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2262
dev_langs:
- C++
helpviewer_keywords:
- C2262
ms.assetid: 727d1c6e-53e8-40e5-b7b8-6a7ac2011727
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 199c5d109cf994a8f69e29f893cd13dd7028ca82
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2262"></a>Derleyici Hatası C2262
'attribute_specifiers': InternalsVisibleTo bildirimlerinde belirtilen sürüm, kültür veya işlemci mimarisi sahip olamaz  
  
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> Özniteliği düzgün belirtilmedi.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C2262 oluşturur.  
  
```  
// C2262.cpp  
// compile with: /clr /c  
using namespace System::Runtime::CompilerServices;  
[assembly: InternalsVisibleTo("assembly_name, version=1.2.3.7")];   // C2262  
[assembly: InternalsVisibleTo("assembly_name ")];   // OK  
```