---
title: Tek Devralma
ms.date: 11/19/2018
helpviewer_keywords:
- single inheritance
- base classes [C++], indirect
- scope, scope resolution operator
- operators [C++], scope resolution
- scope resolution operator
- derived classes [C++], single base class
- inheritance, single
ms.assetid: 1cb946ed-8b1b-4cf1-bde0-d9cecbfdc622
ms.openlocfilehash: 96af0c42a32f14280fd8c208a3e4eaec38a8ca3a
ms.sourcegitcommit: 9e891eb17b73d98f9086d9d4bfe9ca50415d9a37
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52175632"
---
# <a name="single-inheritance"></a>Tek Devralma

Sık kullanılan bir devralma biçimi olan "tek devralma"da, sınıflarda yalnızca bir temel sınıfı vardır. Aşağıdaki şekilde gösterilen ilişkiyi göz önünde bulundurun.

![Temel tek&#45;Devralma Grafiği](../cpp/media/vc38xj1.gif "temel tek&#45;Devralma Grafiği") <br/>
Basit Tek Devralma Grafiği

Şekildeki ilerlemenin genelden özele olduğuna dikkat edin. Çoğu sınıf hiyerarşisinin tasarımında bulunan diğer bir genel öznitelik ise türetilen sınıfın temel sınıf ile bir "türü" ilişkisi olmasıdır. Şekilde, `Book` bir `PrintedDocument` türü, `PaperbackBook` ise bir `book` türüdür.

Şekildeki notun diğer bir öğesi: `Book` hem türetilen bir sınıf (`PrintedDocument` öğesinden) hem de temel bir sınıftır (`PaperbackBook`, `Book` öğesinden türetilir). Böyle bir sınıf hiyerarşisi olan iskelet bildirimi aşağıdaki örnekte gösterilmiştir:

```cpp
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

Yukarıdaki örnekte, bir erişim belirticisi **genel** kullanılır. Genel, korumalı ve özel Devralmanın anlamı açıklanan [üye erişim denetimi.](../cpp/member-access-control-cpp.md)

Bir sınıf, aşağıdaki şekilde gösterildiği gibi birçok özel sınıf için temel sınıf olarak kullanılabilir.

![Yönlendirilmiş Çevrimsiz grafik](../cpp/media/vc38xj2.gif "yönlendirilmiş Çevrimsiz grafik") <br/>
Yönlendirilmiş Çevrimsiz Grafik Örneği

Yukarıda gösterilen "yönlendirilmiş çevrimsiz graf" (veya "DAG") adlı diyagramda, sınıfların bazıları birden fazla türetilmiş sınıfa yönelik temel sınıflardır. Ancak bunun tersi doğru değildir: türetilmiş herhangi bir sınıfa yönelik yalnızca bir doğrudan temel sınıf vardır. Şekildeki grafikte "tek devralma" yapısı gösterilmiştir.

> [!NOTE]
> Yönlendirilmiş çevrimsiz grafikler, tek devralmaya özgü değildir. Birden çok devralma grafiklerini göstermek için de kullanılırlar.

Devralma işleminde, türetilen sınıf temel sınıfın üyelerini ve eklediğiniz tüm yeni üyeleri içerir. Sonuç olarak, türetilen bir sınıf temel sınıfın üyelerine başvurabilir (bu üyeler türetilen sınıfta yeniden tanımlanmadıkça). Kapsam çözümleme işleci (`::`), bu sınıflar türetilen sınıfta yeniden tanımlandığında doğrudan veya dolaylı temel sınıfların üyelerine başvurmak için kullanılabilir. Bu örneği göz önünde bulundurun:

```cpp
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

```cpp
//  Create a new object of type Book. This invokes the
//   constructor Book::Book.
Book LibraryBook( "Programming Windows, 2nd Ed", 944 );

...

//  Use PrintNameOf function inherited from class Document.
LibraryBook.PrintNameOf();
```

Yukarıdaki örnekte de gösterildiği gibi, sınıf üyesi ve devralınan veri ve işlevler benzer şekilde kullanılır. `Book` sınıfı için uygulama `PrintNameOf` işlevinin yeniden uygulanmasını çağırırsa, `Document` sınıfına ait olan işlev yalnızca kapsam çözümleme (`::`) işleci kullanılarak çağrılabilir:

```cpp
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

```cpp
// deriv_SingleInheritance4.cpp
// compile with: /W3
struct Document {
   char *Name;
   void PrintNameOf() {}
};

class PaperbackBook : public Document {};

int main() {
   Document * DocLib[10];   // Library of ten documents.
   for (int i = 0 ; i < 5 ; i++)
      DocLib[i] = new Document;
   for (int i = 5 ; i < 10 ; i++)
      DocLib[i] = new PaperbackBook;
}
```

Yukarıdaki örnekte, farklı türler oluşturulur. Ancak, bu türlerin tümü `Document` sınıfından türetildiği için `Document *` öğesine örtük dönüştürme vardır. Sonuç olarak `DocLib`, farklı nesne türleri içeren "heterojen listedir" (tüm nesnelerin aynı türden olmadığı bir liste).

`Document` sınıfında `PrintNameOf` işlevi olduğu için belgenin türüne özgü bilgilerin bazılarını atlasa da (`Book` için sayfa sayısı, `HelpFile` için bayt sayısı, vb.), kitaplıktaki her kitabın adını yazdırabilir.

> [!NOTE]
>  Temel sınıfı `PrintNameOf` gibi bir işlevi uygulamaya zorlamak, genellikle iyi bir tasarım uygulaması değildir. [Sanal işlevler](../cpp/virtual-functions.md) başka tasarım alternatifleri sunar.