---
title: "Derleyici Hatası C2854 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2854
dev_langs: C++
helpviewer_keywords: C2854
ms.assetid: 917fec9c-790a-4149-8dfc-00d17a09199c
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0f8423af7be34d431ab8ace8ca512d857611c6c3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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