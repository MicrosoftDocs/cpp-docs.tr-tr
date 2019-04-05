---
title: Derleyici Hatası C2664
ms.date: 11/04/2016
f1_keywords:
- C2664
helpviewer_keywords:
- C2664
ms.assetid: 3595d66e-cf87-4fda-a896-c0cd81f95db4
ms.openlocfilehash: cffd178e1736358333ee27d4572d3531de23f527
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "58774613"
---
# <a name="compiler-error-c2664"></a>Derleyici Hatası C2664

'function': 'type1' öğesinden 'type2' bağımsız değişkeni n dönüştürülemiyor

Bu parametre sorunu, bir sınıfın bir örneği oluşturulur ve işaretli bir oluşturucuda örtülü dönüştürme denendi gerçekleşebilir `explicit` anahtar sözcüğü. Açık dönüştürmeler hakkında daha fazla bilgi için bkz: [kullanıcı tanımlı tür dönüşümleri](../../cpp/user-defined-type-conversions-cpp.md).

Geçici bir nesne bir parametre olarak bir nesneye bir başvuru alan bir işleve geçirilirse, bu başvuruyu olmalıdır bir `const` başvuru.

İşlev, işlevin beklediği türde olmayan bir parametreye geçirilmişse, uygun oluşturucu kullanılarak geçici bir nesne oluşturulur. Bu geçici nesne, daha sonra işleve geçirilir. Bu durumda, geçici nesne, başvuruyu başlatmak üzere kullanılır. Dilin önceki sürümlerinde, tüm başvurular geçici nesneler tarafından başlatılabiliyordu.

C2664 düzeltmek için

- Verilen işlevin prototipini yeniden denetleyin ve hata iletisinde belirtilen bağımsız değişkeni düzeltin.

- Gerekirse, açık bir dönüştürme sağlayın.

C2664, aynı zamanda, bir sınıf, temel sınıflarından birinde bir üye gizlediğinde de meydana gelebilir.

Daha fazla bilgi için [nasıl yapılır: System:: String'i wchar_t * veya char dönüştürme\*](../../dotnet/how-to-convert-system-string-to-wchar-t-star-or-char-star.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C2664 oluşturur ve bu sorunun nasıl gösterir.

```
// C2664.cpp
// C2664
struct A {
   void f(int i) {};
};

struct B : public A {
   // To fix, uncomment the following line.
   // using A::f;
   void f(A a) {};
};

int main() {
   B b;
   int i = 1;
   b.f(i);   // B::F hides A::f Uncomment the using declaration in B.
}
```

## <a name="example"></a>Örnek

Bu örnek C2664 oluşturur ve bu sorunun nasıl gösterir.

```
// C2664b.cpp
// C2664 expected
struct A {
   // To fix, uncomment the following line.
   // A(int i){}
};

void func( int, A ) {}

int main() {
   func( 1, 1 );   // No conversion from int to A.
}
```

## <a name="example"></a>Örnek

Sonraki örnek C2664 çağırmak için bir dize değişmez değeri kullanarak gösterir `Test`ve bu sorunun nasıl gösterir. Parametre bir `szString` başvuru, bir nesne uygun oluşturucu kullanılarak oluşturulmalıdır. Sonuç, başvuruyu başlatmak üzere kullanılamayan geçici bir nesnedir.

```
// C2664c.cpp
// compile with: /EHsc
// C2664 expected
#include <iostream>
#include <string.h>
using namespace std;

class szString {
   int slen;
   char *str;

public:
   szString(const char *);
   int len() const {
      return slen;
   }
};

// Simple reference cannot bind to temp var.
void Test(szString &a) {}

// To fix, uncomment the following line.
// void Test(const szString &a) {}

szString::szString(const char * newstr) : slen(0), str(NULL) {
   slen=strlen(newstr);
   str = new char[slen + 1];
   if (str)
      strcpy_s(str, (slen + 1), newstr);
}

int main() {
   Test("hello");
}
```

## <a name="example"></a>Örnek

Derleyici uygulamak için C++ Standart gereksinimlerini uygular `const`. Bu örnek C2664 oluşturur:

```
// C2664d.cpp
// C2664 expected
#include <windows.h>

void func1(LPCSTR &s)
{

}

void func2(LPSTR &s)
{
   func1(s);
}

int main()
{
   return 0;
}
```

## <a name="example"></a>Örnek

C2664, nasıl düzeltileceği hakkında yönergeler dahil olmak üzere oluşturulduğu daha karmaşık bir durum şu şekildedir:

```
// C2664e.cpp
// compile with: /EHsc
// C2664 expected
#define _INTL
#include <locale>
#include <iostream>

using namespace std;
#define LEN 90

int main( ) {
   char* pszExt = "This is the string to be converted!";
   wchar_t pwszInt [LEN+1];
   memset(&pwszInt[0], 0, (sizeof(wchar_t))*(LEN+1));

   // To fix, delete the following line.
   char* pszNext;

   // To fix, uncomment the following line.
   // const char* pszNext;

   wchar_t* pwszNext;
   mbstate_t state;
   locale loc("C");
   int res = use_facet<codecvt<wchar_t, char, mbstate_t> >
      ( loc ).in( state,
      pszExt, &pszExt[strlen(pszExt)], pszNext,
      pwszInt, &pwszInt[strlen(pszExt)], pwszNext );
   // See earlier comment.
      pwszInt[strlen(pszExt)] = 0;
   wcout << ( (res!=codecvt_base::error) ?
                       L"It worked! " : L"It didn't work! " )
   << L"The converted string is:\n ["
   << &pwszInt[0]
   << L"]" << endl;

   exit(-1);
}
```

## <a name="example"></a>Örnek

Enum değişkeni, temelindeki türe işlev çağrısını karşılayacak şekilde dönüştürülemez. Daha fazla bilgi için [sabit listesi sınıfı](../../extensions/enum-class-cpp-component-extensions.md). Aşağıdaki örnek C2664 oluşturur ve bu sorunun nasıl gösterir.

```
// C2664f.cpp
// compile with: /clr
using namespace System;
public enum class A : Char {
   None = 0,
   NonSilent = 1,
};

void Test(Char c) {}

int main() {
   A aa = A::None;
   Test(aa);   // C2664
   Test(Char(aa));   // OK - fix by using a conversion cast
}
```

## <a name="example"></a>Örnek

MIDL derleyicisindeki bir hata, tür kitaplığında unsigned short olarak wchar_t türünün yayılmasına neden oluyor. Bu hatayı gidermek için türü C++ kaynak kodunda yayımlayın ya da türü idl dosyasında bir dize olarak tanımlayın.

```
// C2664g.idl
import "prsht.idl";

[ object, uuid(8402B8F1-BF7F-4B49-92D4-C2B9DF4543E9) ]

interface IMyObj1 : IUnknown {
   HRESULT  teststr([in, string] wchar_t *wstr);
   HRESULT  testarr([in, size_is(len)] wchar_t wstr[], [in] int len);
   HRESULT  testbstr([in] BSTR bstr);
};

[  uuid(44463307-CBFC-47A6-8B4F-13CD0A83B436) ]
library myproj1 {
   [  version(1.0), uuid(D8622C12-5448-42B8-8F0E-E3AD6B8470C1) ]
   coclass CMyObj1 { interface IMyObj1; };
}
```

C2664, kullanarak da oluşturulur `wchar_t` sonraki sürümlerinde Visual C++ 6.0 kodundan taşırken. Visual C++ 6.0 ve önceki sürümlerinde, `wchar_t` olduğu bir `typedef` için `unsigned short` ve bu nedenle bu türe örtük olarak dönüştürülebilir. Visual C++ 6.0 sonra `wchar_t` C++ standardında belirtildiği gibi kendi yerleşik türü ve artık örtük olarak dönüştürülebilir değil `unsigned short`. Bkz: [/ZC: wchar_t (wchar_t yerel türü olduğu)](../../build/reference/zc-wchar-t-wchar-t-is-native-type.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C2664 oluşturur ve bu sorunun nasıl gösterir.

```
// C2664h.cpp
#import "C2664g.tlb"
using namespace myproj1;

int main() {
   IMyObj1Ptr ptr;

   wchar_t * mybuff = 0;
   BSTR bstr = 0;
   int len;
   ptr->teststr(mybuff);
   ptr->testbstr(bstr);
   ptr->testarr(mybuff, len);   // C2664
   ptr->testarr((unsigned short *)mybuff, len);   // OK - Fix by using a cast
}
```

## <a name="example"></a>Örnek

C2664, derleyici şablon bağımsız değişkenlerini çözümleyemediğinde de oluşabilir.

```
// C2664i.cpp
#include <stdio.h>
template <class T, int iType=0>
class CTypedImg {
public:
   CTypedImg() {}
   void run() {}

   operator CTypedImg<T>& () {
      return *((CTypedImg<T>*)this);
    }
};

template <class t1>
void test(CTypedImg<t1>& myarg) {
   myarg.run();
}

int main() {
   CTypedImg<float,2> img;

   test((CTypedImg<float>&)img);   // OK
   test<float>(img);   // OK
   test(img);   // C2664 - qualify as above to fix
}
```