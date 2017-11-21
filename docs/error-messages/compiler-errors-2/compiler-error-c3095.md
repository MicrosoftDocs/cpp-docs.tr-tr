---
title: "Derleyici Hatası C3095 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3095
dev_langs: C++
helpviewer_keywords: C3095
ms.assetid: cde725be-0936-40f6-9e57-e1d7d0710f83
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a47e7b6ee006bc7a490a01a825a29a265586b0aa
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3095"></a>Derleyici Hatası C3095
'öznitelik': öznitelik olamaz yinelenen  
  
 Hedef öznitelik birden çok tekrarı uygulanamaz şekilde bazı öznitelikler bildirilir.  
  
 Daha fazla bilgi için bkz: [kullanıcı tanımlı öznitelikler](../../windows/user-defined-attributes-cpp-component-extensions.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3095 oluşturur.  
  
```  
// C3095.cpp  
// compile with: /clr /c  
using namespace System;  
  
[AttributeUsage(AttributeTargets::All, AllowMultiple=false)]  
public ref class Attr : public Attribute {  
public:  
   Attr(int t) : m_t(t) {}  
   const int m_t;  
};  
  
[AttributeUsage(AttributeTargets::All, AllowMultiple=true)]  
public ref class Attr2 : public Attribute {  
public:  
   Attr2(int t) : m_t(t) {}  
   const int m_t;  
};  
  
[Attr(10)]   // C3095  
[Attr(11)]  
ref class A {};  
  
[Attr2(10)]   // OK  
[Attr2(11)]  
ref class B {};  
```