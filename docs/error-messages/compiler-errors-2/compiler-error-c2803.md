---
title: Derleyici Hatası C2803 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2803
dev_langs:
- C++
helpviewer_keywords:
- C2803
ms.assetid: 2cdbe374-8cc4-4c4e-ba15-062a7479e937
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 51cf2a8b38a86fcd97ab693b3853fe25527a0bb3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33236229"
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