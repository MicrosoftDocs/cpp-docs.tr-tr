---
title: "Derleyici Hatası C2375 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2375
dev_langs: C++
helpviewer_keywords: C2375
ms.assetid: 193c5e8b-1b20-4928-8a02-8c1cddaf2a26
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 57fa2e73e9f25fb226ef52971cb933e2fec5e3f6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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