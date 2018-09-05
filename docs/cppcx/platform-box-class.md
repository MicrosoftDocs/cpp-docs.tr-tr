---
title: Platform::Box sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Box
dev_langs:
- C++
ms.assetid: b3d7ea37-e98a-4fbc-80b0-ad35e50250c6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7def63199666a9dba0a1628031129ce584e0fcec
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43753535"
---
# <a name="platformbox-class"></a>Platform::Box sınıfı
Bir değer türü etkinleştirir `Windows::Foundation::DateTime` ya da bir skalar türü gibi `int` depolanması için bir `Platform::Object` türü. Genellikle kullanmak için gerekli değildir `Box` açıkça kutulama örtük olarak ne zaman, bir değer türüne olur çünkü `Object^`.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
ref class Box abstract;  
```  
  ### <a name="remarks"></a>Açıklamalar  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** vccorlib.h  
  
 **Namespace:** platformu
|Üye|Açıklama|  
|------------|-----------------|
|[Kutusu](#ctor)|Oluşturur bir `Box` belirtilen türde bir değer kapsülleyen.|
|[işleci kutusunda&lt;const T&gt;^](#box-const-t)|Kutulama dönüşümlerse sağlayan bir `const` değer sınıfının `T` veya `enum` sınıfı `T` için `Box<T>`.|
|[işleci kutusunda&lt;const volatile T&gt;^](#box-const-volatile-t)|Kutulama dönüşümlerse sağlayan bir `const volatile` değer sınıfının `T` veya `enum` türü `T` için `Box<T>`. |
|[işleci kutusunda&lt;T&gt;^](#box-t)|Değer sınıfından kutulama dönüştürmeler sağlar `T` için `Box<T>`.|
|[işleci kutusunda&lt;geçici T&gt;^](#box-volatile-t)|Kutulama dönüşümlerse sağlayan bir `volatile` değer sınıfının `T` veya `enum` türü `T` için `Box<T>`.|
|[Box::operator T](#t)|Değer sınıfından kutulama dönüştürmeler sağlar `T` veya `enum` sınıfı `T` için `Box<T>`.| 
## <a name="ctor"></a> Box::Box Oluşturucusu
Oluşturur bir `Box` belirtilen türde bir değer kapsülleyen. | |[ Özellik değeri](#value)| İçinde kapsüllenir değeri döndürür `Box` nesne. |  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
Box(T valueArg);  
```  
  
### <a name="parameters"></a>Parametreler  
 `valueArg`  
 Kutu içinde değerinin türü — örneğin, `int`, `bool`, `float64`, `DateTime`.  
  

## <a name="box-const-t"></a> Box::operator kutusu&lt;const T&gt;^ işleci
Kutulama dönüşümlerse sağlayan bir `const` değer sınıfının `T` veya `enum` sınıfı `T` için `Box<T>`.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
operator Box<const T>^(const T valueType);  
```  
  
### <a name="parameters"></a>Parametreler  
 `T`  
 Hiçbir değer sınıfı, değer yapı veya sabit listesi türü. Yerleşik türleri içeren [varsayılan ad alanı](../cppcx/default-namespace.md).  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `Platform::Box<T>^` orijinal değeri temsil eden örneği kutu içinde bir başvuru sınıfı.  
  
## <a name="box-const-volatile-t"></a> Box::operator kutusu&lt;const volatile T&gt;^ işleci
Kutulama dönüşümlerse sağlayan bir `const volatile` değer sınıfının `T` veya `enum` türü `T` için `Box<T>`.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
operator Box<const volatile T>^(const volatile T valueType);  
```  
  
### <a name="parameters"></a>Parametreler  
 `T`  
 Tüm sabit listesi türü, değer sınıfı veya değer yapısı. Yerleşik türleri içeren [varsayılan ad alanı](../cppcx/default-namespace.md).  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `Platform::Box<T>^` orijinal değeri temsil eden örneği kutu içinde bir başvuru sınıfı.  
  
## <a name="box-t"></a> Box::operator kutusu&lt;T&gt;^ işleci
Değer sınıfından kutulama dönüştürmeler sağlar `T` için `Box<T>`.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
operator Box<const T>^(const T valueType);  
```  
  
### <a name="parameters"></a>Parametreler  
 `T`  
 Tüm sabit listesi türü, değer sınıfı veya değer yapısı. Yerleşik türleri içeren [varsayılan ad alanı](../cppcx/default-namespace.md).  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `Platform::Box<T>^` orijinal değeri temsil eden örneği kutu içinde bir başvuru sınıfı.  
  
## <a name="box-volatile-t"></a> Box::operator kutusu&lt;geçici T&gt;^ işleci
Kutulama dönüşümlerse sağlayan bir `volatile` değer sınıfının `T` veya `enum` türü `T` için `Box<T>`.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
operator Box<volatile T>^(volatile T valueType);  
```  
  
### <a name="parameters"></a>Parametreler  
 `T`  
 Tüm sabit listesi türü, değer sınıfı veya değer yapısı. Yerleşik türleri içeren [varsayılan ad alanı](../cppcx/default-namespace.md).  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `Platform::Box<T>^` orijinal değeri temsil eden örneği kutu içinde bir başvuru sınıfı.  
  
## <a name="t"></a>  Box::operator T işleci
Değer sınıfından kutulama dönüştürmeler sağlar `T` veya `enum` sınıfı `T` için `Box<T>`.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
operator Box<T>^(T valueType);  
```  
  
### <a name="parameters"></a>Parametreler  
 `T`  
 Tüm sabit listesi türü, değer sınıfı veya değer yapısı. Yerleşik türleri içeren [varsayılan ad alanı](../cppcx/default-namespace.md).  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `Platform::Box<T>^` orijinal değeri temsil eden örneği kutu içinde bir başvuru sınıfı.  
  

## <a name="value"></a> Box::Value özelliği
İçinde kapsüllenir değeri döndürür `Box` nesne.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
virtual property T Value{  
   T get();  
}  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu kutu önce ilk olarak olduğu gibi aynı türde kutulanmış değer döndürür.  
  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Platform ad alanı](../cppcx/platform-namespace-c-cx.md)   
 [Kutulama](../cppcx/boxing-c-cx.md)