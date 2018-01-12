---
title: "chrono değişmez değerleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 1a9e23b1-256f-4570-8226-5fa7364fb032
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f23208b916c190e2fbcdcd0db4ce0709485795ff
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="chrono-literals"></a>chrono değişmez değerleri
(C ++ 14) \<Chrono > Üstbilgi tanımlar 12 [kullanıcı tanımlı değişmez değerler](../cpp/user-defined-literals-cpp.md) saat, dakika, saniye, milisaniye, mikrosaniye ve nanosaniye temsil eden değişmez değerleri kullanarak kolaylaştırmak için. Her kullanıcı tanımlı değişmez değeri bir Entegral ve bir kayan nokta aşırı vardır. Değişmez değerler std::chrono kapsamda olduğunda bu kapsam içine otomatik olarak getirilene literals::chrono_literals satır içi ad alanında tanımlanır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
inline namespace literals {  
    inline namespace chrono_literals {  
 // return integral hours  
    constexpr chrono::hours operator"" h(unsigned long long Val);

 // return floating-point hours  
    constexpr chrono::duration<double, ratio<3600>> operator"" h(long double Val);

 // return integral minutes  
    constexpr chrono::minutes(operator"" min)(unsigned long long Val);

 // return floating-point minutes  
    constexpr chrono::duration<double, ratio<60>>(operator"" min)(long double Val);

 // return integral seconds  
    constexpr chrono::seconds operator"" s(unsigned long long Val);

 // return floating-point seconds  
    constexpr chrono::duration<double> operator"" s(long double Val);

 // return integral milliseconds  
    constexpr chrono::milliseconds operator"" ms(unsigned long long Val);

 // return floating-point milliseconds  
    constexpr chrono::duration<double, milli> operator"" ms(long double Val);

 // return integral microseconds      
    constexpr chrono::microseconds operator"" us(unsigned long long Val);

 // return floating-point microseconds  
    inline constexpr chrono::duration<double, micro> operator"" us(long double Val);

 // return integral nanoseconds  
    inline constexpr chrono::nanoseconds operator"" ns(unsigned long long Val);

 // return floating-point nanoseconds  
    constexpr chrono::duration<double, nano> operator"" ns(long double Val);

 }// inline namespace chrono_literals  
}// inline namespace literals  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Ele değişmez değerleri bir `long long` bağımsız değişkeni bir değer veya karşılık gelen türünü döndürür. Dönüş bağımsız değişkeni bir kayan ele değişmez değerleri noktası bir [süresi](../standard-library/duration-class.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekler chrono değişmez değerleri kullanmak nasıl sow.  
  
```cpp  
constexpr auto day = 24h;  
constexpr auto week = 24h* 7;  
constexpr auto my_duration_unit = 108ms;  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Üstbilgi**: \<chrono >  
  
 **Namespace**: std::literals::chrono_literals  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<chrono >](../standard-library/chrono.md)

