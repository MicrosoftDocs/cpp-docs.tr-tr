---
title: "Aşırı yüklenmiş işleçler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- operator overloading, in a CLR class
- operators [C++], overloading
ms.assetid: 30391426-afe7-4497-bf22-e4816c1e48c8
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 21d006aabc83af2021bb2b6d8bfa6a35588de12f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="overloaded-operators"></a>Aşırı Yüklenmiş İşleçler
İşleç aşırı yüklemesi önemli ölçüde Yönetilen Uzantılar'dan C++ için Visual C++'a değişmiştir.  
  
 Yerel kullanmak yerine örnek için bir başvuru türü bildiriminde `operator+` sözdizimi, açıkça yazdığınız - işleci temel iç adını bu durumda, `op_Addition`. Ayrıca, İşleç aşırı yüklemesi, iki adet birincil avantajı dolayısıyla çağrısı ile bu adını açıkça çağrılacak bir işleç çağırma sahiptir: (a) sezgisel sözdizimi ve varolan türleriyle yeni türleri intermix (b) yeteneği. Örneğin:  
  
```  
public __gc __sealed class Vector {  
public:  
   Vector( double x, double y, double z );  
  
   static bool    op_Equality( const Vector*, const Vector* );  
   static Vector* op_Division( const Vector*, double );  
   static Vector* op_Addition( const Vector*, const Vector* );  
   static Vector* op_Subtraction( const Vector*, const Vector* );  
};  
  
int main()  
{  
   Vector *pa = new Vector( 0.231, 2.4745, 0.023 );  
   Vector *pb = new Vector( 1.475, 4.8916, -1.23 );   
  
   Vector *pc1 = Vector::op_Addition( pa, pb );  
   Vector *pc2 = Vector::op_Subtraction( pa, pc1 );  
   Vector *pc3 = Vector::op_Division( pc1, pc2->x );  
  
   if ( Vector::op_Equality( pc1, pc2 ))  
      ;  
}  
```  
  
 Yeni sözdiziminde, yerel C++ Programcı olağan beklentileri, hem bildirim hem statik operatörlerin kullanımını de geri yüklenir. Burada `Vector` sınıfı yeni sözdizimine çevrilmiş:  
  
```  
public ref class Vector sealed {  
public:  
   Vector( double x, double y, double z );  
  
   static bool    operator ==( const Vector^, const Vector^ );  
   static Vector^ operator /( const Vector^, double );  
   static Vector^ operator +( const Vector^, const Vector^ );  
   static Vector^ operator -( const Vector^, const Vector^ );  
};  
  
int main()  
{  
   Vector^ pa = gcnew Vector( 0.231, 2.4745, 0.023 );  
   Vector^ pb = gcnew Vector( 1.475,4.8916,-1.23 );  
  
   Vector^ pc1 = pa + pb;  
   Vector^ pc2 = pa - pc1;  
   Vector^ pc3 = pc1 / pc2->x;  
  
   if ( pc1 == pc2 )  
      ;  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfta veya arabirimde üye bildirimleri (C + +/ CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)