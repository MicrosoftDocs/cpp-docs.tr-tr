---
title: "Derleyici Hatası C3347 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3347
dev_langs: C++
helpviewer_keywords: C3347
ms.assetid: e939ad29-0b78-4681-9618-9bdae5675cee
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 75d81462324690ae126938ffeab5a8eea9334426
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3347"></a>Derleyici Hatası C3347
'arg': bağımsız değişkeni idl_module özniteliği belirtilmezse gerekli  
  
 Gerekli bir bağımsız değişken geçirilmedi [idl_module](../../windows/idl-module.md) özniteliği.  
  
 Aşağıdaki örnek C3347 oluşturur:  
  
```  
// C3347.cpp  
// compile with: /c  
[module(name="xx")];  
  
[idl_module(dllname="x")];    // C3347  
// try the following line instead  
// [idl_module(name="test", dllname="x")];  
```