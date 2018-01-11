---
title: "Derleyici Hatası C3034 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3034
dev_langs: C++
helpviewer_keywords: C3034
ms.assetid: 49db8bac-2720-4622-94e3-7988f1603fa3
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0c81810493b332bc9066ed29df114ff7b8a53cfc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3034"></a>Derleyici Hatası C3034
OpenMP 'directive1' yönergesi doğrudan 'directive2' yönergesi içinde iç içe olamaz  
  
 Bazı yönergeleri iç içe olamaz. Bu hatayı düzeltmek için her iki yönergeleri deyimleri bir yönergesi bloğu içine birleştirebilirsiniz veya ardışık yönergeleri oluşturabileceğiniz.  
  
 Aşağıdaki örnek C3034 oluşturur:  
  
```  
// C3034.cpp  
// compile with: /openmp /link vcomps.lib  
int main() {  
  
   #pragma omp single  
   {  
      #pragma omp single   // C3034   
      {  
      ;  
      }  
   }  
  
   // Two consecutive single clauses are OK.  
   #pragma omp single  
   {  
   }  
  
   #pragma omp single  
   {  
   }  
}  
```