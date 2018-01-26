---
title: "özellik (C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: property_cpp
dev_langs: C++
helpviewer_keywords:
- property __declspec keyword
- __declspec keyword [C++], property
ms.assetid: f3b850ba-bf48-4df7-a1d6-8259d97309ce
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 313123a75c2fbcf295d1c1d87aa423e76154091e
ms.sourcegitcommit: 9a0a287d6940591523af959ebdac5affa36220da
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/25/2018
---
# <a name="property-c"></a>property (C++)
**Microsoft Specific**  
  
 Bu öznitelik, bir sınıf veya yapı tanımında statik olmayan için "sanal veri üyeleri" uygulanabilir. Derleyici işlev çağrılarını başvurularını değiştirerek bu "sanal veri üyeleri" veri üye olarak değerlendirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
   __declspec( property( get=get_func_name ) ) declarator  
   __declspec( property( put=put_func_name ) ) declarator  
   __declspec( property( get=get_func_name, put=put_func_name ) ) declarator  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu öznitelik ile üye seçimi işlecinin sağ tarafta bildirilen bir veri üyesi gördüğünde derleyici ("**.**"veya"**->**"), işlemi dönüştürür bir **Al** veya **put** bu tür bir ifade l-değeri ya da bir r olup olmamasına bağlı olarak işlevi. Daha fazla kapsamları gibi karmaşık "`+=`", bir yeniden yazma hem de yaparak gerçekleştirilir **almak** ve **put**.  
  
 Bu öznitelik, bir sınıf veya yapı tanımı içinde boş bir dizi bildiriminde de kullanılabilir. Örneğin:  
  
```  
__declspec(property(get=GetX, put=PutX)) int x[];  
```  
  
 Yukarıdaki ifadeyi belirten `x[]` bir veya daha fazla dizi dizinlerini ile kullanılabilir. Bu durumda, `i=p->x[a][b]` içine açık `i=p->GetX(a, b)`, ve `p->x[a][b] = i` içine açık`p->PutX(a, b, i);`  
  
 **SON Microsoft özel**  
  
## <a name="example"></a>Örnek  
  
```  
// declspec_property.cpp  
struct S {  
   int i;  
   void putprop(int j) {   
      i = j;  
   }  
  
   int getprop() {  
      return i;  
   }  
  
   __declspec(property(get = getprop, put = putprop)) int the_prop;  
};  
  
int main() {  
   S s;  
   s.the_prop = 5;  
   return s.the_prop;  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [__declspec](../cpp/declspec.md)   
 [Anahtar Sözcükler](../cpp/keywords-cpp.md)