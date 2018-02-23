---
title: "Platform::WriteOnlyArray sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::WriteOnlyArray::begin
- VCCORLIB/Platform::WriteOnlyArray::Data
- VCCORLIB/Platform::WriteOnlyArray::end
- VCCORLIB/Platform::WriteOnlyArray::FastPass
- VCCORLIB/Platform::WriteOnlyArray::Length
- VCCORLIB/Platform::WriteOnlyArray::set
dev_langs:
- C++
helpviewer_keywords:
- Platform::WriteOnlyArray Class
ms.assetid: 92d7dd56-ec58-4b8c-88ba-9c903668b687
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 081dc6489b6cd16ef9065ce8ec332c7593105617
ms.sourcegitcommit: a5a69d2dc3513261e9e28320e4e067aaf40d2ef2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/21/2018
---
# <a name="platformwriteonlyarray-class"></a>Platform::WriteOnlyArray sınıfı
Arayan doldurmak yöntemi için bir dizi geçtiğinde giriş parametresi olarak kullanılan bir tek boyutlu dizi temsil eder.  
  
 Bu ref sınıf private vccorlib.h olarak bildirilmiş; Bu nedenle, meta verilerde yayılan değil ve yalnızca C++ içinden tüketilebilir. Bu sınıf yalnızca çağıran ayrılmış sahip bir dizi alan giriş parametresi olarak kullanıma yöneliktir. Kullanıcı kodundan oluşturulabilir değil. Doğrudan bu diziye yazmak bir C++ yöntemi sağlar — olarak bilinen bir deseni *FillArray* düzeni. Daha fazla bilgi için bkz: [dizi ve WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
private ref class WriteOnlyArray<T, 1>  
```  
  
### <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
 Bu yöntemler iç erişilebilirlik sahip — diğer bir deyişle, bunlar yalnızca C++ uygulama veya bileşen içinde erişilebilir.  
  
|Ad|Açıklama|  
|----------|-----------------|  

|[WriteOnlyArray::begin](#begin)| Dizinin ilk öğesi işaret yineleyici. |  
|[WriteOnlyArray::Data](#data)| Veri arabelleği için bir işaretçi. |  
|[WriteOnlyArray::end](#end)| Bir dizi son öğesi geçmiş işaret yineleyici. |  
|[WriteOnlyArray::FastPass](#fastpass)| Dizi saydam sistem tarafından gerçekleştirilen bir iyileştirme FastPass mekanizması kullanıp kullanamayacağını belirtir. Bu, kodunuzda kullanma |  
|[WriteOnlyArray::Length](#length)| Dizide öğe sayısını döndürür. |  
|[WriteOnlyArray::set](#set)| Belirtilen öğe belirtilen değere ayarlar. |  

  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `WriteOnlyArray`  
  
### <a name="requirements"></a>Gereksinimler  
 Compiler option: **/ZW**  
  
 **Meta veriler:** Platform.winmd  
  
 **Namespace:** Platform  

## <a name="begin"></a>  WriteOnlyArray::begin yöntemi
Dizinin ilk öğe için bir işaretçi döndürür.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
T* begin() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dizinin ilk öğe için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yineleyici STL algoritmalarıyla gibi kullanılabilir `std::sort` dizideki öğeler üzerinde çalışılacak.  
  


## <a name="data"></a>  WriteOnlyArray::Data özelliği
Veri arabelleği işaretçi.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
property T* Data{  
   T* get() const;  
}  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ham dizi bayt gösteren bir işaretçi.  
  


## <a name="end"></a>  WriteOnlyArray::end yöntemi
Bir dizi son öğesi geçmiş bir işaretçi döndürür.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
T* end() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşaretçi yineleyici bir dizi son öğesi geçti.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yineleyici STL algoritmalarıyla gibi işlemleri gerçekleştirmek için kullanılabilir `std::sort` dizi öğelerde.  
  


## <a name="fastpass"></a>  WriteOnlyArray::FastPass özelliği
İç FastPass iyileştirme gerçekleştirip gerçekleştirmediğini belirtir. Kullanıcı kodu tarafından kullanılmaya değil.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
property bool FastPass{  
   bool get() const;  
}  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dizi FastPass olup olmadığını belirten Boolean değeri.  
  


## <a name="get"></a>  WriteOnlyArray::get yöntemi
Belirtilen dizindeki öğeyi döndürür.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
T& get(  
   unsigned int indexArg) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `indexArg`  
  
### <a name="return-value"></a>Dönüş Değeri  
  


## <a name="length"></a>  WriteOnlyArray::Length özelliği
Arayana ayrılan dizisinde öğe sayısını döndürür.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
property unsigned int Length{  
   unsigned int get() const;  
}  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dizideki öğelerin sayısı  
  


## <a name="set"></a>  WriteOnlyArray::set işlevi
Dizideki belirtilen dizindeki belirtilen değere ayarlar.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
T& set(  
   unsigned int indexArg,  
   T valueArg);  
```  
  
### <a name="parameters"></a>Parametreler  
 `indexArg`  
 Ayarlamak için öğenin dizini.  
  
 `valueArg`  
 Konumundaki ayarlanacak değer `indexArg`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir başvuru öğesine ayarlamanız yeterlidir.  
  

  
### <a name="remarks"></a>Açıklamalar  
 HRESULT değeri yorumlama hakkında daha fazla bilgi için bkz: [COM hata kodları yapısı](http://go.microsoft.com/fwlink/p/?LinkId=262045).  
  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Platform Namespace](platform-namespace-c-cx.md)   
 [C++'ta Windows çalışma zamanı bileşenleri oluşturma](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)