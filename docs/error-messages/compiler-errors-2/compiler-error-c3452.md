---
title: "Derleyici Hatası C3452 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3452
dev_langs: C++
helpviewer_keywords: C3452
ms.assetid: e5293dcf-cb70-4133-ae2a-0bb496950ba0
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3991b7d95233941bd63191f1d64a6c6d818a27d7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3452"></a>Derleyici Hatası C3452
Liste bağımsız değişkeni üyesi olmayan sabit  
  
 Bir sabit derleme zamanında sonucu verebilen bir değer beklenen bir öznitelik için bir bağımsız değişken geçirildi.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3452 oluşturur.  
  
```  
// C3452.cpp  
// compile with: /c  
int i;  
[module( name="mod", type=dll, custom={i} ) ];   // C3452  
// try the following line instead  
// [module( name="mod", type=dll, custom={"a"} ) ];  
```