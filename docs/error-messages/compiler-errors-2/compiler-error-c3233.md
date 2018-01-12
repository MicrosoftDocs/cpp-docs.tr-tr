---
title: "Derleyici Hatası C3233 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3233
dev_langs: C++
helpviewer_keywords: C3233
ms.assetid: a9210830-1136-4f02-ba41-030c85f93547
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c14ba944e90ff08a21098389d964fc240674455d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3233"></a>Derleyici Hatası C3233
'type': önceden kısıtlı genel tür parametresi  
  
 Birden çok genel bir parametre sınırlamak için geçerli değil `where` yan tümcesi.  
  
 Aşağıdaki örnek C3233 oluşturur:  
  
```  
// C3233.cpp  
// compile with: /clr /LD  
  
interface struct C {};  
interface struct D {};  
  
generic <class T>  
where T : C  
where T : D  
ref class E {};   // C3233  
```