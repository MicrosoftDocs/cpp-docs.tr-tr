---
title: "Derleyici Hatası C3197 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3197
dev_langs: C++
helpviewer_keywords: C3197
ms.assetid: 4e385c3b-222e-425c-9612-46e83ed41650
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 52c5287171cb162e66b39bb464ed7a464d571136
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3197"></a>Derleyici Hatası C3197
'anahtar sözcüğü': yalnızca tanımlarında kullanılabilir  
  
 Bir anahtar sözcüğü bir bildiriminde kullanıldı ancak yalnızca bir tanım geçerlidir.  
  
 Aşağıdaki örnek C3197 oluşturur:  
  
```  
// C3197.cpp  
// compile with: /clr /c  
ref struct R abstract;   // C3197  
ref struct R abstract {};   // OK  
  
public ref class MyObject;   // C3197  
ref class MyObject;   // OK  
public ref class MyObject {};   // OK  
```