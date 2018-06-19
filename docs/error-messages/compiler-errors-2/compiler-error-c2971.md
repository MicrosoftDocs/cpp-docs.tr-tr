---
title: Derleyici Hatası C2971 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2971
dev_langs:
- C++
helpviewer_keywords:
- C2971
ms.assetid: fdb5467b-9a41-41ef-ac20-2e9428d5a4fc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fd46be67a2ce8e7f3a8ab1319c7a16a465797474
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33241555"
---
# <a name="compiler-error-c2971"></a>Derleyici Hatası C2971
'class': 'param' şablon parametresi: 'arg': yerel bir değişken türü olmayan bağımsız değişken olarak kullanılamaz  
  
 Şablon bağımsız değişken adını veya adresini yerel değişken kullanamazsınız.  
  
 Aşağıdaki örnek C2971 oluşturur:  
  
```  
// C2971.cpp  
template <int *pi>   
class Y {};  
  
int global_var = 0;  
  
int main() {  
   int local_var = 0;  
   Y<&local_var> aY;   // C2971  
   // try the following line instead  
   // Y<&global_var> aY;  
}  
```