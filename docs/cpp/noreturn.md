---
title: noreturn | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: noreturn_cpp
dev_langs: C++
helpviewer_keywords:
- __declspec keyword [C++], noreturn
- noreturn __declspec keyword
ms.assetid: 9c6517e5-22d7-4051-9974-3d2200ae4d1d
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 91c6a7b38653a3bb0a86927ced602fd85ff29277
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="noreturn"></a>noreturn
## <a name="microsoft-specific"></a>Microsoft'a Özgü  
 Bu `__declspec` özniteliği bir işlevin dönmeyeceğini derleyiciye bildirir. Sonuç olarak, derleyici, bilir yapılan bir çağrı aşağıdaki kod bir **__declspec(noreturn)** işlevidir erişilemiyor.  
  
 Derleyici bir işlevi değer döndürmeyen bir denetim yolu ile bulursa, (C4715) uyarısı veya hata iletisi (C2202) oluşturur. Denetim yolu hiçbir zaman döndüren bir işlev nedeniyle ulaşılamıyorsa kullanabileceğiniz **__declspec(noreturn)** bu uyarı veya hata önlemek için.  
  
> [!NOTE]
>  Ekleme **__declspec(noreturn)** dönmek için beklenen bir işleve tanımlanmamış davranışlara neden olabilir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte, **başka** yan tümcesi bir dönüş ifadesi içermiyor.  Bildirme `fatal` olarak **__declspec(noreturn)** bir hata veya uyarı iletisi önler.  
  
```  
// noreturn2.cpp  
__declspec(noreturn) extern void fatal () {}  
  
int main() {  
   if(1)  
     return 1;  
   else if(0)  
     return 0;  
   else  
     fatal();  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [__declspec](../cpp/declspec.md)   
 [Anahtar sözcükler](../cpp/keywords-cpp.md)