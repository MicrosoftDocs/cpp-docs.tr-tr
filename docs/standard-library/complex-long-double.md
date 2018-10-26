---
title: karmaşık&lt;uzun çift&gt; | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- std::complex<long double>
- complex<long double>
- std.complex<long double>
dev_langs:
- C++
helpviewer_keywords:
- complex<long double> function
ms.assetid: 37591991-b385-46e9-b727-d534dbc10432
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e1d17b66285b60190a5c91c8defd5adf51f79a6a
ms.sourcegitcommit: 8c2de32e96c84d0147af3cce1e89e4f28707ff12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/26/2018
ms.locfileid: "50143659"
---
# <a name="complexltlong-doublegt"></a>karmaşık&lt;uzun çift&gt;

Bu açıkça özel bir şablon sınıfının nesneleri, tür hem de sıralı bir çift depolayan bir nesneyi tanımlayan **uzun çift**, ilk karmaşık sayıyı ve ikinci gerçek bölümünü temsil eden sanal bölümü temsil eden.

## <a name="syntax"></a>Sözdizimi

```cpp
template <>
class complex<long double> {
public:
    constexpr complex(
    long double _RealVal = 0,
    long double _ImagVal = 0);

complex(
    constexpr complex<long double>& complexNum);

// rest same as template class complex
};
```

### <a name="parameters"></a>Parametreler

*_RealVal*<br/>
Türü değeri **uzun çift** için yapılandırılan karmaşık sayıyı gerçek bir parçası.

*_ImagVal*<br/>
Türü değeri **uzun çift** yapılandırılmakta karmaşık sayıyı sanal bölümü için.

*complexNum*<br/>
Tür karmaşık sayısı **çift** veya türü **float** olan reel ve sanal parça türü karmaşık bir sayıyı başlatmak için kullanılan **uzun çift** oluşturuluyor.

## <a name="return-value"></a>Dönüş Değeri

Türü karmaşık bir sayıyı **uzun çift**.

## <a name="remarks"></a>Açıklamalar

Şablon sınıfının açık uzmanlığı `complex` türü karmaşık bir sınıfa **uzun çift** Şablon sınıfı yalnızca tanımladığı Yapıcılardaki farklıdır. Dönüştürme **uzun çift** için **float** örtük, izin verilen ancak dönüştürme **çift** için **uzun çift** gereklidir olmasını **açık**. Kullanımını **açık** başlatma ile atama sözdizimi kullanılarak tür dönüştürme kuralları.

Şablon sınıfı hakkında daha fazla bilgi için `complex` ve onun üyeleri [complex sınıfı](../standard-library/complex-class.md).

**Microsoft'a özgü**: **uzun çift** ve **çift** türleri aynı gösterimi vardır, ancak farklı türleri. Daha fazla bilgi için [temel türler](../cpp/fundamental-types-cpp.md).

## <a name="example"></a>Örnek

```cpp
// complex_comp_ld.cpp
// compile with: /EHsc
#include <complex>
#include <iostream>

int main( )
{
    using namespace std;
    double pi = 3.14159265359;

    // The first constructor specifies real & imaginary parts
    complex<long double> c1( 4.0 , 5.0 );
    cout << "Specifying initial real & imaginary parts,\n"
        << " as type float gives c1 = " << c1 << endl;

    // The second constructor initializes values of the real &
    // imaginary parts using those of complex number of type float
    complex<float> c2float( 1.0 , 3.0 );
    complex<long double> c2longdouble ( c2float );
    cout << "Implicit conversion from type float to type long double,"
        << "\n gives c2longdouble = " << c2longdouble << endl;

    // The third constructor initializes values of the real &
    // imaginary parts using those of a complex number
    // of type double
    complex<double> c3double( 3.0 , 4.0 );
    complex<long double> c3longdouble( c3double );
    cout << "Implicit conversion from type long double to type float,"
        << "\n gives c3longdouble = " << c3longdouble << endl;

    // The modulus and argument of a complex number can be recovered
    double absc3 = abs( c3longdouble );
    double argc3 = arg( c3longdouble );
    cout << "The modulus of c3 is recovered from c3 using: abs( c3 ) = "
        << absc3 << endl;
    cout << "Argument of c3 is recovered from c3 using:\n arg( c3 ) = "
        << argc3 << " radians, which is " << argc3 * 180 / pi
        << " degrees." << endl;
}
```

```Output
Specifying initial real & imaginary parts,
as type float gives c1 = (4,5)
Implicit conversion from type float to type long double,
gives c2longdouble = (1,3)
Implicit conversion from type long double to type float,
gives c3longdouble = (3,4)
The modulus of c3 is recovered from c3 using: abs( c3 ) = 5
Argument of c3 is recovered from c3 using:
arg( c3 ) = 0.927295 radians, which is 53.1301 degrees.
```

## <a name="requirements"></a>Gereksinimler

**Üst bilgi**: \<karmaşık >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[complex Sınıfı](../standard-library/complex-class.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
