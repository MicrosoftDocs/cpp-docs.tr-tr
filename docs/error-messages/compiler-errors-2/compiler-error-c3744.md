---
title: Derleyici Hatası C3744 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3744
dev_langs:
- C++
helpviewer_keywords:
- C3744
ms.assetid: a447d050-80d1-406a-9a6e-f15c527d717c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f96b8445c343bdd4f606157e692c4d6ce262e369
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33265889"
---
# <a name="compiler-error-c3744"></a>Derleyici Hatası C3744
__unhook yönetilen olayları için en az 3 tane bağımsız değişkene sahip olmalıdır  
  
 [__Unhook](../../cpp/unhook.md) işlevi C++ için Yönetilen Uzantılar için derlenmiş bir program kullanıldığında üç parametre almalıdır.  
  
 `__hook` ve  `__unhook` /CLR programlama ile uyumlu değil. += Ve-= işleç kullanın.  
  
 C3744 eski derleyici seçeneği kullanılarak erişilebilir, yalnızca **/clr:oldSyntax**.  
