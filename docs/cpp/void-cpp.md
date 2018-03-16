---
title: void (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- void_cpp
dev_langs:
- C++
helpviewer_keywords:
- void keyword [C++]
- functions [C++], void
- pointers, void
ms.assetid: d203edba-38e6-4056-8b89-011437351057
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a800aca290a178e3b193c245df515385311b5593
ms.sourcegitcommit: 9239c52c05e5cd19b6a72005372179587a47a8e4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2018
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
 [Temel Türler](../cpp/fundamental-types-cpp.md)