---
title: Derleyici Hatası C2601 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2601
dev_langs:
- C++
helpviewer_keywords:
- C2601
ms.assetid: 88275582-5f37-45d7-807d-05f06ba00965
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 49598223c3f68271065cc6212da19767020c51e9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33230831"
---
# <a name="compiler-error-c2601"></a>Derleyici Hatası C2601
'function': yerel işlev tanımları geçersiz  
  
 Bir işlevin içindeki bir işlev tanımlamak kod çalışır.  
  
 Ya da kaynak kodunuzda C2601 hata konumunu önce ek bir küme parantezi olabilir.  
  
 Aşağıdaki örnek C2601 oluşturur:  
  
```  
// C2601.cpp  
int main() {  
   int i = 0;  
  
   void funcname(int j) {   // C2601  
      j++;  
   }  
}  
```