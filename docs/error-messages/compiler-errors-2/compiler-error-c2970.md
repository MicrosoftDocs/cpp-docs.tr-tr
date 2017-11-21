---
title: "Derleyici Hatası C2970 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2970
dev_langs: C++
helpviewer_keywords: C2970
ms.assetid: 21d90348-20d3-438c-b278-efdbfb93a7d2
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: fc125b400a718805af2ee0829100c056fffa29a3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2970"></a>Derleyici Hatası C2970
'class': 'param' şablon parametresi: 'arg': iç bağlantı nesneleri içeren bir ifade türü olmayan bağımsız değişken olarak kullanılamaz  
  
 Adı veya adresi statik bir değişkenin bir şablon bağımsız değişken olarak kullanamazsınız. Şablon sınıfı derleme zamanında değerlendirilebilir sabit bir değere bekliyor.  
  
 Aşağıdaki örnek C2970 oluşturur:  
  
```  
// C2970.cpp  
// compile with: /c  
static int si;  
// could declare nonstatic to resolve all errors  
// int si;  
  
template <int i>   
class X {};  
  
template <int *pi>   
class Y {};  
  
X<si> anX;   // C2970 cannot use static variable in templates  
  
// this would also work  
const int i = 10;  
X<i> anX2;  
```