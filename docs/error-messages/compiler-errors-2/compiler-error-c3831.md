---
title: "Derleyici Hatası C3831 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3831
dev_langs: C++
helpviewer_keywords: C3831
ms.assetid: a125d8dc-b75a-4ea0-b6c7-fe7b119dba25
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 27b330e82c952bd02de7499e8dffe548acfe819c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3831"></a>Derleyici Hatası C3831
'member': 'sınıfı' sabitlenmiş veri üyesi veya bir sabitleme işaretçisi döndüren bir üye işlevi olamaz  
  
 [pin_ptr (C + +/ CLI)](../../windows/pin-ptr-cpp-cli.md) yanlış kullanıldı.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3831 oluşturur:  
  
```  
// C3831a.cpp  
// compile with: /clr  
ref class Y  
{  
public:  
   int i;  
};  
  
ref class X  
{  
   pin_ptr<int> mbr_Y;   // C3831  
   int^ mbr_Y2;   // OK  
};  
  
int main() {  
   Y y;  
   pin_ptr<int> p = &y.i;  
}  
```  
