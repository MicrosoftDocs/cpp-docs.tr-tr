---
title: karmaşık&lt;çift&gt; | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- complex/std::complex<double>
dev_langs:
- C++
helpviewer_keywords:
- complex<double> function
ms.assetid: 0d0b9d2a-9b9b-410b-82a0-86b6df127e47
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f5a311083df4783b94b82f74f8fa5849dff8b429
ms.sourcegitcommit: 1d9bd38cacbc783fccd3884b7b92062161c91c84
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/03/2018
ms.locfileid: "48234742"
---
# <a name="complexltdoublegt"></a>karmaşık&lt;çift&gt;

Her iki türdeki nesneleri sıralı bir çift depolayan bir nesneyi tanımlayan **çift**, ilk karmaşık sayıyı ve ikinci gerçek bölümünü temsil eden sanal bölümü temsil eden.

## <a name="syntax"></a>Sözdizimi

```cpp
template <>
class complex<double> {
public:
    constexpr complex(
    double RealVal = 0,
    double ImagVal = 0);

constexpr complex(const complex<double>& complexNum);

constexpr explicit complex(const complex<long double>& complexNum);
// rest same as template class complex
};
```

### <a name="parameters"></a>Parametreler

*RealVal*<br/>
Türü değeri **çift** için yapılandırılan karmaşık sayıyı gerçek bir parçası.

*ImagVal*<br/>
Türü değeri **çift** yapılandırılmakta karmaşık sayıyı sanal bölümü için.

*complexNum*<br/>
Tür karmaşık sayısı **float** veya türü **uzun çift** olan reel ve sanal parça türü karmaşık bir sayıyı başlatmak için kullanılan **çift** oluşturuluyor.

## <a name="return-value"></a>Dönüş Değeri

Türü karmaşık bir sayıyı **çift**.

## <a name="remarks"></a>Açıklamalar

Karmaşık türü karmaşık bir sınıfa şablon sınıfının açık uzmanlığı **çift** Şablon sınıfı yalnızca tanımladığı Yapıcılardaki farklıdır. Dönüştürme **float** için **çift** örtük, izin verilen ancak dönüştürme **uzun çift** için **çift** olması gerekir **açık**. Kullanımını **açık** başlatma ile atama sözdizimi kullanılarak tür dönüştürme kuralları.

Şablon sınıfı hakkında daha fazla bilgi için `complex`, bkz: [complex sınıfı](../standard-library/complex-class.md). Şablon sınıfının üye listesini `complex`, bkz.

## <a name="example"></a>Örnek

```cpp
// complex_comp_dbl.cpp
// compile with: /EHsc
#include <complex>
#include <iostream>

int main( )
{
   using namespace std;
   double pi = 3.14159265359;

   // The first constructor specifies real & imaginary parts
   complex <double> c1 ( 4.0 , 5.0 );
   cout << "Specifying initial real & imaginary parts,\n"
        << "as type double gives c1 = " << c1 << endl;

   // The second constructor initializes values of the real &
   // imaginary parts using those of complex number of type float
   complex <float> c2float ( 4.0 , 5.0 );
   complex <double> c2double ( c2float );
   cout << "Implicit conversion from type float to type double,"
        << endl << "gives c2double = " << c2double << endl;

   // The third constructor initializes values of the real &
   // imaginary parts using those of a complex number
   // of type long double
   complex <long double> c3longdouble ( 4.0 , 5.0 );
   complex <double> c3double ( c3longdouble );
   cout << "Explicit conversion from type float to type double,"
        << endl << "gives c3longdouble = " << c3longdouble << endl;

   // The modulus and argument of a complex number can be recovered
   double absc3 = abs ( c3longdouble );
   double argc3 = arg ( c3longdouble );
   cout << "The modulus of c3 is recovered from c3 using: abs ( c3 ) = "
        << absc3 << endl;
   cout << "Argument of c3 is recovered from c3 using:" << endl
        << "arg ( c3 ) = " << argc3 << " radians, which is "
        << argc3 * 180 / pi << " degrees." << endl;
}
/* Output:
Specifying initial real & imaginary parts,
as type double gives c1 = (4,5)
Implicit conversion from type float to type double,
gives c2double = (4,5)
Explicit conversion from type float to type double,
gives c3longdouble = (4,5)
The modulus of c3 is recovered from c3 using: abs ( c3 ) = 6.40312
Argument of c3 is recovered from c3 using:
arg ( c3 ) = 0.896055 radians, which is 51.3402 degrees.
*/
```

## <a name="requirements"></a>Gereksinimler

**Üst bilgi**: \<karmaşık >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[complex Sınıfı](../standard-library/complex-class.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
