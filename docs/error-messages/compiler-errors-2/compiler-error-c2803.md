---
title: "Derleyici Hatası C2803 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2803
dev_langs: C++
helpviewer_keywords: C2803
ms.assetid: 2cdbe374-8cc4-4c4e-ba15-062a7479e937
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2472c0e1182ad11f5ea95e3411649e6214b110ab
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2803"></a>Derleyici Hatası C2803
sınıf türü en az bir biçimsel parametresi 'işleci işleci' olmalıdır  
  
 Aşırı yüklenmiş işleci sınıfı türünde bir parametre eksik.  
  
 En az bir parametre yazabilmesi için değer veya başvuru (işaretçileri ancak başvurular kullanarak değil) tarafından geçirmenize gerek "bir < b" (bir ve türü sınıf A b verilen).  
  
 Her iki parametre işaretçileri varsa işaretçi adresleri saf karşılaştırması olacak ve kullanıcı tanımlı dönüştürme kullanmaz.  
  
 Aşağıdaki örnek C2803 oluşturur:  
  
```  
// C2803.cpp  
// compile with: /c  
class A{};  
bool operator< (const A *left, const A *right);   // C2803  
// try the following line instead  
// bool operator< (const A& left, const A& right);  
```