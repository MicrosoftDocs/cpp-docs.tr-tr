---
title: karmaşık &lt; uzun çift&gt;
ms.date: 11/04/2016
f1_keywords:
- std::complex<long double>
- complex<long double>
- std.complex<long double>
helpviewer_keywords:
- complex<long double> function
ms.assetid: 37591991-b385-46e9-b727-d534dbc10432
ms.openlocfilehash: 73027ba76d608424b1a6da346e861b10c66989fe
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87228394"
---
# <a name="complexltlong-doublegt"></a>karmaşık &lt; uzun çift&gt;

Bu açıkça özelleştirilmiş sınıf şablonu, her ikisi de, **`long double`** karmaşık bir sayının gerçek bölümünü ve sanal parçayı temsil eden ikincisini temsil eden, her ikisi de türündeki sıralı bir nesne çiftini depolayan bir nesneyi tanımlar.

## <a name="syntax"></a>Söz dizimi

```cpp
template <>
class complex<long double> {
public:
    constexpr complex(
    long double _RealVal = 0,
    long double _ImagVal = 0);

complex(
    constexpr complex<long double>& complexNum);

// rest same as class template complex
};
```

### <a name="parameters"></a>Parametreler

*_RealVal*\
**`long double`** Oluşturulan karmaşık sayının gerçek parçası için tür değeri.

*_ImagVal*\
**`long double`** Oluşturulmakta olan karmaşık sayının sanal parçasının tür değeri.

*Karmaşıksayı*\
**`double`** **`float`** Oluşturulan karmaşık bir tür türü başlatmak için gerçek ve sanal parçaları kullanılan tür veya türün karmaşık sayısı **`long double`** .

## <a name="return-value"></a>Dönüş Değeri

Karmaşık türden bir sayıdır **`long double`** .

## <a name="remarks"></a>Açıklamalar

Sınıf şablonunun açıkça `complex` bir tür karmaşık özelleştirmesi, **`long double`** sınıf şablonundan yalnızca tanımladığı oluşturucularda farklılık gösterir. Öğesinden öğesine dönüştürmenin **`long double`** **`float`** örtük olmasına izin verilir, ancak öğesinden **`double`** öğesine dönüştürmenin **`long double`** olması gerekir **`explicit`** . **`explicit`** Atama söz dizimini kullanarak tür dönüşümle başlatma kurallarını kullanma.

Sınıf şablonu ve üyeleri hakkında daha fazla bilgi için `complex` bkz. [Complex Class](../standard-library/complex-class.md).

**Microsoft 'a özgü**: **`long double`** ve **`double`** türleri aynı gösterimine sahiptir, ancak farklı türlerdir. Daha fazla bilgi için bkz. [Yerleşik türler](../cpp/fundamental-types-cpp.md).

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

**Üst bilgi**:\<complex>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[karmaşık sınıf](../standard-library/complex-class.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
