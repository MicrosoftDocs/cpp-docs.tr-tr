---
title: "Derleyici Hatası C2292 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2292
dev_langs: C++
helpviewer_keywords: C2292
ms.assetid: 256b392f-2b8f-4162-b578-e7633984e162
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 64c44b5467b404d348324749d1d888f928256846
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2292"></a>Derleyici Hatası C2292
'tanımlayıcısı': devralma gösterimi'en iyi durumda: 'representation1 'representation2 gerekli' bildirilen'  
  
 Aşağıdaki kod ile derleme [/vmb](../../build/reference/vmb-vmg-representation-method.md) ("iyi her zaman" gösterimi) C2292 neden olur.  
  
```  
// C2292.cpp  
// compile with: /vmb  
class __single_inheritance X;  
  
struct A { };  
struct B { };  
struct X : A, B { };  // C2292, X uses multiple inheritance  
```