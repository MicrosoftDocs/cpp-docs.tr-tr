---
title: karmaşık&lt;uzun çift&gt;
ms.date: 11/04/2016
f1_keywords:
- std::complex<long double>
- complex<long double>
- std.complex<long double>
helpviewer_keywords:
- complex<long double> function
ms.assetid: 37591991-b385-46e9-b727-d534dbc10432
ms.openlocfilehash: 280fb4c15219b11d2325ff37a296e133810bf2b5
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68449487"
---
# <a name="complexltlong-doublegt"></a>karmaşık&lt;uzun çift&gt;

Bu açıkça özelleştirilmiş şablon sınıfı, her ikisi de **Long Double**türünde, her ikisi de karmaşık bir sayının gerçek bölümünü ve sanal parçayı temsil eden ikincisini temsil eden, her ikisi de, düzenli bir nesne çifti depolayan bir nesneyi tanımlar.

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

*_RealVal*\
Oluşturulan karmaşık sayının gerçek parçası için **Long Double** türü değeri.

*_ImagVal*\
Oluşturulan karmaşık sayının sanal parçası için **Long Double** türü değeri.

*Karmaşıksayı*\
Gerçek ve sanal parçaları oluşturulan karmaşık sayıda **Long Double** türü başlatmak için kullanılan **Double** veya **float** türünde karmaşık sayı.

## <a name="return-value"></a>Dönüş Değeri

**Uzun çift**türünde karmaşık bir sayı.

## <a name="remarks"></a>Açıklamalar

Template sınıfının `complex` , **Long Double** türündeki karmaşık bir sınıfa açık özelleştirmesi, şablon sınıfından yalnızca tanımladığı oluşturucularda farklılık gösterir. **Long Double** 'dan **float** 'e dönüştürmenin örtük olmasına izin verilir, ancak **Double** 'tan **Long Double** 'a dönüştürmenin **Açık**olması gerekir. Atama söz dizimini kullanarak tür dönüşümle başlatma, **Açık** kuralların kullanımı.

Şablon sınıfı `complex` ve üyeleri hakkında daha fazla bilgi için bkz. [Complex Class](../standard-library/complex-class.md).

**Microsoft 'a özgü**: **Uzun çift** ve **çift** türleri aynı gösterimine sahiptir, ancak farklı türlerdir. Daha fazla bilgi için bkz. [temel türler](../cpp/fundamental-types-cpp.md).

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

**Üstbilgi**: \<karmaşık >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[karmaşık sınıf](../standard-library/complex-class.md)\
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
