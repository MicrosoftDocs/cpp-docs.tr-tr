---
title: "Derleyici Hatası C3451 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3451
dev_langs: C++
helpviewer_keywords: C3451
ms.assetid: a4897a69-e3e7-40bb-bb1c-598644904012
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c1c0f9de919fbe646eaa6303fa5b1e9fcba886eb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3451"></a>Derleyici Hatası C3451
'öznitelik': 'type ' yönetilmeyen özniteliğini uygulayamazsınız  
  
 C++ öznitelik CLR türüne uygulanamıyor. Bkz: [C++ öznitelikleri başvurusu](../../windows/cpp-attributes-reference.md) daha fazla bilgi için.  
  
 Daha fazla bilgi için bkz: [kullanıcı tanımlı öznitelikler](../../windows/user-defined-attributes-cpp-component-extensions.md).  
  
 Bu hata için Visual C++ 2005 yapıldığı derleyici uyumluluğu iş sonucunda oluşturulabilir: [UUID](../../windows/uuid-cpp-attributes.md) özniteliği artık CLR programlama kullanarak kullanıcı tanımlı bir öznitelikte izin verilir. Bunun yerine <xref:System.Runtime.InteropServices.GuidAttribute> kullanın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3451 oluşturur.  
  
```  
// C3451.cpp  
// compile with: /clr /c  
using namespace System;  
[ attribute(AttributeTargets::All) ]  
public ref struct MyAttr {};  
  
[ MyAttr, helpstring("test") ]   // C3451  
// try the following line instead  
// [ MyAttr ]  
public ref struct ABC {};  
```