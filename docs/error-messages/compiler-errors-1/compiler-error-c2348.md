---
title: "Derleyici Hatası C2348 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2348
dev_langs: C++
helpviewer_keywords: C2348
ms.assetid: 4c4d701f-ccf1-46fe-9ddb-3f341684f269
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1a9c2d6f00a99f3d56c998ac8c98e330099e4d4a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2348"></a>Derleyici Hatası C2348
'tür adı': C-style Toplama ifadesi değil, katıştırılmış-IDL dışarı aktarılamaz  
  
 Yerleştirmek için bir `struct` ile .idl dosyasında [verme](../../windows/export.md) özniteliği `struct` yalnızca verileri içermesi gerekir.  
  
 Aşağıdaki örnek C2348 oluşturur:  
  
```  
// C2348.cpp  
// C2348 error expected  
[ module(name="SimpleMidlTest") ];  
  
[export]  
struct Point {  
   // Delete the following two lines to resolve.  
   Point() : m_i(0), m_j(0) {}  
   Point(int i, int j) : m_i(i), m_j(j) {}  
  
   int m_i;  
   int m_j;  
};  
```