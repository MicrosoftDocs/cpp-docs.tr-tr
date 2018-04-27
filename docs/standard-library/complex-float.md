---
title: karmaşık&lt;float&gt; | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- complex/std::complex<float>
dev_langs:
- C++
helpviewer_keywords:
- complex<float> function
ms.assetid: 1178eb1e-39bd-4017-89cd-aea95f813939
caps.latest.revision: 23
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: be38630557f1c3c5a9a27b6358117456665180b0
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="complexltfloatgt"></a>karmaşık&lt;float&gt;

Her iki türdeki nesneleri sıralı bir çiftinden depolayan bir nesneyi tanımlayan **float **** ilk karmaşık sayı ve ikinci gerçek parçası temsil eden sanal bölümü temsil eden.

## <a name="syntax"></a>Sözdizimi

```cpp
template <>
class complex<float> {
public:
    constexpr complex(
    float _RealVal = 0,
    float _ImagVal = 0);

constexpr complex(
    const complex<float>& complexNum);

constexpr complex(
    const complex<double>& complexNum);

constexpr complex(
    const complex<long double>& complexNum);
// rest same as template class complex
};
```

### <a name="parameters"></a>Parametreler

`_RealVal` Türü değeri **float** için yapılandırılan bir karmaşık sayı gerçek parçası.

`_ImagVal` Türü değeri **float** yapılandırılan karmaşık sayı sanal kısmı için.

`complexNum` Karmaşık sayı türü **çift** veya türünde `long double` , gerçek ve sanal bölümleri türü bir karmaşık sayı başlatmak için kullanılan **float** yapılandırılan.

## <a name="return-value"></a>Dönüş Değeri

Türü bir karmaşık sayı **float**.

## <a name="remarks"></a>Açıklamalar

Şablon sınıfı türü karmaşık bir sınıfa karmaşık açık alt uzmanlaşması **float** tanımladığı oluşturucular şablon sınıfında farklıdır. Dönüştürme işlemi **float** için **çift** dolaylı olarak izin verilir ancak daha az güvenli bir dönüştürme **float** için `long double` olması gereken  **Açık**. Kullanımını **açık** başlatma ile atama sözdizimini kullanarak tür dönüştürme kuralları.

Şablon sınıfı hakkında daha fazla bilgi için `complex`, bkz: [karmaşık sınıfı](../standard-library/complex-class.md). Şablon sınıfının üye listesi `complex`, bkz.

## <a name="example"></a>Örnek

```cpp
// complex_comp_flt.cpp
// compile with: /EHsc
#include <complex>
#include <iostream>

int main( )
{
   using namespace std;
   double pi = 3.14159265359;

   // The first constructor specifies real & imaginary parts
   complex <float> c1 ( 4.0 , 5.0 );
   cout << "Specifying initial real & imaginary parts,\n"
        << " as type float gives c1 = " << c1 << endl;

   // The second constructor initializes values of the real &
   // imaginary parts using those of complex number of type double
   complex <double> c2double ( 1.0 , 3.0 );
   complex <float> c2float ( c2double );
   cout << "Implicit conversion from type double to type float,"
        << "\n gives c2float = " << c2float << endl;

   // The third constructor initializes values of the real &
   // imaginary parts using those of a complex number
   // of type long double
   complex <long double> c3longdouble ( 3.0 , 4.0 );
   complex <float> c3float ( c3longdouble );
   cout << "Explicit conversion from type long double to type float,"
        << "\n gives c3float = " << c3float << endl;

   // The modulus and argument of a complex number can be recovered
   double absc3 = abs ( c3float);
   double argc3 = arg ( c3float);
   cout << "The modulus of c3 is recovered from c3 using: abs ( c3 ) = "
        << absc3 << endl;
   cout << "Argument of c3 is recovered from c3 using:\n arg ( c3 ) = "
        << argc3 << " radians, which is " << argc3 * 180 / pi
        << " degrees." << endl;
}
\* Output:
Specifying initial real & imaginary parts,
 as type float gives c1 = (4,5)
Implicit conversion from type double to type float,
 gives c2float = (1,3)
Explicit conversion from type long double to type float,
 gives c3float = (3,4)
The modulus of c3 is recovered from c3 using: abs ( c3 ) = 5
Argument of c3 is recovered from c3 using:
 arg ( c3 ) = 0.927295 radians, which is 53.1301 degrees.
*\
```

## <a name="requirements"></a>Gereksinimler

**Üstbilgi**: \<karmaşık >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[complex Sınıfı](../standard-library/complex-class.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
