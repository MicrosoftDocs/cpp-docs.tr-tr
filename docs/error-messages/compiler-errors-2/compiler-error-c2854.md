---
title: Derleyici Hatası C2854 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2854
dev_langs:
- C++
helpviewer_keywords:
- C2854
ms.assetid: 917fec9c-790a-4149-8dfc-00d17a09199c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1555d36a9371145af2685ecd6650d7fdecc69660
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2854"></a>Derleyici Hatası C2854
#pragma hdrstop sözdizimi hatası  
  
 `#pragma hdrstop` Geçersiz bir dosya adı sağlar. Pragma parantezler ve tırnak işaretleri isteğe bağlı bir dosya adı tarafından izlenebilir:  
  
 Aşağıdaki örnek C2854 oluşturur:  
  
```  
// C2854.cpp  
// compile with: /c  
#pragma hdrstop( "\\source\\pchfiles\\myheader.pch" ]   // C2854  
// try the following line instead  
// #pragma hdrstop( "\\source\\pchfiles\\myheader.pch" )  
```