---
title: noreturn | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- noreturn_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++], noreturn
- noreturn __declspec keyword
ms.assetid: 9c6517e5-22d7-4051-9974-3d2200ae4d1d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 662ccef9f0acf1d73e8db51cc042c6f4d59d38bc
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39403394"
---
# <a name="noreturn"></a>noreturn
## <a name="microsoft-specific"></a>Microsoft'a Özgü  
 Bu **__declspec** öznitelik derleyiciye bir işlev değil döndürür. Sonuç olarak derleyici olduğunu bilir çağrıyı izleyen kodu bir **__declspec(noreturn)** işlevi erişilemez.  
  
 Derleyici bir işlevi değer döndürmeyen bir denetim yolu ile bulursa, (C4715) uyarısı veya hata iletisi (C2202) oluşturur. Hiçbir zaman döndüren bir işlev nedeniyle denetim yoluna ulaşılamıyorsa kullanabileceğiniz **__declspec(noreturn)** bu uyarı veya hatayı önlemek için.  
  
> [!NOTE]
>  Ekleme **__declspec(noreturn)** dönmesi beklenen bir işleve tanımsız davranışlara neden olabilir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte, **başka** yan tümcesi bir dönüş deyimi içermez.  Bildirme `fatal` olarak **__declspec(noreturn)** bir hata veya uyarı iletisi önler.  
  
```cpp 
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
  
## <a name="see-also"></a>Ayrıca bkz.  
 [__declspec](../cpp/declspec.md)   
 [Anahtar Sözcükler](../cpp/keywords-cpp.md)