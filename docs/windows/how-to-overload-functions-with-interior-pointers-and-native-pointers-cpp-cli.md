---
title: "Nasıl yapılır: iç işaretçiler ve yerel işaretçilerle işlevleri tekrar yükleme (C + +/ CLI) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords: Functions with interior and native pointers, overloading
ms.assetid: d70df625-4aad-457c-84f5-70a0a290cc1f
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f5f46abca993acb2990c3310e8fefd9ab970b751
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-overload-functions-with-interior-pointers-and-native-pointers-ccli"></a>Nasıl yapılır: İç İşaretçiler ve Yerel İşaretçilerle İşlevleri Tekrar Yükleme (C++/CLI)
Parametre türü iç işaretçi veya yerel bir işaretçi olmasına bağlı olarak işlevleri aşırı yüklenmiş.  
  
> [!IMPORTANT]
>  Bu dil özelliği tarafından desteklenen **/CLR** derleyici seçeneği, ancak tarafından **/ZW** derleyici seçeneği.  
  
## <a name="example"></a>Örnek  
  
### <a name="code"></a>Kod  
  
```  
// interior_ptr_overload.cpp  
// compile with: /clr  
using namespace System;  
  
// C++ class  
struct S {  
   int i;  
};  
  
// managed class  
ref struct G {  
   int i;  
};  
  
// can update unmanaged storage  
void f( int* pi ) {  
   *pi = 10;  
   Console::WriteLine("in f( int* pi )");  
}  
  
// can update managed storage  
void f( interior_ptr<int> pi ) {  
   *pi = 10;   
   Console::WriteLine("in f( interior_ptr<int> pi )");  
}  
  
int main() {  
   S *pS = new S;   // C++ heap  
   G ^pG = gcnew G;   // common language runtime heap  
   f( &pS->i );  
   f( &pG->i );  
};  
```  
  
### <a name="output"></a>Çıkış  
  
```  
in f( int* pi )  
in f( interior_ptr<int> pi )  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [interior_ptr (C++/CLI)](../windows/interior-ptr-cpp-cli.md)