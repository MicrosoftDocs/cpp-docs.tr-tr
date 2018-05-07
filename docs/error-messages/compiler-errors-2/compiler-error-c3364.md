---
title: Derleyici Hatası C3364 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3364
dev_langs:
- C++
helpviewer_keywords:
- C3364
ms.assetid: 98654741-60fe-4472-a6af-e580f8c0a6e1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 337bcf71e89dc1ff3e434eba6645f76df1022a11
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3364"></a>Derleyici Hatası C3364
'temsilci': temsilci Oluşturucu: yönetilen sınıfının üye işlevini veya genel işlev işaretçisi bağımsız değişkeni olmalıdır.  
  
 Öğesinin ikinci parametresi, temsilcinin Oluşturucusu üye işlevi adresini veya herhangi bir sınıfın statik üye işlevinin adresini alır. Her ikisi de basit adresleri olarak kabul edilir.  
  
 Aşağıdaki örnek C3364 oluşturur:  
  
```  
// C3364_2.cpp  
// compile with: /clr  
  
delegate int D( int, int );  
  
ref class C {  
public:  
   int mf( int, int ) {  
      return 1;  
   }  
};  
  
int main() {  
   C^ pC = gcnew C;  
   System::Delegate^ pD = gcnew D( pC,pC->mf( 1, 2 ) ); // C3364  
  
   // try the following line instead  
   // System::Delegate^ pD = gcnew D(pC, &C::mf);  
}  
```  
