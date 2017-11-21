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
ms.openlocfilehash: c95f18c959ce2c3dbd8f76e0f2fbf1130b92ceb4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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