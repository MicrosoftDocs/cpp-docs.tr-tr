---
title: void (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: void_cpp
dev_langs: C++
helpviewer_keywords:
- void keyword [C++]
- functions [C++], void
- pointers, void
ms.assetid: d203edba-38e6-4056-8b89-011437351057
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5ec762d15c878df4bcde01284f1b10783bff7e3c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="void-c"></a>void (C++)
Bir işlev dönüş türü olarak kullanıldığında `void` anahtar sözcüğü işlevin bir değer döndürmediğini belirtir. İşlevin parametre listesi için kullanıldığında, void işlevin parametre almadığını belirtir. Bir işaretçinin bildiriminde kullanıldığında, void işaretçinin "evrensel" olduğunu belirtir.  
  
 Bir işaretçinin türü ise **void \*** , işaretçi ile bildirilmemiş herhangi bir değişken götürebilir **const** veya `volatile` anahtar sözcüğü. Başka bir türe atanmadığı sürece bir void işaretçisine tekrar başvurulamaz. Void bir işaretçi başka türde veri işaretçisine dönüştürülebilir.  
  
 Void bir işaretçi, bir işlevi gösterebilir ancak C++'ta bir sınıf üyesini gösteremez.  
  
 Void türünün değişkeninin bildirimini yapamazsınız.  
  
## <a name="example"></a>Örnek  
  
```  
// void.cpp  
void vobject;   // C2182  
void *pv;   // okay  
int *pint; int i;  
int main() {  
   pv = &i;  
   // Cast optional in C required in C++  
   pint = (int *)pv;  
}   
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Anahtar sözcükler](../cpp/keywords-cpp.md)   
 [Temel türler](../cpp/fundamental-types-cpp.md)