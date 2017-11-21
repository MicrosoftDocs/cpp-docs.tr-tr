---
title: nothrow (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: nothrow_cpp
dev_langs: C++
helpviewer_keywords:
- __declspec keyword [C++], nothrow
- nothrow __declspec keyword
ms.assetid: 0a475139-459c-4ec6-99e8-7ecd0d7f44a3
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 82370900fc96c97665cb35351605db86c9ff4faf
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="nothrow-c"></a>nothrow (C++)
**Microsoft özel**  
  
 İşlevlerin bildiriminde kullanılabilen `__declspec` genişletilmiş özniteliği.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
return-type __declspec(nothrow) [call-convention] function-name ([argument-list])  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu öznitelik, derleyiciye bildirilen işlevlerin ve çağırdığı işlevlerin hiçbir zaman özel durum oluşturmayacağını bildirir. Artık varsayılan olarak zaman uyumlu özel durum işleme modeliyle, derleyici böyle bir işlevde geriye doğru izlenemeyen nesnelerin kullanım süresini izleme mekaniklerini ortadan kaldırabilir ve kod boyutunu önemli ölçüde azaltabilir. Aşağıdaki önişlemci yönergesi dikkate alındığında, aşağıdaki üç işlev bildirimi eşdeğerdir:  
  
```  
#define WINAPI __declspec(nothrow) __stdcall   
  
void WINAPI f1();  
void __declspec(nothrow) __stdcall f2();  
void __stdcall f3() throw();  
```  
  
 `void __declspec(nothrow) __stdcall f2();` kullanımı, bir işlevler kümesinde kolayca `#define` belirtmek için `nothrow` deyimi tarafından gösterilen gibi bir API tanımı kullanabilmenizi sağlar. Üçüncü `, void __stdcall f3() throw();` bildirimi, C++ standardı tarafından tanımlanan sözdizimidir.  
  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [__declspec](../cpp/declspec.md)   
 [Anahtar sözcükler](../cpp/keywords-cpp.md)