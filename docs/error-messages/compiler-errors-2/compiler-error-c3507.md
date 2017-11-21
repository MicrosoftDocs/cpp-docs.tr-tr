---
title: "Derleyici Hatası C3507 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3507
dev_langs: C++
helpviewer_keywords: C3507
ms.assetid: 75f89767-f6f9-40f6-9820-81a49e09abdf
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 697732f9e9c37735db591fc5a90d2380806fb7eb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3507"></a>Derleyici Hatası C3507
bir ProgID en fazla 39 'ID'; karakter uzunluğunda olabilir ya da apart gelen tüm noktalama işaretlerini içeren '.'; veya bir rakamla Başlat  
  
 [ProgID](../../windows/progid.md) özniteliği devam edebilir değerlerine kısıtlamaları vardır.  
  
 Aşağıdaki örnek C3507 oluşturur:  
  
```  
// C3507.cpp  
[module(name="x")];  
[  
coclass,  
progid("0123456789012345678901234567890123456789"),  
uuid("00000000-0000-0000-0000-000000000001") // C3507 expected  
]  
struct CMyStruct {  
};  
int main() {  
}  
```