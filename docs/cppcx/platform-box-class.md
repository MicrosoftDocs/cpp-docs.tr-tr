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
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 59fcdf177f942dd598348654b366e0c0f42e916b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33091686"
---
# <a name="platformbox-class"></a>Platform::Box sınıfı
Değer türü gibi etkinleştirir `Windows::Foundation::DateTime` veya skaler bir tür gibi `int` depolanması için bir `Platform::Object` türü. Genellikle kullanmak için gerekli değildir `Box` açıkça kutulama örtük olarak bir değer türüne dönüştürme ne zaman olacağını çünkü `Object^`.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
ref class Box abstract;  
```  
  ### <a name="remarks"></a>Açıklamalar  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** vccorlib.h  
  
 **Namespace:** Platform
|Üye|Açıklama|  
|------------|-----------------|
|[Kutusu](#ctor)|Oluşturur bir `Box` belirtilen türde bir değer kapsülleyen.|
|[işleç kutusunu&lt;const T&gt;^](#box-const-t)|Kutulama dönüşümleri gelen etkinleştirir bir `const` değer sınıfının `T` veya `enum` sınıfı `T` için `Box<T>`.|
|[işleç kutusunu&lt;const volatile T&gt;^](#box-const-volatile-t)|Kutulama dönüşümleri gelen etkinleştirir bir `const volatile` değer sınıfının `T` veya `enum` türü `T` için `Box<T>`. |
|[işleç kutusunu&lt;T&gt;^](#box-t)|Kutulama dönüşümleri değeri sınıfından etkinleştirir `T` için `Box<T>`.|
|[işleç kutusunu&lt;volatile T&gt;^](#box-volatile-t)|Kutulama dönüşümleri gelen etkinleştirir bir `volatile` değer sınıfının `T` veya `enum` türü `T` için `Box<T>`.|
|[Box::operator T](#t)|Kutulama dönüşümleri değeri sınıfından etkinleştirir `T` veya `enum` sınıfı `T` için `Box<T>`.| 
## <a name="ctor"></a> Box::Box Oluşturucusu
Oluşturur bir `Box` belirtilen türde bir değer kapsülleyen. | |[ Özellik değeri](#value)| İçinde kapsüllenir değeri döndürür `Box` nesnesi. |  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
Box(T valueArg);  
```  
  
### <a name="parameters"></a>Parametreler  
 `valueArg`  
 Kutulu değerinin türü — örneğin, `int`, `bool`, `float64`, `DateTime`.  
  

## <a name="box-const-t"></a> Box::operator kutusunu&lt;const T&gt;^ işleci
Kutulama dönüşümleri gelen etkinleştirir bir `const` değer sınıfının `T` veya `enum` sınıfı `T` için `Box<T>`.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
operator Box<const T>^(const T valueType);  
```  
  
### <a name="parameters"></a>Parametreler  
 `T`  
 Hiçbir değer sınıfı, değer yapısı ya da enum türü. Yerleşik türler içeren [varsayılan ad alanı](../cppcx/default-namespace.md).  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `Platform::Box<T>^` özgün değeri temsil eden örneği Kutulu ref sınıfta.  
  
## <a name="box-const-volatile-t"></a> Box::operator kutusunu&lt;const volatile T&gt;^ işleci
Kutulama dönüşümleri gelen etkinleştirir bir `const volatile` değer sınıfının `T` veya `enum` türü `T` için `Box<T>`.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
operator Box<const volatile T>^(const volatile T valueType);  
```  
  
### <a name="parameters"></a>Parametreler  
 `T`  
 Tüm numaralandırma türü, değer sınıfı ya da değer yapısı. Yerleşik türler içeren [varsayılan ad alanı](../cppcx/default-namespace.md).  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `Platform::Box<T>^` özgün değeri temsil eden örneği Kutulu ref sınıfta.  
  
## <a name="box-t"></a> Box::operator kutusunu&lt;T&gt;^ işleci
Kutulama dönüşümleri değeri sınıfından etkinleştirir `T` için `Box<T>`.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
operator Box<const T>^(const T valueType);  
```  
  
### <a name="parameters"></a>Parametreler  
 `T`  
 Tüm numaralandırma türü, değer sınıfı ya da değer yapısı. Yerleşik türler içeren [varsayılan ad alanı](../cppcx/default-namespace.md).  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `Platform::Box<T>^` özgün değeri temsil eden örneği Kutulu ref sınıfta.  
  
## <a name="box-volatile-t"></a> Box::operator kutusunu&lt;volatile T&gt;^ işleci
Kutulama dönüşümleri gelen etkinleştirir bir `volatile` değer sınıfının `T` veya `enum` türü `T` için `Box<T>`.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
operator Box<volatile T>^(volatile T valueType);  
```  
  
### <a name="parameters"></a>Parametreler  
 `T`  
 Tüm numaralandırma türü, değer sınıfı ya da değer yapısı. Yerleşik türler içeren [varsayılan ad alanı](../cppcx/default-namespace.md).  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `Platform::Box<T>^` özgün değeri temsil eden örneği Kutulu ref sınıfta.  
  
## <a name="t"></a>  Box::operator T işleci
Kutulama dönüşümleri değeri sınıfından etkinleştirir `T` veya `enum` sınıfı `T` için `Box<T>`.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
operator Box<T>^(T valueType);  
```  
  
### <a name="parameters"></a>Parametreler  
 `T`  
 Tüm numaralandırma türü, değer sınıfı ya da değer yapısı. Yerleşik türler içeren [varsayılan ad alanı](../cppcx/default-namespace.md).  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `Platform::Box<T>^` özgün değeri temsil eden örneği Kutulu ref sınıfta.  
  

## <a name="value"></a> Box::Value özelliği
İçinde kapsüllenir değeri döndürür `Box` nesnesi.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
virtual property T Value{  
   T get();  
}  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bunu Kutulu önce ilk olarak önceki gibi aynı türde Kutulu değeri döndürür.  
  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Platform ad alanı](../cppcx/platform-namespace-c-cx.md)   
 [Kutulama](../cppcx/boxing-c-cx.md)