---
title: Tek devralma | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- single inheritance
- base classes [C++], indirect
- scope, scope resolution operator
- operators [C++], scope resolution
- scope resolution operator
- derived classes [C++], single base class
- inheritance, single
ms.assetid: 1cb946ed-8b1b-4cf1-bde0-d9cecbfdc622
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c896b9ae68aad6e537655f03585f2261203099e5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="single-inheritance"></a>Tek Devralma
Sık kullanılan bir devralma biçimi olan "tek devralma"da, sınıflarda yalnızca bir temel sınıfı vardır. Aşağıdaki şekilde gösterilen ilişkiyi göz önünde bulundurun.  
  
 ![Temel tek &#45; Devralma Grafiği](../cpp/media/vc38xj1.gif "vc38XJ1")  
Basit Tek Devralma Grafiği  
  
 Şekildeki ilerlemenin genelden özele olduğuna dikkat edin. Çoğu sınıf hiyerarşisinin tasarımında bulunan diğer bir genel öznitelik ise türetilen sınıfın temel sınıf ile bir "türü" ilişkisi olmasıdır. Şekilde, `Book` bir `PrintedDocument` türü, `PaperbackBook` ise bir `book` türüdür.  
  
 Şekildeki notun diğer bir öğesi: `Book` hem türetilen bir sınıf (`PrintedDocument` öğesinden) hem de temel bir sınıftır (`PaperbackBook`, `Book` öğesinden türetilir). Böyle bir sınıf hiyerarşisi olan iskelet bildirimi aşağıdaki örnekte gösterilmiştir:  
  
```  
// deriv_SingleInheritance.cpp  
// compile with: /LD  
class PrintedDocument {};  
  
// Book is derived from PrintedDocument.  
class Book : public PrintedDocument {};  
  
// PaperbackBook is derived from Book.  
class PaperbackBook : public Book {};  
```  
  
 `PrintedDocument`, `Book` için "doğrudan temel" sınıfı olarak kabul edilir; `PaperbackBook` için ise "dolaylı temel" sınıfıdır. Aralarındaki fark, doğrudan temel sınıfının, sınıf bildiriminin temel listesinde görünmesi, dolaylı sınıfın ise görünmemesidir.  
  
 Her sınıfın türetildiği temel sınıf, türetilen sınıfın bildiriminden önce bildirilir. Temel sınıf için ileri başvuran bir bildirim sağlamak yeterli değildir; tam bir bildirim olması gerekir.  
  
 Önceki örnekte, bir erişim belirticisi **ortak** kullanılır. Genel, korumalı ve özel devralma anlamını açıklanan [üye erişim denetimi.](../cpp/member-access-control-cpp.md)  
  
 Bir sınıf, aşağıdaki şekilde gösterildiği gibi birçok özel sınıf için temel sınıf olarak kullanılabilir.  
  
 ![Yönlendirilmiş Çevrimsiz grafik](../cpp/media/vc38xj2.gif "vc38XJ2")  
Yönlendirilmiş Çevrimsiz Grafik Örneği  
  
 Yukarıda gösterilen "yönlendirilmiş çevrimsiz graf" (veya "DAG") adlı diyagramda, sınıfların bazıları birden fazla türetilmiş sınıfa yönelik temel sınıflardır. Ancak bunun tersi doğru değildir: türetilmiş herhangi bir sınıfa yönelik yalnızca bir doğrudan temel sınıf vardır. Şekildeki grafikte "tek devralma" yapısı gösterilmiştir.  
  
> [!NOTE]
>  Yönlendirilmiş çevrimsiz grafikler, tek devralmaya özgü değildir. Birden çok devralma grafiklerini göstermek için de kullanılırlar. Bu konu içinde ele [birden çok devralma](http://msdn.microsoft.com/en-us/3b74185e-2beb-4e29-8684-441e51d2a2ca).  
  
 Devralma işleminde, türetilen sınıf temel sınıfın üyelerini ve eklediğiniz tüm yeni üyeleri içerir. Sonuç olarak, türetilen bir sınıf temel sınıfın üyelerine başvurabilir (bu üyeler türetilen sınıfta yeniden tanımlanmadıkça). Kapsam çözümleme işleci (`::`), bu sınıflar türetilen sınıfta yeniden tanımlandığında doğrudan veya dolaylı temel sınıfların üyelerine başvurmak için kullanılabilir. Bu örneği göz önünde bulundurun:  
  
```  
// deriv_SingleInheritance2.cpp  
// compile with: /EHsc /c  
#include <iostream>  
using namespace std;  
class Document {  
public:  
   char *Name;   // Document name.  
   void PrintNameOf();   // Print name.  
};  
  
// Implementation of PrintNameOf function from class Document.  
void Document::PrintNameOf() {  
   cout << Name << endl;  
}  
  
class Book : public Document {  
public:  
   Book( char *name, long pagecount );  
private:  
   long  PageCount;  
};  
  
// Constructor from class Book.  
Book::Book( char *name, long pagecount ) {  
   Name = new char[ strlen( name ) + 1 ];  
   strcpy_s( Name, strlen(Name), name );  
   PageCount = pagecount;  
};  
```  
  
 `Book` oluşturucusunun (`Book::Book`) `Name` veri üyesine erişimi olduğunu unutmayın. Bir programda `Book` türündeki bir nesne oluşturulabilir ve aşağıdaki gibi kullanılabilir:  
  
```  
//  Create a new object of type Book. This invokes the  
//   constructor Book::Book.  
Book LibraryBook( "Programming Windows, 2nd Ed", 944 );  
  
...  
  
//  Use PrintNameOf function inherited from class Document.  
LibraryBook.PrintNameOf();  
```  
  
 Yukarıdaki örnekte de gösterildiği gibi, sınıf üyesi ve devralınan veri ve işlevler benzer şekilde kullanılır. `Book` sınıfı için uygulama `PrintNameOf` işlevinin yeniden uygulanmasını çağırırsa, `Document` sınıfına ait olan işlev yalnızca kapsam çözümleme (`::`) işleci kullanılarak çağrılabilir:  
  
```  
// deriv_SingleInheritance3.cpp  
// compile with: /EHsc /LD  
#include <iostream>  
using namespace std;  
  
class Document {  
public:  
   char *Name;          // Document name.  
   void  PrintNameOf() {}  // Print name.  
};  
  
class Book : public Document {  
   Book( char *name, long pagecount );  
   void PrintNameOf();  
   long  PageCount;  
};  
  
void Book::PrintNameOf() {  
   cout << "Name of book: ";  
   Document::PrintNameOf();  
}  
```  
  
 Türetilmiş sınıfların işaretçileri ve başvuruları erişilebilir, açık bir temel sınıf varsa temel sınıflarının işaretçilerine ve başvurularına örtük olarak dönüştürülebilir. Aşağıdaki kodda, bu kavram işaretçiler kullanılarak (başvurular için de aynı ilke geçerlidir) gösterilmektedir:  
  
```  
// deriv_SingleInheritance4.cpp  
// compile with: /W3  
struct Document {  
   char *Name;  
   void PrintNameOf() {}  
};  
  
class PaperbackBook : public Document {};  
  
int main() {  
   Document * DocLib[10];   // Library of ten documents.  
   for (int i = 0 ; i < 10 ; i++)  
      DocLib[i] = new Document;  
}  
```  
  
 Yukarıdaki örnekte, farklı türler oluşturulur. Ancak, bu türlerin tümü `Document` sınıfından türetildiği için `Document *` öğesine örtük dönüştürme vardır. Sonuç olarak `DocLib`, farklı nesne türleri içeren "heterojen listedir" (tüm nesnelerin aynı türden olmadığı bir liste).  
  
 `Document` sınıfında `PrintNameOf` işlevi olduğu için belgenin türüne özgü bilgilerin bazılarını atlasa da (`Book` için sayfa sayısı, `HelpFile` için bayt sayısı, vb.), kitaplıktaki her kitabın adını yazdırabilir.  
  
> [!NOTE]
>  Temel sınıfı `PrintNameOf` gibi bir işlevi uygulamaya zorlamak, genellikle iyi bir tasarım uygulaması değildir. [Sanal işlevler](../cpp/virtual-functions.md) diğer tasarım seçenekleri sunar.  
  
