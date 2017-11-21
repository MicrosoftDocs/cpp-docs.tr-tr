---
title: "Derleyici Hatası C2971 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2971
dev_langs: C++
helpviewer_keywords: C2971
ms.assetid: fdb5467b-9a41-41ef-ac20-2e9428d5a4fc
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 81194765278adc82d57a7a95cc8528f1fd6e1ef3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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