---
title: Derleyici Hatası C2375 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2375
dev_langs:
- C++
helpviewer_keywords:
- C2375
ms.assetid: 193c5e8b-1b20-4928-8a02-8c1cddaf2a26
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6b0d6d3ecda2bd996e7ef53ff5fd0eed6290e2b0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33195470"
---
# <a name="compiler-error-c2375"></a>Derleyici Hatası C2375
'function': şemadaki; farklı bağlantı  
  
 İşlevi ile farklı bağlantı tanımlayıcısı zaten bildirildi.  
  
 Aşağıdaki örnek C2375 oluşturur:  
  
```  
// C2375.cpp  
// compile with: /Za /c  
extern void func( void );  
static void func( void );   // C2375  
static void func2( void );   // OK  
```