---
title: complex Sınıfı
ms.date: 03/27/2019
f1_keywords:
- complex/std::complex::value_type
- complex/std::complex::imag
- complex/std::complex::real
helpviewer_keywords:
- std::complex [C++], value_type
- std::complex [C++], imag
- std::complex [C++], real
ms.assetid: d6492e1c-5eba-4bc5-835b-2a88001a5868
ms.openlocfilehash: 0c72726bfb92965a2152830d7ce77ae13f763d35
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78876210"
---
# <a name="complex-class"></a>complex Sınıfı

Sınıf şablonu, bir karmaşık sayının gerçek bölümünü temsil eden biri olan `Type`türünde iki nesneyi depolayan bir nesne ve sanal parçayı temsil eden bir nesnesi tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Type>
class complex
```

## <a name="remarks"></a>Açıklamalar

`Type`sınıfının bir nesnesi:

- Geleneksel davranışa sahip ortak bir varsayılan Oluşturucu, yıkıcı, kopya Oluşturucusu ve atama işleci vardır.

- Tamsayı veya kayan nokta değerleri atanabilir veya geleneksel davranışla bu tür değerlere tür atama yapılabilir.

- Geleneksel davranışa sahip kayan nokta türleri için tanımlanan aritmetik işleçleri ve matematik işlevlerini, gerektiğinde tanımlar.

Özellikle, kopyalama oluşturma ve varsayılan oluşturma arasında ve ardından atama ile hiçbir hafif fark olamaz. `Type` sınıfının nesnelerinde hiçbir işlem özel durum oluşturabilir.

Üç kayan nokta türü için karmaşık sınıf şablonu açık özelleştirilmesi vardır. Bu uygulamada, `Type` diğer tür bir değer gerçek hesaplamalar için **Double** olarak, `Type`türünde depolanan nesneye yeniden atanmış olan **Double** sonucuyla birlikte typecast ' dır.

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

|||
|-|-|
|[ş](#complex)|Belirtilen gerçek ve sanal parçalar ile karmaşık bir sayı ya da başka bir karmaşık sayının kopyası olarak oluşturur.|

### <a name="typedefs"></a>Tür tanımları

|||
|-|-|
|[value_type](#value_type)|Karmaşık bir sayının gerçek ve sanal parçalarını temsil etmek için kullanılan veri türünü temsil eden bir tür.|

### <a name="functions"></a>İşlevler

|||
|-|-|
|[imag](#imag)|Karmaşık bir sayının sanal bileşenini ayıklar.|
|[gerçek](#real)|Karmaşık bir sayının gerçek bileşenini ayıklar.|

### <a name="operators"></a>İşleçler

|||
|-|-|
|[işleç * =](#op_star_eq)|Karmaşık bir sayının gerçek ve sanal parçalarıyla aynı türde olan bir faktörle bir hedef karmaşık sayıyı çarparak çarpar.|
|[işleç + =](#op_add_eq)|Eklenmiş sayının, eklendiği karmaşık sayının gerçek ve sanal kısımlarıyla aynı türde olabileceği hedef karmaşık sayıya bir sayı ekler.|
|[işleç-=](#operator-_eq)|Bir sayıyı hedef karmaşık sayıdan çıkartır, burada çıkarılan sayı, eklendiği karmaşık sayının gerçek ve sanal parçalarıyla aynı türde olabilir.|
|[işleç/=](#op_div_eq)|Karmaşık bir sayının gerçek ve sanal parçalarıyla aynı türde olan ve karmaşık olabilecek bir hedef karmaşık sayıyı bölen tarafından böler.|
|[işleç =](#op_eq)|Atanan sayının, atanmakta olduğu karmaşık sayının gerçek ve sanal parçalarıyla aynı türde olabileceği hedef karmaşık sayıya bir sayı atar.|

## <a name="complex"></a>ş

Belirtilen gerçek ve sanal parçalar ile karmaşık bir sayı ya da başka bir karmaşık sayının kopyası olarak oluşturur.

```cpp
constexpr complex(
    const T& _RealVal = 0,
    const T& _ImagVal = 0);

template <class Other>
constexpr complex(
    const complex<Other>& complexNum);
```

### <a name="parameters"></a>Parametreler

*_RealVal*\
Oluşturulan karmaşık sayıyı başlatmak için kullanılan gerçek parçanın değeri.

*_ImagVal*\
Oluşturulan karmaşık sayıyı başlatmak için kullanılan sanal parçanın değeri.

*Karmaşıksayı*\
Oluşturulan karmaşık sayıyı başlatmak için gerçek ve sanal parçalarını kullanılan karmaşık sayı.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu, depolanan gerçek parçayı, *realval\_* ve depolanan sanal bölümü *\_imagval*' a başlatır. İkinci Oluşturucu, depolanan gerçek parçayı `complexNum.real()` ve depolanan sanal bölümü `complexNum.imag()`olarak başlatır.

Bu uygulamada, bir çevirmen üye şablon işlevlerini desteklemiyorsa, şablon:

```cpp
template <class Other>
complex(const complex<Other>& right);
```

ile değiştirilmiştir:

```cpp
complex(const complex& right);
```

kopya Oluşturucu.

### <a name="example"></a>Örnek

```cpp
// complex_complex.cpp
// compile with: /EHsc
#include <complex>
#include <iostream>

int main( )
{
    using namespace std;
    double pi = 3.14159265359;

    // The first constructor specifies real & imaginary parts
    complex<double> c1( 4.0 , 5.0 );
    cout << "Specifying initial real & imaginary parts,"
        << "c1 = " << c1 << endl;

    // The second constructor initializes values of the real &
    // imaginary parts using those of another complex number
    complex<double> c2( c1 );
    cout << "Initializing with the real and imaginary parts of c1,"
        << " c2 = " << c2 << endl;

    // Complex numbers can be initialized in polar form
    // but will be stored in Cartesian form
    complex<double> c3( polar( sqrt( (double)8 ) , pi / 4 ) );
    cout << "c3 = polar( sqrt( 8 ) , pi / 4 ) = " << c3 << endl;

    // The modulus and argument of a complex number can be recovered
    double absc3 = abs( c3 );
    double argc3 = arg( c3 );
    cout << "The modulus of c3 is recovered from c3 using: abs( c3 ) = "
        << absc3 << endl;
    cout << "Argument of c3 is recovered from c3 using:\n arg( c3 ) = "
        << argc3 << " radians, which is " << argc3 * 180 / pi
        << " degrees." << endl;
}
```

## <a name="imag"></a>imag

Karmaşık bir sayının sanal bileşenini ayıklar.

```cpp
T imag() const;

T imag(const T& right);
```

### <a name="parameters"></a>Parametreler

*sağ*\
Sanal değeri ayıklanmak üzere olan karmaşık bir sayı.

### <a name="return-value"></a>Dönüş Değeri

Karmaşık sayının sanal bölümü.

### <a name="remarks"></a>Açıklamalar

*Bir + bı*karmaşık numarası için, sanal parça veya bileşen *IM (a + bi) = b*' dir.

### <a name="example"></a>Örnek

```cpp
// complex_imag.cpp
// compile with: /EHsc
#include <complex>
#include <iostream>

int main( )
{
    using namespace std;

    complex<double> c1( 4.0 , 3.0 );
    cout << "The complex number c1 = " << c1 << endl;

    double dr1 = c1.real();
    cout << "The real part of c1 is c1.real() = "
        << dr1 << "." << endl;

    double di1 = c1.imag();
    cout << "The imaginary part of c1 is c1.imag() = "
        << di1 << "." << endl;
}
```

```Output
The complex number c1 = (4,3)
The real part of c1 is c1.real() = 4.
The imaginary part of c1 is c1.imag() = 3.
```

## <a name="op_star_eq"></a>işleç * =

Karmaşık bir sayının gerçek ve sanal parçalarıyla aynı türde olan bir faktörle bir hedef karmaşık sayıyı çarparak çarpar.

```cpp
template <class Other>
complex& operator*=(const complex<Other>& right);

complex<Type>& operator*=(const Type& right);

complex<Type>& operator*=(const complex<Type>& right);
```

### <a name="parameters"></a>Parametreler

*sağ*\
Karmaşık bir sayı veya hedef karmaşık sayının parametresiyle aynı türde bir sayı.

### <a name="return-value"></a>Dönüş Değeri

Parametre olarak belirtilen sayı ile çarpılmış karmaşık bir sayı.

### <a name="remarks"></a>Açıklamalar

Bu işlem, verilerin belirli bir biçime dönüştürülmesi gerekmeden basit aritmetik işlemlerin yürütülebilmesi için aşırı yüklenmiştir.

### <a name="example"></a>Örnek

```cpp
// complex_op_me.cpp
// compile with: /EHsc
#include <complex>
#include <iostream>

int main()
{
    using namespace std;
    double pi = 3.14159265359;

    // Example of the first member function
    // type complex<double> multiplied by type complex<double>
    complex<double> cl1( polar ( 3.0 , pi / 6 ) );
    complex<double> cr1( polar ( 2.0 , pi / 3 ) );
    cout << "The left-side complex number is cl1 = " << cl1 << endl;
    cout << "The right-side complex number is cr1 = " << cr1 << endl;

    complex<double> cs1 = cl1 * cr1;
    cout << "Quotient of two complex numbers is: cs1 = cl1 * cr1 = "
        << cs1 << endl;

    // This is equivalent to the following operation
    cl1 *= cr1;
    cout << "Quotient of two complex numbers is also: cl1 *= cr1 = "
        << cl1 << endl;

    double abscl1 = abs ( cl1 );
    double argcl1 = arg ( cl1 );
    cout << "The modulus of cl1 is: " << abscl1 << endl;
    cout << "The argument of cl1 is: "<< argcl1 << " radians, which is "
        << argcl1 * 180 / pi << " degrees." << endl << endl;

    // Example of the second member function
    // type complex<double> multiplied by type double
    complex<double> cl2 ( polar ( 3.0 , pi / 6 ) );
    double cr2 = 5.0;
    cout << "The left-side complex number is cl2 = " << cl2 << endl;
    cout << "The right-side complex number is cr2 = " << cr2 << endl;

    complex<double> cs2 = cl2 * cr2;
    cout << "Quotient of two complex numbers is: cs2 = cl2 * cr2 = "
        << cs2 << endl;

    // This is equivalent to the following operation
    cl2 *= cr2;
    cout << "Quotient of two complex numbers is also: cl2 *= cr2 = "
        << cl2 << endl;

    double abscl2 = abs ( cl2 );
    double argcl2 = arg ( cl2 );
    cout << "The modulus of cl2 is: " << abscl2 << endl;
    cout << "The argument of cl2 is: "<< argcl2 << " radians, which is "
        << argcl2 * 180 / pi << " degrees." << endl;
}
```

## <a name="op_add_eq"></a>işleç + =

Eklenmiş sayının, eklendiği karmaşık sayının gerçek ve sanal kısımlarıyla aynı türde olabileceği hedef karmaşık sayıya bir sayı ekler.

```cpp
template <class Other>
complex<Type>& operator+=(const complex<Other>& right);

complex<Type>& operator+=(const Type& right);

complex<Type>& operator+=(const complex<Type>& right);
```

### <a name="parameters"></a>Parametreler

*sağ*\
Karmaşık bir sayı veya hedef karmaşık sayının parametresiyle aynı türde bir sayı.

### <a name="return-value"></a>Dönüş Değeri

Eklenmiş bir parametre olarak belirtilen sayı olan karmaşık bir sayı.

### <a name="remarks"></a>Açıklamalar

Bu işlem, verilerin belirli bir biçime dönüştürülmesi gerekmeden basit aritmetik işlemlerin yürütülebilmesi için aşırı yüklenmiştir.

### <a name="example"></a>Örnek

```cpp
// complex_op_pe.cpp
// compile with: /EHsc
#include <complex>
#include <iostream>

int main( )
{
   using namespace std;
   double pi = 3.14159265359;

   // Example of the first member function
   // type complex<double> added to type complex<double>
   complex<double> cl1( 3.0 , 4.0 );
   complex<double> cr1( 2.0 , -1.0 );
   cout << "The left-side complex number is cl1 = " << cl1 << endl;
   cout << "The right-side complex number is cr1 = " << cr1 << endl;

   complex<double> cs1 = cl1 + cr1;
   cout << "The sum of the two complex numbers is: cs1 = cl1 + cr1 = "
        << cs1 << endl;

   // This is equivalent to the following operation
   cl1 += cr1;
   cout << "The complex number cr1 added to the complex number cl1 is:"
        << "\n cl1 += cr1 = " << cl1 << endl;

   double abscl1 = abs( cl1 );
   double argcl1 = arg( cl1 );
   cout << "The modulus of cl1 is: " << abscl1 << endl;
   cout << "The argument of cl1 is: "<< argcl1 << " radians, which is "
        << argcl1 * 180 / pi << " degrees." << endl << endl;

   // Example of the second member function
   // type double added to type complex<double>
   complex<double> cl2( -2 , 4 );
   double cr2 =5.0;
   cout << "The left-side complex number is cl2 = " << cl2 << endl;
   cout << "The right-side complex number is cr2 = " << cr2 << endl;

   complex<double> cs2 = cl2 + cr2;
   cout << "The sum of the two complex numbers is: cs2 = cl2 + cr2 = "
        << cs2 << endl;

   // This is equivalent to the following operation
   cl2 += cr2;
   cout << "The complex number cr2 added to the complex number cl2 is:"
        << "\n cl2 += cr2 = " << cl2 << endl;

   double abscl2 = abs( cl2 );
   double argcl2 = arg( cl2 );
   cout << "The modulus of cl2 is: " << abscl2 << endl;
   cout << "The argument of cl2 is: "<< argcl2 << " radians, which is "
        << argcl2 * 180 / pi << " degrees." << endl << endl;
}
```

```Output
The left-side complex number is cl1 = (3,4)
The right-side complex number is cr1 = (2,-1)
The sum of the two complex numbers is: cs1 = cl1 + cr1 = (5,3)
The complex number cr1 added to the complex number cl1 is:
cl1 += cr1 = (5,3)
The modulus of cl1 is: 5.83095
The argument of cl1 is: 0.54042 radians, which is 30.9638 degrees.

The left-side complex number is cl2 = (-2,4)
The right-side complex number is cr2 = 5
The sum of the two complex numbers is: cs2 = cl2 + cr2 = (3,4)
The complex number cr2 added to the complex number cl2 is:
cl2 += cr2 = (3,4)
The modulus of cl2 is: 5
The argument of cl2 is: 0.927295 radians, which is 53.1301 degrees.
```

## <a name="operator-_eq"></a>işleç-=

Bir sayıyı hedef karmaşık sayıdan çıkartır, burada çıkarılan sayı, eklendiği karmaşık sayının gerçek ve sanal parçalarıyla aynı türde olabilir.

```cpp
template <class Other>
complex<Type>& operator-=(const complex<Other>& complexNum);

complex<Type>& operator-=(const Type& _RealPart);

complex<Type>& operator-=(const complex<Type>& complexNum);
```

### <a name="parameters"></a>Parametreler

*Karmaşıksayı*\
Hedef karmaşık sayıdan çıkarılan karmaşık bir sayı.

*_RealPart*\
Hedef karmaşık sayıdan çıkarılan gerçek sayı.

### <a name="return-value"></a>Dönüş Değeri

Bir parametre olarak belirtilen sayının ondan çıkarılan karmaşık bir sayı.

### <a name="remarks"></a>Açıklamalar

Bu işlem, verilerin belirli bir biçime dönüştürülmesi gerekmeden basit aritmetik işlemlerin yürütülebilmesi için aşırı yüklenmiştir.

### <a name="example"></a>Örnek

```cpp
// complex_op_se.cpp
// compile with: /EHsc
#include <complex>
#include <iostream>

int main( )
{
   using namespace std;
   double pi = 3.14159265359;

   // Example of the first member function
   // type complex<double> subtracted from type complex<double>
   complex<double> cl1( 3.0 , 4.0 );
   complex<double> cr1( 2.0 , -1.0 );
   cout << "The left-side complex number is cl1 = " << cl1 << endl;
   cout << "The right-side complex number is cr1 = " << cr1 << endl;

   complex<double> cs1 = cl1 - cr1;
   cout << "The difference between the two complex numbers is:"
        << "\n cs1 = cl1 - cr1 = " << cs1 << endl;

   // This is equivalent to the following operation
   cl1 -= cr1;
   cout << "Complex number cr1 subtracted from complex number cl1 is:"
        << "\n cl1 -= cr1 = " << cl1 << endl;

   double abscl1 = abs( cl1 );
   double argcl1 = arg( cl1 );
   cout << "The modulus of cl1 is: " << abscl1 << endl;
   cout << "The argument of cl1 is: "<< argcl1 << " radians, which is "
        << argcl1 * 180 / pi << " degrees." << endl << endl;

   // Example of the second member function
   // type double subtracted from type complex<double>
   complex<double> cl2( 2.0 , 4.0 );
   double cr2 = 5.0;
   cout << "The left-side complex number is cl2 = " << cl2 << endl;
   cout << "The right-side complex number is cr2 = " << cr2 << endl;

   complex<double> cs2 = cl2 - cr2;
   cout << "The difference between the two complex numbers is:"
        << "\n cs2 = cl2 - cr2 = " << cs2 << endl;

   // This is equivalent to the following operation
   cl2  -= cr2;
   cout << "Complex number cr2 subtracted from complex number cl2 is:"
        << "\n cl2 -= cr2 = " << cl2 << endl;

   double abscl2 = abs( cl2 );
   double argcl2 = arg( cl2 );
   cout << "The modulus of cl2 is: " << abscl2 << endl;
   cout << "The argument of cl2 is: "<< argcl2 << " radians, which is "
        << argcl2 * 180 / pi << " degrees." << endl << endl;
}
```

```Output
The left-side complex number is cl1 = (3,4)
The right-side complex number is cr1 = (2,-1)
The difference between the two complex numbers is:
cs1 = cl1 - cr1 = (1,5)
Complex number cr1 subtracted from complex number cl1 is:
cl1 -= cr1 = (1,5)
The modulus of cl1 is: 5.09902
The argument of cl1 is: 1.3734 radians, which is 78.6901 degrees.

The left-side complex number is cl2 = (2,4)
The right-side complex number is cr2 = 5
The difference between the two complex numbers is:
cs2 = cl2 - cr2 = (-3,4)
Complex number cr2 subtracted from complex number cl2 is:
cl2 -= cr2 = (-3,4)
The modulus of cl2 is: 5
The argument of cl2 is: 2.2143 radians, which is 126.87 degrees.
```

## <a name="op_div_eq"></a>işleç/=

Karmaşık bir sayının gerçek ve sanal parçalarıyla aynı türde olan ve karmaşık olabilecek bir hedef karmaşık sayıyı bölen tarafından böler.

```cpp
template <class Other>
complex<Type>& operator/=(const complex<Other>& complexNum);

complex<Type>& operator/=(const Type& _RealPart);

complex<Type>& operator/=(const complex<Type>& complexNum);
```

### <a name="parameters"></a>Parametreler

*Karmaşıksayı*\
Hedef karmaşık sayıdan çıkarılan karmaşık bir sayı.

*_RealPart*\
Hedef karmaşık sayıdan çıkarılan gerçek sayı.

### <a name="return-value"></a>Dönüş Değeri

Parametre olarak belirtilen sayıya bölünen karmaşık bir sayı.

### <a name="remarks"></a>Açıklamalar

Bu işlem, verilerin belirli bir biçime dönüştürülmesi gerekmeden basit aritmetik işlemlerin yürütülebilmesi için aşırı yüklenmiştir.

### <a name="example"></a>Örnek

```cpp
// complex_op_de.cpp
// compile with: /EHsc
#include <complex>
#include <iostream>

int main( )
{
   using namespace std;
   double pi = 3.14159265359;

   // Example of the first member function
   // type complex<double> divided by type complex<double>
   complex<double> cl1( polar (3.0 , pi / 6 ) );
   complex<double> cr1( polar (2.0 , pi / 3 ) );
   cout << "The left-side complex number is cl1 = " << cl1 << endl;
   cout << "The right-side complex number is cr1 = " << cr1 << endl;

   complex<double> cs1 = cl1 / cr1;
   cout << "The quotient of the two complex numbers is: cs1 = cl1 /cr1 = "
        << cs1 << endl;

   // This is equivalent to the following operation
   cl1 /= cr1;
   cout << "Quotient of two complex numbers is also: cl1 /= cr1 = "
        << cl1 << endl;

   double abscl1 = abs( cl1 );
   double argcl1 = arg( cl1 );
   cout << "The modulus of cl1 is: " << abscl1 << endl;
   cout << "The argument of cl1 is: "<< argcl1 << " radians, which is "
        << argcl1 * 180 / pi << " degrees." << endl << endl;

   // Example of the second member function
   // type complex<double> divided by type double
   complex<double> cl2( polar(3.0 , pi / 6 ) );
   double cr2 =5;
   cout << "The left-side complex number is cl2 = " << cl2 << endl;
   cout << "The right-side complex number is cr2 = " << cr2 << endl;

   complex<double> cs2 = cl2 / cr2;
   cout << "The quotient of the two complex numbers is: cs2 /= cl2 cr2 = "
        << cs2 << endl;

   // This is equivalent to the following operation
   cl2 /= cr2;
   cout << "Quotient of two complex numbers is also: cl2 = /cr2 = "
        << cl2 << endl;

   double abscl2 = abs( cl2 );
   double argcl2 = arg( cl2 );
   cout << "The modulus of cl2 is: " << abscl2 << endl;
   cout << "The argument of cl2 is: "<< argcl2 << " radians, which is "
        << argcl2 * 180 / pi << " degrees." << endl << endl;
}
```

```Output
The left-side complex number is cl1 = (2.59808,1.5)
The right-side complex number is cr1 = (1,1.73205)
The quotient of the two complex numbers is: cs1 = cl1 /cr1 = (1.29904,-0.75)
Quotient of two complex numbers is also: cl1 /= cr1 = (1.29904,-0.75)
The modulus of cl1 is: 1.5
The argument of cl1 is: -0.523599 radians, which is -30 degrees.

The left-side complex number is cl2 = (2.59808,1.5)
The right-side complex number is cr2 = 5
The quotient of the two complex numbers is: cs2 /= cl2 cr2 = (0.519615,0.3)
Quotient of two complex numbers is also: cl2 = /cr2 = (0.519615,0.3)
The modulus of cl2 is: 0.6
The argument of cl2 is: 0.523599 radians, which is 30 degrees.
```

## <a name="op_eq"></a>işleç =

Atanan sayının, atanmakta olduğu karmaşık sayının gerçek ve sanal parçalarıyla aynı türde olabileceği hedef karmaşık sayıya bir sayı atar.

```cpp
template <class Other>
complex<Type>& operator=(const complex<Other>& right);

complex<Type>& operator=(const Type& right);
```

### <a name="parameters"></a>Parametreler

*sağ*\
Karmaşık bir sayı veya hedef karmaşık sayının parametresiyle aynı türde bir sayı.

### <a name="return-value"></a>Dönüş Değeri

Parametre olarak belirtilen sayının atandığı karmaşık bir sayı.

### <a name="remarks"></a>Açıklamalar

Bu işlem, verilerin belirli bir biçime dönüştürülmesi gerekmeden basit aritmetik işlemlerin yürütülebilmesi için aşırı yüklenmiştir.

### <a name="example"></a>Örnek

```cpp
// complex_op_as.cpp
// compile with: /EHsc
#include <complex>
#include <iostream>

int main( )
{
   using namespace std;
   double pi = 3.14159265359;

   // Example of the first member function
   // type complex<double> assigned to type complex<double>
   complex<double> cl1( 3.0 , 4.0 );
   complex<double> cr1( 2.0 , -1.0 );
   cout << "The left-side complex number is cl1 = " << cl1 << endl;
   cout << "The right-side complex number is cr1 = " << cr1 << endl;

   cl1  = cr1;
   cout << "The complex number cr1 assigned to the complex number cl1 is:"
        << "\ncl1 = cr1 = " << cl1 << endl;

   // Example of the second member function
   // type double assigned to type complex<double>
   complex<double> cl2( -2 , 4 );
   double cr2 =5.0;
   cout << "The left-side complex number is cl2 = " << cl2 << endl;
   cout << "The right-side complex number is cr2 = " << cr2 << endl;

   cl2 = cr2;
   cout << "The complex number cr2 assigned to the complex number cl2 is:"
        << "\ncl2 = cr2 = " << cl2 << endl;

   cl2 = complex<double>(3.0, 4.0);
   cout << "The complex number (3, 4) assigned to the complex number cl2 is:"
        << "\ncl2 = " << cl2 << endl;
}
```

```Output
The left-side complex number is cl1 = (3,4)
The right-side complex number is cr1 = (2,-1)
The complex number cr1 assigned to the complex number cl1 is:
cl1 = cr1 = (2,-1)
The left-side complex number is cl2 = (-2,4)
The right-side complex number is cr2 = 5
The complex number cr2 assigned to the complex number cl2 is:
cl2 = cr2 = (5,0)
The complex number (3, 4) assigned to the complex number cl2 is:
cl2 = (3,4)
```

## <a name="real"></a>gerçek

Karmaşık bir sayının gerçek bileşenini alır veya ayarlar.

```cpp
constexpr T real() const;

T real(const T& right);
```

### <a name="parameters"></a>Parametreler

*sağ*\
Gerçek değeri ayıklanmak üzere olan karmaşık bir sayı.

### <a name="return-value"></a>Dönüş Değeri

Karmaşık sayının gerçek bölümü.

### <a name="remarks"></a>Açıklamalar

*Bir + bi*karmaşık numarası için, gerçek parça veya bileşen bir *Re (a + bi) = a*olur.

### <a name="example"></a>Örnek

```cpp
// complex_class_real.cpp
// compile with: /EHsc
#include <complex>
#include <iostream>

int main( )
{
   using namespace std;

   complex<double> c1( 4.0 , 3.0 );
   cout << "The complex number c1 = " << c1 << endl;

   double dr1 = c1.real();
   cout << "The real part of c1 is c1.real() = "
        << dr1 << "." << endl;

   double di1 = c1.imag();
   cout << "The imaginary part of c1 is c1.imag() = "
        << di1 << "." << endl;
}
```

```Output
The complex number c1 = (4,3)
The real part of c1 is c1.real() = 4.
The imaginary part of c1 is c1.imag() = 3.
```

## <a name="value_type"></a>value_type

Karmaşık bir sayının gerçek ve sanal parçalarını temsil etmek için kullanılan veri türünü temsil eden bir tür.

```cpp
typedef Type value_type;
```

### <a name="remarks"></a>Açıklamalar

`value_type`, sınıf karmaşık `Type` şablonu parametresinin eşanlamlısıdır.

### <a name="example"></a>Örnek

```cpp
// complex_valuetype.cpp
// compile with: /EHsc
#include <complex>
#include <iostream>

int main( )
{
    using namespace std;
    complex<double>::value_type a = 3, b = 4;

    complex<double> c1 ( a , b );
    cout << "Specifying initial real & imaginary parts"
        << "\nof type value_type: "
        << "c1 = " << c1 << "." << endl;
}
```

```Output
Specifying initial real & imaginary parts
of type value_type: c1 = (3,4).
```

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
