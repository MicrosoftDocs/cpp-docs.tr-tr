---
title: "Derleyici Hatası C3219 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3219
dev_langs: C++
helpviewer_keywords: C3219
ms.assetid: 9c9757b0-1256-4cdf-9d8c-a3a72f300ce5
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 33816ce0cdc079d3531e72d777a4ac7c082025ed
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3219"></a>Derleyici Hatası C3219
'param': genel parametresi birden çok olmayan-arabirimleri tarafından kısıtlanamaz: 'sınıfı'  
  
 İki veya daha fazla yönetilen sınıfları tarafından genel bir parametreye sınırlamak için geçerli değil.  
  
 Aşağıdaki örnek C3219 oluşturur:  
  
```  
// C3219.cpp  
// compile with: /clr  
ref class A {};  
ref class B {};  
  
generic <class T>  
where T : A, B  
ref class E {};   // C3219  
```  
  
 Aşağıdaki örnek, olası bir çözüm gösterilmektedir:  
  
```  
// C3219b.cpp  
// compile with: /clr /c  
ref class A {};  
  
interface struct C {};  
  
generic <class T>  
where T : A  
ref class E {};  
```