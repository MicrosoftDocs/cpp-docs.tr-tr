---
title: "Derleyici Hatası C2433 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2433
dev_langs: C++
helpviewer_keywords: C2433
ms.assetid: 7079fedd-6059-4125-82ef-ebe275f1f9d1
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c5994da7e2e2dff73f7746dd0fdb2b7a20395cce
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2433"></a>Derleyici Hatası C2433
'tanımlayıcısı': 'değiştiricisi veri bildirimlerine izin verilmeyen'  
  
 `friend`, `virtual`, Ve `inline` değiştiricileri veri bildirimleri için kullanılamaz.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C2433 oluşturur.  
  
```  
// C2433.cpp  
class C{};  
  
int main() {  
   inline C c;   // C2433  
}  
```