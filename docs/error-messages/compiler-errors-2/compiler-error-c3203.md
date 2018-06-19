---
title: Derleyici Hatası C3203 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3203
dev_langs:
- C++
helpviewer_keywords:
- C3203
ms.assetid: 6356770e-22c1-434c-91fe-f60b0aa23b91
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 81548f5fc8fc4a28a4ad85e4611eba9440d6f107
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33251130"
---
# <a name="compiler-error-c3203"></a>Derleyici Hatası C3203
'type': unspecialized sınıf şablonu veya genel bir şablon veya şablon veya genel parametre 'param' için genel bir bağımsız değişken olarak kullanılamaz, gerçek tür bekleniyor  
  
 Sınıf şablonu veya genel geçersiz bağımsız değişken geçirildi. Sınıf şablonu veya genel bir türü bir parametre bekler.  
  
 Bu hata için Visual C++ 2005 yapıldığı derleyici uyumluluğu iş sonucunda oluşturulabilir: unspecialized sınıf şablonu bir temel sınıf listesinde şablon bağımsız değişken olarak kullanılamaz. C3203 gidermek için açıkça şablon türü parametreleri şablon sınıf adı için bir temel sınıf listesi bir şablon parametresi olarak kullanırken ekleyin.  
  
```  
// C3203.cpp  
template< typename T >  
struct X {  
   void f(X) {}  
};  
  
template< typename T >  
struct Y : public X<Y> {   // C3203  
// try the following line instead  
// struct Y : public X<Y<T> > {  
   void f(Y) {}  
};  
  
int main() {  
   Y<int> y;  
}  
```  
  
 Aşağıdaki örnek C3203 oluşturur ve düzeltmek gösterilmektedir:  
  
```  
// C3203_b.cpp  
// compile with: /c  
template <class T>  
struct S1 {};  
  
template <class T>  
class C1 {};  
  
typedef C1<S1> MyC1;   // C3203  
  
// OK  
template <template <class> class T>  
class C2 {};  
  
typedef C2<S1> MyC1;  
  
template <class T>  
class C3 {};  
  
typedef C3<S1<int> > MyC12;  
```  
  
 Ayrıca C3203 genel türler kullanma ortaya çıkabilir:  
  
```  
// C3203_c.cpp  
// compile with: /clr /c  
generic <class T>  
value struct GS1 {};  
  
generic <class T>  
value struct GC1 {};  
  
typedef GC1<GS1> MyGC1;   // C3203  
typedef GC1<GS1<int> > MyGC2;   // OK  
```