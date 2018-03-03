---
title: "Derleyici Hatası C3744 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3744
dev_langs:
- C++
helpviewer_keywords:
- C3744
ms.assetid: a447d050-80d1-406a-9a6e-f15c527d717c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fd5c11e88960f2b4332a586d2fe982a8ea94fdbd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3744"></a>Derleyici Hatası C3744
__unhook yönetilen olayları için en az 3 tane bağımsız değişkene sahip olmalıdır  
  
 [__Unhook](../../cpp/unhook.md) işlevi C++ için Yönetilen Uzantılar için derlenmiş bir program kullanıldığında üç parametre almalıdır.  
  
 `__hook`ve  `__unhook` /CLR programlama ile uyumlu değil. += Ve-= işleç kullanın.  
  
 C3744 eski derleyici seçeneği kullanılarak erişilebilir, yalnızca **/clr:oldSyntax**.  
