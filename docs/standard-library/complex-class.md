---
title: "Complex sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- complex/std::complex::value_type
- complex/std::complex::imag
- complex/std::complex::real
dev_langs: C++
helpviewer_keywords:
- std::complex [C++], value_type
- std::complex [C++], imag
- std::complex [C++], real
ms.assetid: d6492e1c-5eba-4bc5-835b-2a88001a5868
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a4fe9411d306e08f16df138786d6d55e4ea1647c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="complex-class"></a>complex Sınıfı
Şablon sınıfı türünde iki nesnelerini depolayan bir nesne tanımlar **türü**, bir karmaşık sayı ve bir sanal bölümünü temsil eden gerçek bölümünü temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
 
template <class   
Type>  
class complex  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Sınıfın bir nesnesi **türü**:  
  
-   Ortak varsayılan oluşturucu, yıkıcı, kopya oluşturucu ve atama işleci geleneksel davranışı sahiptir.  
  
-   Geleneksel davranışı böyle değerlerle dönüştürme yazın veya tamsayı veya kayan nokta değerlerini atanabilir.  
  
-   Aritmetik işleçler ve geleneksel davranışı kayan nokta türleri için tanımlanan gerektiği gibi matematik işlevleri tanımlar.  
  
 Özellikle, kopya oluşturma ve atama tarafından izlenen varsayılan yapım arasında hiçbir küçük farklılıklar olabilir. Sınıfındaki nesneler üzerinde işlemler hiçbiri **türü** özel durumlar oluşturma.  
  
 Şablon sınıfının karmaşık açık özelleştirmeleri üç kayan nokta türleri için mevcut. Bu uygulamada, diğer herhangi türde bir değer **türü** için typecast **çift** asıl hesaplamalar için ile **çift** saklı nesnesine atanmış sonucu tür **türü**`.`  
  
### <a name="constructors"></a>Oluşturucular  
  
|||  
|-|-|  
|[karmaşık](#complex)|Karmaşık sayıyı belirtilen gerçek ve sanal bölümleri içeren veya başka bir karmaşık sayıyı bir kopyasını oluşturur.|  
  
### <a name="typedefs"></a>Tür tanımları  
  
|||  
|-|-|  
|[value_type](#value_type)|Karmaşık bir sayının gerçek ve sanal bölümleri göstermek için kullanılan veri türünü temsil eden tür.|  
  
### <a name="member-functions"></a>Üye İşlevleri  
  
|||  
|-|-|  
|[imag](#imag)|Karmaşık bir sayının sanal bileşeni ayıklar.|  
|[Gerçek](#real)|Karmaşık bir sayının gerçek bileşen ayıklar.|  
  
### <a name="operators"></a>İşleçler  
  
|||  
|-|-|  
|[işleç * =](#op_star_eq)|Bir hedef karmaşık sayı karmaşık sayıyı gerçek ve sanal bölümlerini olduğu gibi aynı türden olması veya karmaşık olabilir bir faktörüyle tarafından çarpar.|  
|[+= işleci](#op_add_eq)|Bir hedef karmaşık sayıya bir numara ekler, eklenen sayı karmaşık olabilir veya aynı türde gerçek ve sanal için bunu eklendiği karmaşık sayı bölümlerdir.|  
|[-= işleci](#operator-_eq)|Bir hedef karmaşık sayı arasında bir sayı çıkarır, çıkarılır sayı karmaşık olabilir veya aynı türde gerçek ve sanal için bunu eklendiği karmaşık sayı bölümlerdir.|  
|[/ = işleci](#op_div_eq)|Bir hedef karmaşık sayı, karmaşık olabilir veya karmaşık sayıyı gerçek ve sanal bölümlerini olduğu gibi aynı türden olması bölen tarafından böler.|  
|[işleç =](#op_eq)|Burada atanmış numarası karmaşık olabilir bir hedef karmaşık sayı veya aynı türde bir sayı, atandığı karmaşık sayı gerçek ve sanal bölümlerini atar.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Üstbilgi**: \<karmaşık >  
  
 **Namespace:** std  
  
##  <a name="complex"></a>Complex::Complex  
 Karmaşık sayıyı belirtilen gerçek ve sanal bölümleri içeren veya başka bir karmaşık sayıyı bir kopyasını oluşturur.  
  
```  
constexpr complex(
    const T& 
    _RealVal = 0  ,   
    const T& 
    _ImagVal = 0);

    template <class Other>  
constexpr complex(
    const complex<Other>& 
    complexNum);
```  
  
### <a name="parameters"></a>Parametreler  
 `_RealVal`  
 Yapılandırılan bir karmaşık sayı başlatmak için kullanılan gerçek bölüm değeri.  
  
 `_ImagVal`  
 Yapılandırılan bir karmaşık sayı başlatmak için kullanılan sanal bölüm değeri.  
  
 `complexNum`  
 Karmaşık, gerçek ve sanal bölümleri yapılandırılan karmaşık sayı başlatmak için kullanılan sayı.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk Oluşturucu saklı başlatır _ gerçek parçası *RealVal* ve depolanan sanal bölümü \_ *Imagval*. İkinci oluşturucu saklı başlatır parçası gerçek `complexNum` **.real**() ve depolanan sanal bölümü `complexNum` **.imag**().  
  
 Çevirmen üye şablon işlevleri, şablon desteklemiyorsa, bu uygulama:  
  
```  
template <class Other>  
complex(const complex<Other>& right);
```  
  
 ile değiştirilmiştir:  
  
```  
 
complex(const complex& right);
```  
  
 kopya Oluşturucu olduğu.  
  
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
   complex <double> c1 ( 4.0 , 5.0 );  
   cout << "Specifying initial real & imaginary parts,"  
        << "c1 = " << c1 << endl;   
  
   // The second constructor initializes values of the real &  
   // imaginary parts using those of another complex number  
   complex <double> c2 ( c1 );  
   cout << "Initializing with the real and imaginary parts of c1,"  
        << " c2 = " << c2 << endl;   
  
   // Complex numbers can be initialized in polar form  
   // but will be stored in Cartesian form  
   complex <double> c3 ( polar ( sqrt( (double)8 ) , pi / 4 ) );  
   cout << "c3 = polar ( sqrt ( 8 ) , pi / 4 ) = " << c3 << endl;   
  
   // The modulus and argument of a complex number can be recovered  
   double absc3 = abs ( c3 );  
   double argc3 = arg ( c3 );  
   cout << "The modulus of c3 is recovered from c3 using: abs ( c3 ) = "  
        << absc3 << endl;  
   cout << "Argument of c3 is recovered from c3 using:\n arg ( c3 ) = "  
        << argc3 << " radians, which is " << argc3 * 180 / pi  
        << " degrees." << endl;  
}  
```  
  
##  <a name="imag"></a>Complex::imag  
 Karmaşık bir sayının sanal bileşeni ayıklar.  
  
```  
T imag() const;

 
T imag(const T& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `right`  
 Ayıklanacak sanal değeri olan bir karmaşık sayı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Karmaşık sayıyı sanal parçası.  
  
### <a name="remarks"></a>Açıklamalar  
 Karmaşık sayıyı için *+ bi*, sanal bölümü ya da bileşen *Im(a + bi) = b.*  
  
### <a name="example"></a>Örnek  
  
```cpp  
// complex_imag.cpp  
// compile with: /EHsc  
#include <complex>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   complex <double> c1 ( 4.0 , 3.0 );  
   cout << "The complex number c1 = " << c1 << endl;  
  
   double dr1 = c1.real ( );  
   cout << "The real part of c1 is c1.real ( ) = "  
        << dr1 << "." << endl;  
  
   double di1 = c1.imag ( );  
   cout << "The imaginary part of c1 is c1.imag ( ) = "  
        << di1 << "." << endl;  
}  
```  
  
```Output  
The complex number c1 = (4,3)  
The real part of c1 is c1.real ( ) = 4.  
The imaginary part of c1 is c1.imag ( ) = 3.  
```  
  
##  <a name="op_star_eq"></a>Complex::operator * =  
 Bir hedef karmaşık sayı karmaşık sayıyı gerçek ve sanal bölümlerini olduğu gibi aynı türden olması veya karmaşık olabilir bir faktörüyle tarafından çarpar.  
  
```  
template <class Other>  
complex& operator*=(const complex<Other>& right);

complex<Type>& operator*=(const Type& right);

complex<Type>& operator*=(const complex<Type>& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `right`  
 Karmaşık sayıyı veya aynı türde hedef karmaşık sayının parametre olarak bir sayı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Parametre olarak belirtilen sayıyla çarpılan karmaşık sayı.  
  
### <a name="remarks"></a>Açıklamalar  
 Böylece basit aritmetik işlemler belirli bir biçimde veri dönüştürme olmadan çalıştırılabilir işlemi aşırı yüklendi.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// complex_op_me.cpp  
// compile with: /EHsc  
#include <complex>  
#include <iostream>  
  
int main() {  
   using namespace std;  
   double pi = 3.14159265359;  
  
   // Example of the first member function  
   // type complex<double> multiplied by type complex<double>  
   complex <double> cl1 ( polar ( 3.0 , pi / 6 ) );  
   complex <double> cr1 ( polar ( 2.0 , pi / 3 ) );  
   cout << "The left-side complex number is cl1 = " << cl1 << endl;  
   cout << "The right-side complex number is cr1 = " << cr1 << endl;  
  
   complex <double> cs1 = cl1 * cr1;  
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
   complex <double> cl2 ( polar ( 3.0 , pi / 6 ) );  
   double cr2 = 5.0;  
   cout << "The left-side complex number is cl2 = " << cl2 << endl;  
   cout << "The right-side complex number is cr2 = " << cr2 << endl;  
  
   complex <double> cs2 = cl2 * cr2;  
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
  
##  <a name="op_add_eq"></a>Complex::operator +=  
 Bir hedef karmaşık sayıya bir numara ekler, eklenen sayı karmaşık olabilir veya aynı türde gerçek ve sanal için bunu eklendiği karmaşık sayı bölümlerdir.  
  
```  
template <class Other>  
complex<Type>& operator+=(const complex<Other>& right);

complex<Type>& operator+=(const Type& right);

complex<Type>& operator+=(const complex<Type>& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `right`  
 Karmaşık sayıyı veya aynı türde hedef karmaşık sayının parametre olarak bir sayı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Eklenen bir parametre olarak belirtilen sayı olan bir karmaşık sayı.  
  
### <a name="remarks"></a>Açıklamalar  
 Böylece basit aritmetik işlemler belirli bir biçimde veri dönüştürme olmadan çalıştırılabilir işlemi aşırı yüklendi.  
  
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
   complex <double> cl1 ( 3.0 , 4.0 );  
   complex <double> cr1 ( 2.0 , -1.0 );  
   cout << "The left-side complex number is cl1 = " << cl1 << endl;  
   cout << "The right-side complex number is cr1 = " << cr1 << endl;  
  
   complex <double> cs1 = cl1 + cr1;  
   cout << "The sum of the two complex numbers is: cs1 = cl1 + cr1 = "  
        << cs1 << endl;  
  
   // This is equivalent to the following operation  
   cl1 += cr1;  
   cout << "The complex number cr1 added to the complex number cl1 is:"  
        << "\n cl1 += cr1 = " << cl1 << endl;  
  
   double abscl1 = abs ( cl1 );  
   double argcl1 = arg ( cl1 );  
   cout << "The modulus of cl1 is: " << abscl1 << endl;  
   cout << "The argument of cl1 is: "<< argcl1 << " radians, which is "   
        << argcl1 * 180 / pi << " degrees." << endl << endl;   
  
   // Example of the second member function  
   // type double added to type complex<double>  
   complex <double> cl2 ( -2 , 4 );  
   double cr2 =5.0;  
   cout << "The left-side complex number is cl2 = " << cl2 << endl;  
   cout << "The right-side complex number is cr2 = " << cr2 << endl;  
  
   complex <double> cs2 = cl2 + cr2;  
   cout << "The sum of the two complex numbers is: cs2 = cl2 + cr2 = "   
        << cs2 << endl;  
  
   // This is equivalent to the following operation  
   cl2 += cr2;  
   cout << "The complex number cr2 added to the complex number cl2 is:"  
        << "\n cl2 += cr2 = " << cl2 << endl;  
  
   double abscl2 = abs ( cl2 );  
   double argcl2 = arg ( cl2 );  
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
  
##  <a name="complex__operator-_eq"></a>Complex::operator-=  
 Bir hedef karmaşık sayı arasında bir sayı çıkarır, çıkarılır sayı karmaşık olabilir veya aynı türde gerçek ve sanal için bunu eklendiği karmaşık sayı bölümlerdir.  
  
```  
template <class Other>  
complex<Type>& operator-=(const complex<Other>& complexNum);

complex<Type>& operator-=(const Type& _RealPart);

complex<Type>& operator-=(const complex<Type>& complexNum);
```  
  
### <a name="parameters"></a>Parametreler  
 `complexNum`  
 Hedef karmaşık numarasından çıkarılır için bir karmaşık sayı.  
  
 `_RealPart`  
 Hedef karmaşık numarasından çıkarılır için bir gerçek sayı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bundan çıkarılır bir parametre olarak belirtilen sayı olan bir karmaşık sayı.  
  
### <a name="remarks"></a>Açıklamalar  
 Böylece basit aritmetik işlemler belirli bir biçimde veri dönüştürme olmadan çalıştırılabilir işlemi aşırı yüklendi.  
  
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
   complex <double> cl1 ( 3.0 , 4.0 );  
   complex <double> cr1 ( 2.0 , -1.0 );  
   cout << "The left-side complex number is cl1 = " << cl1 << endl;  
   cout << "The right-side complex number is cr1 = " << cr1 << endl;  
  
   complex <double> cs1 = cl1 - cr1;  
   cout << "The difference between the two complex numbers is:"  
        << "\n cs1 = cl1 - cr1 = " << cs1 << endl;  
  
   // This is equivalent to the following operation  
   cl1 -= cr1;  
   cout << "Complex number cr1 subtracted from complex number cl1 is:"  
        << "\n cl1 -= cr1 = " << cl1 << endl;  
  
   double abscl1 = abs ( cl1 );  
   double argcl1 = arg ( cl1 );  
   cout << "The modulus of cl1 is: " << abscl1 << endl;  
   cout << "The argument of cl1 is: "<< argcl1 << " radians, which is "   
        << argcl1 * 180 / pi << " degrees." << endl << endl;   
  
   // Example of the second member function  
   // type double subtracted from type complex<double>  
   complex <double> cl2 ( 2.0 , 4.0 );  
   double cr2 = 5.0;  
   cout << "The left-side complex number is cl2 = " << cl2 << endl;  
   cout << "The right-side complex number is cr2 = " << cr2 << endl;  
  
   complex <double> cs2 = cl2 - cr2;  
   cout << "The difference between the two complex numbers is:"  
        << "\n cs2 = cl2 - cr2 = " << cs2 << endl;  
  
   // This is equivalent to the following operation  
   cl2  -= cr2;  
   cout << "Complex number cr2 subtracted from complex number cl2 is:"  
        << "\n cl2 -= cr2 = " << cl2 << endl;  
  
   double abscl2 = abs ( cl2 );  
   double argcl2 = arg ( cl2 );  
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
  
##  <a name="op_div_eq"></a>Complex::operator / =  
 Bir hedef karmaşık sayı, karmaşık olabilir veya karmaşık sayıyı gerçek ve sanal bölümlerini olduğu gibi aynı türden olması bölen tarafından böler.  
  
```  
template <class Other>  
complex<Type>& operator/=(const complex<Other>& complexNum);

complex<Type>& operator/=(const Type& _RealPart);

complex<Type>& operator/=(const complex<Type>& complexNum);
```  
  
### <a name="parameters"></a>Parametreler  
 `complexNum`  
 Hedef karmaşık numarasından çıkarılır için bir karmaşık sayı.  
  
 `_RealPart`  
 Hedef karmaşık numarasından çıkarılır için bir gerçek sayı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Parametre olarak belirtilen numarasına göre bölünmüş bir karmaşık sayı.  
  
### <a name="remarks"></a>Açıklamalar  
 Böylece basit aritmetik işlemler belirli bir biçimde veri dönüştürme olmadan çalıştırılabilir işlemi aşırı yüklendi.  
  
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
   complex <double> cl1 ( polar (3.0 , pi / 6 ) );  
   complex <double> cr1 ( polar (2.0 , pi / 3 ) );  
   cout << "The left-side complex number is cl1 = " << cl1 << endl;  
   cout << "The right-side complex number is cr1 = " << cr1 << endl;  
  
   complex <double> cs1 = cl1 / cr1;  
   cout << "The quotient of the two complex numbers is: cs1 = cl1 /cr1 = "  
        << cs1 << endl;  
  
   // This is equivalent to the following operation  
   cl1 /= cr1;  
   cout << "Quotient of two complex numbers is also: cl1 /= cr1 = "  
        << cl1 << endl;  
  
   double abscl1 = abs ( cl1 );  
   double argcl1 = arg ( cl1 );  
   cout << "The modulus of cl1 is: " << abscl1 << endl;  
   cout << "The argument of cl1 is: "<< argcl1 << " radians, which is "   
        << argcl1 * 180 / pi << " degrees." << endl << endl;   
  
   // Example of the second member function  
   // type complex<double> divided by type double  
   complex <double> cl2 ( polar (3.0 , pi / 6 ) );  
   double cr2 =5;  
   cout << "The left-side complex number is cl2 = " << cl2 << endl;  
   cout << "The right-side complex number is cr2 = " << cr2 << endl;  
  
   complex <double> cs2 = cl2 / cr2;  
   cout << "The quotient of the two complex numbers is: cs2 /= cl2 cr2 = "   
        << cs2 << endl;  
  
   // This is equivalent to the following operation  
   cl2 /= cr2;  
   cout << "Quotient of two complex numbers is also: cl2 = /cr2 = "  
        << cl2 << endl;  
  
   double abscl2 = abs ( cl2 );  
   double argcl2 = arg ( cl2 );  
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
  
##  <a name="op_eq"></a>Complex::operator =  
 Burada atanmış numarası karmaşık olabilir bir hedef karmaşık sayı veya aynı türde bir sayı, atandığı karmaşık sayı gerçek ve sanal bölümlerini atar.  
  
```  
template <class Other>  
complex<Type>& operator=(const complex<Other>& right);

complex<Type>& operator=(const Type& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `right`  
 Karmaşık sayıyı veya aynı türde hedef karmaşık sayının parametre olarak bir sayı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Parametre olarak belirtilen sayı atanmış bir karmaşık sayı.  
  
### <a name="remarks"></a>Açıklamalar  
 Böylece basit aritmetik işlemler belirli bir biçimde veri dönüştürme olmadan çalıştırılabilir işlemi aşırı yüklendi.  
  
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
   complex <double> cl1 ( 3.0 , 4.0 );  
   complex <double> cr1 ( 2.0 , -1.0 );  
   cout << "The left-side complex number is cl1 = " << cl1 << endl;  
   cout << "The right-side complex number is cr1 = " << cr1 << endl;  
  
   cl1  = cr1;  
   cout << "The complex number cr1 assigned to the complex number cl1 is:"  
        << "\n cl1 = cr1 = " << cl1 << endl;  
  
   // Example of the second member function  
   // type double assigned to type complex<double>  
   complex <double> cl2 ( -2 , 4 );  
   double cr2 =5.0;  
   cout << "The left-side complex number is cl2 = " << cl2 << endl;  
   cout << "The right-side complex number is cr2 = " << cr2 << endl;  
  
   cl2 = cr2;  
   cout << "The complex number cr2 assigned to the complex number cl2 is:"  
        << "\n cl2 = cr2 = " << cl2 << endl;  
  
   cl2 = complex<double>(3.0, 4.0);  
   cout << "The complex number (3, 4) assigned to the complex number cl2 is:"  
        << "\n cl2 = " << cl2 << endl;  
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
  
##  <a name="real"></a>Complex::Real  
 Alır veya karmaşık bir sayının gerçek bileşen ayarlar.  
  
```  
constexpr T real() const;

 
T real(const T& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `right`  
 Ayıklanacak gerçek değeri olan bir karmaşık sayı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Karmaşık sayıyı gerçek parçası.  
  
### <a name="remarks"></a>Açıklamalar  
 Karmaşık sayıyı için *+ bi*, gerçek bölüm ya da bileşen *Re(a + bi) = bir.*  
  
### <a name="example"></a>Örnek  
  
```cpp  
// complex_class_real.cpp  
// compile with: /EHsc  
#include <complex>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   complex <double> c1 ( 4.0 , 3.0 );  
   cout << "The complex number c1 = " << c1 << endl;  
  
   double dr1 = c1.real ( );  
   cout << "The real part of c1 is c1.real ( ) = "  
        << dr1 << "." << endl;  
  
   double di1 = c1.imag ( );  
   cout << "The imaginary part of c1 is c1.imag ( ) = "  
        << di1 << "." << endl;  
}  
```  
  
```Output  
The complex number c1 = (4,3)  
The real part of c1 is c1.real ( ) = 4.  
The imaginary part of c1 is c1.imag ( ) = 3.  
```  
  
##  <a name="value_type"></a>Complex::value_type  
 Karmaşık bir sayının gerçek ve sanal bölümleri göstermek için kullanılan veri türünü temsil eden tür.  
  
```  
 
typedef Type value_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 `value_type`sınıfı için eş anlamlı karmaşıktır **türü** şablon parametresi.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// complex_valuetype.cpp  
// compile with: /EHsc  
#include <complex>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   complex <double>::value_type a = 3, b = 4;  
  
   complex <double> c1 ( a , b );  
   cout << "Specifying initial real & imaginary parts"  
      << "\nof type value_type: "  
      << "c1 = " << c1 << "." << endl;  
}  
```  
  
```Output  
Specifying initial real & imaginary parts  
of type value_type: c1 = (3,4).  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [karmaşık üyeleri](http://msdn.microsoft.com/en-us/d5c4466c-43a0-4817-aca1-9a5d492dae28)   
 [C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)

